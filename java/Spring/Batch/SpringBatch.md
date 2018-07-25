**What is Spring Batch?**

Spring batch is a lightweight, comprehensive batch framework designed to enable the development of robust batch applications vital for 
the daily operations of enterprise systems. Spring Batch builds upon the characteristics of the Spring Framework that people have
come to expect (productivity, POJO-based development approach, and general ease of use), while making it easy for developers to access 
and leverage more advance enterprise services when necessary.

**Business oparation:**

Automate, complex processing of large amount of data that is most efficiently processed without human intaraction. Like schedulers Month 
end calculation, notices etc.

Integration of information that is recieved from internal and external system that typically needs to be formating,validating and
processing in a transactional manner into the system of records.

**Usage Scenario:**

1) Reads a large no of records from database, file or queue.
2) processes the data in some critaria.
3) write data in modified form.

**Spring Batch Architechture:**

Three tier architechture Application, Batch Core and Batch Infustructure.

Application: It's contain all the batch jobs and Custom code written by devoloper using spring batch.

Batch Core: It's contain core runtime classes necessary to launc and control a batch job

Batch Infustructure: Both Application and Batch core build on common infustructure. It's containe ItemReader, ItemWriter.

**General Batch Principles and Guidelines:**

Minimized the system resources like I/O oparation. Perform in internal memory.
Review application I/O (analyze SQL statements) to ensure that unnecessary physical I/O is avoided. In particular, the following four common flaws need to be looked for:

    1) Reading data for every transaction when the data could be read once and cached or kept in the working storage.
    2) Rereading data for a transaction where the data was read earlier in the same transaction.
    3) Causing unnecessary table or index scans.
    4) Not specifying key values in the WHERE clause of an SQL statement.

