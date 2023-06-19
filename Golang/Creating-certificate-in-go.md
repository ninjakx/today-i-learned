- Date : 2023-06-19
- Tags : #Golang

## Creating certificate in go

```
package main

import (
	"crypto/rsa"
	"crypto/x509"
	"encoding/pem"
	"fmt"
	"io/ioutil"
	"os"

	"github.com/beevik/etree"
	"github.com/russellhaering/goxmldsig"
)

func main() {
	// Load the XML to be signed
	doc := etree.NewDocument()
	if err := doc.ReadFromFile("./path/to/file/tobesigned.xml"); err != nil {
		fmt.Println("Error loading XML:", err)
		os.Exit(1)
	}

	// Create a new Signature
	signature := goxmldsig.NewSignature()

	// Use the c14n exclusive canonicalization
	signature.CanonicalizationMethod = goxmldsig.EXC_C14N

	// Sign using SHA-256
	signature.SignedInfo.CanonicalizationMethod = goxmldsig.EXC_C14N
	signature.SignedInfo.SignatureMethod = goxmldsig.RSASHA256

	// Add the reference
	reference := goxmldsig.NewReference()
	reference.URI = ""
	reference.DigestMethod = goxmldsig.SHA256
	reference.Transforms.Add(goxmldsig.TransformEnveloped)
	signature.SignedInfo.References = append(signature.SignedInfo.References, reference)

	// Load the private key
	privateKeyBytes, err := ioutil.ReadFile("./path/to/privatekey.pem")
	if err != nil {
		fmt.Println("Error reading private key:", err)
		os.Exit(1)
	}

	block, _ := pem.Decode(privateKeyBytes)
	if block == nil {
		fmt.Println("Failed to parse PEM block containing the private key")
		os.Exit(1)
	}

	privateKey, err := x509.ParsePKCS1PrivateKey(block.Bytes)
	if err != nil {
		fmt.Println("Error parsing private key:", err)
		os.Exit(1)
	}

	signature.PrivateKey = privateKey.(*rsa.PrivateKey)

	// Sign the XML file
	if err := signature.Sign(doc); err != nil {
		fmt.Println("Error signing XML:", err)
		os.Exit(1)
	}

	// Load the certificate
	certBytes, err := ioutil.ReadFile("./path/to/file/mycert.pem")
	if err != nil {
		fmt.Println("Error reading certificate:", err)
		os.Exit(1)
	}

	block, _ = pem.Decode(certBytes)
	if block == nil {
		fmt.Println("Failed to parse PEM block containing the certificate")
		os.Exit(1)
	}

	cert, err := x509.ParseCertificate(block.Bytes)
	if err != nil {
		fmt.Println("Error parsing certificate:", err)
		os.Exit(1)
	}

	// Add the associated public key to the signature
	signature.KeyInfo = &goxmldsig.KeyInfo{}
	signature.KeyInfo.AddX509Data(cert)

	// Append the signature to the XML
	if err := signature.AppendSignature(doc.FindElement("//Signature")); err != nil {
		fmt.Println("Error appending signature:", err)
		os.Exit(1)
	}

	// Save the signed XML
	if err := doc.WriteToFile("./path/to/signed.xml"); err != nil {
		fmt.Println("Error saving signed XML:", err)
		os.Exit(1)
	}

	fmt.Println("XML signed successfully!")
}
```

