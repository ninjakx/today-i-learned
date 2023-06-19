- Date : 2023-06-19
- Tags : #Golang

## Creating certificate in go

```
package main

import (
	"fmt"
	"io/ioutil"
	"log"
	"os"

	"github.com/beevik/etree"
	"github.com/russellhaering/goxmldsig"
)

func main() {
	// Load the XML to be signed
	doc := etree.NewDocument()
	if err := doc.ReadFromFile("./path/to/file/tobesigned.xml"); err != nil {
		log.Fatal(err)
	}

	// Create a new signing context
	ctx, err := dsig.NewDefaultSigningContext(dsig.NewMemoryKeyStore())
	if err != nil {
		log.Fatal(err)
	}

	// Use the c14n exclusive canonicalization
	ctx.CanonicalizationMethod = dsig.CanonicalizationMethodExclusiveXML

	// Sign using SHA-256
	ctx.SignatureMethod = dsig.SignatureMethodRSASHA256

	// Add a reference to the document
	ref := dsig.NewReference()
	ref.URI = ""
	ref.Transforms.Add(dsig.NewEnvelopedSignatureTransform())
	ref.DigestMethod = dsig.DigestMethodSHA256
	ctx.AddReference(ref)

	// Load the private key
	keyData, err := ioutil.ReadFile("./path/to/privatekey.pem")
	if err != nil {
		log.Fatal(err)
	}
	keyPair, err := ctx.KeyStore.LoadKeyPair(keyData, nil)
	if err != nil {
		log.Fatal(err)
	}

	// Sign the XML file
	if err := ctx.Sign(keyPair); err != nil {
		log.Fatal(err)
	}

	// Add the associated public key to the signature
	certData, err := ioutil.ReadFile("./path/to/file/mycert.pem")
	if err != nil {
		log.Fatal(err)
	}
	ctx.KeyInfo.AddX509Data(certData)

	// Append the signature to the XML
	if err := ctx.CreateSignature(doc.Root()); err != nil {
		log.Fatal(err)
	}

	// Save the signed XML
	signedXML, err := os.Create("./path/to/signed.xml")
	if err != nil {
		log.Fatal(err)
	}
	defer signedXML.Close()

	if _, err := doc.WriteTo(signedXML); err != nil {
		log.Fatal(err)
	}

	fmt.Println("XML successfully signed!")
}
```

