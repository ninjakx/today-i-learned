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
| [Designing Workflows in Microservices : Orchestration vs Choreography](Microservices/Designing-Workflows-in-Microservices-:-Orchestration-vs-Choreography.md) [Microservices] | (17 June 2023) |
| [Golang pointers + GC](Golang/Golang-pointers-+-GC.md) [Golang] | (15 June 2023) |
| [API Composition Pattern in Microservices](Microservices/API-Composition-Pattern-in-Microservices.md) [Microservices] | (15 June 2023) |
| [Why do programming languages need automatic garbage collection?](Programming-Languages/Why-do-programming-languages-need-automatic-garbage-collection?.md) [Programming-Languages] | (15 June 2023) |
| [Database Sharding and Partitioning](Database/Database-Sharding-and-Partitioning.md) [Database] | (14 June 2023) |
| 📚 **Database** [ 1 articles ] | |
| 1. [Database Sharding and Partitioning](Database/Database-Sharding-and-Partitioning.md) | (14 June 2023) |
| 📚 **Golang** [ 1 articles ] | |
| 2. [Golang pointers + GC](Golang/Golang-pointers-+-GC.md) | (15 June 2023) |
| 📚 **Microservices** [ 2 articles ] | |
| 3. [API Composition Pattern in Microservices](Microservices/API-Composition-Pattern-in-Microservices.md) | (15 June 2023) |
| 4. [Designing Workflows in Microservices : Orchestration vs Choreography](Microservices/Designing-Workflows-in-Microservices-:-Orchestration-vs-Choreography.md) | (17 June 2023) |
| 📚 **Programming-Languages** [ 1 articles ] | |
| 5. [Why do programming languages need automatic garbage collection?](Programming-Languages/Why-do-programming-languages-need-automatic-garbage-collection?.md) | (15 June 2023) |


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
