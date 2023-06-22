# Today I Learned

We constantly learn new things. This is a repo to share those learnings.
TILs are short Markdown documents (a few sentences + example code) explaining
concepts, bits of syntax, commands, or tips we've recently learned.

Today-I-Learned (TIL) is inspired by Thoughbot, TIL is a repository for everyone to share what we have learn today.

This repo has a tool that help you to manage and write down what you learned in scientific way.

# What I learned

| Table of Contents | ⬇️ |
| -------- | -------- |
| 🆕 **Top 5 recent learning** | |
| [SOAP basics](API/SOAP-basics.md) [API] | 2023-06-22 |
| [Rest Vs Soap](API/rest-vs-soap.md) [API] | 2023-06-22 |
| [Creating certificate in go](Golang/Creating-certificate-in-go.md) [Golang] | 2023-06-19 |
| [Distributed Cache and Caching Strategies](Distributed-System/Distributed-Cache-and-Caching-Strategies.md) [Distributed-System] | 2023-06-18 |
| [Implement LRU Cache in Golang](Golang/Implement-LRU-Cache-in-Golang.md) [Golang] | 2023-06-18 |
| 📚 **API** [ 2 articles ] | |
| 1. [SOAP basics](API/SOAP-basics.md) | 2023-06-22 |
| 2. [Rest Vs Soap](API/rest-vs-soap.md) | 2023-06-22 |
| 📚 **Database** [ 2 articles ] | |
| 3. [Database Sharding and Partitioning](Database/Database-Sharding-and-Partitioning.md) | 2023-06-14 |
| 4. [Model Your Relational Database Data as NoSQL Document Data](Database/Model-Your-Relational-Database-Data-as-NoSQL-Document-Data.md) | 2023-06-17 |
| 📚 **Distributed-System** [ 1 articles ] | |
| 5. [Distributed Cache and Caching Strategies](Distributed-System/Distributed-Cache-and-Caching-Strategies.md) | 2023-06-18 |
| 📚 **Golang** [ 3 articles ] | |
| 6. [Golang pointers + GC](Golang/Golang-pointers-+-GC.md) | 2023-06-15 |
| 7. [Implement LRU Cache in Golang](Golang/Implement-LRU-Cache-in-Golang.md) | 2023-06-18 |
| 8. [Creating certificate in go](Golang/Creating-certificate-in-go.md) | 2023-06-19 |
| 📚 **Microservices** [ 3 articles ] | |
| 9. [API Composition Pattern in Microservices](Microservices/API-Composition-Pattern-in-Microservices.md) | 2023-06-15 |
| 10. [Designing Workflows in Microservices : Orchestration vs Choreography](Microservices/Designing-Workflows-in-Microservices-:-Orchestration-vs-Choreography.md) | 2023-06-17 |
| 11. [Handling timeouts in a microservice architecture](Microservices/Handling-timeouts-in-a-microservice-architecture.md) | 2023-06-17 |
| 📚 **Programming-Languages** [ 1 articles ] | |
| 12. [Why do programming languages need automatic garbage collection?](Programming-Languages/Why-do-programming-languages-need-automatic-garbage-collection?.md) | 2023-06-15 |


# Instruction

- Step 1: Fork this repo (blank-repo with **only tool** and **readme file**).
- Step 2: Start writting down what you learned in **everyday**.
  + Create a **topic** by:

    ```bash
    ./til <CATEGORY> <SUBJECT> [EDITOR]
    ```

    - Ex:

    ```bash
    ./til bash "Bash Conditional Expression" vim
    ```

    - If you tired of typing the quote mark:

    ```bash
    ./til bash Bash-Conditional-Expression
    ./til bash Bash=Conditional=Expression
    ```

    DO NOT mix the `-` and `=` together!
  + It will create 1 file whose name which is the SUBJECT in lower case:  `bash/160510-bash-conditional-expression.md`.
  + **Write** it! **Save** it!
- Step 3: Commit what you learned today by `./til commit`. After that, if you want to push it to _repository_, just **Enter**

# License

© 2018 khanhicetea.
Distributed under the [Creative Commons Attribution License][license].

[license]: http://creativecommons.org/licenses/by/3.0/
