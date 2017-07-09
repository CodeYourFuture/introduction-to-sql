# Introduction to SQL

_Structured Query Language_ (SQL) provides a means of creating and manipulating databases, or more specifically, _relational database management systems_ (RDBMS).


## What's a Relational Database Management System?

An RDBMS is a representation of how rows in a table, known as _records_, are stored and related to each other.

Take a look at this table of patient appointments at a GP surgery:

![Flat file database](http://i.imgur.com/IlLazOJ.png)

What's wrong with this approach?

In order to accomodate for multiple appointment dates, this single-table approach requires the other columns to be duplicated; this introduces some major concerns:

* Larger storage footprint
* If a patient's doctor or phone number changes, then all copies must be updated
* Having multiple instances of the same data can result in incorrect input; take a look at the final record

It would be better to break this table down into respective tables for each entity:

![Separate tables](http://i.imgur.com/80X1Y3M.png)

Some of the tables contain IDs of related records, such as the appointment table's `id` column, but we still have to explicitly define our relationships. Before we jump into this, let's run some simple queries against the database.


## Browsing the database

For simplicity, our data is stored in an SQLite database; this is a self-contained file that can be read from and written to with no configuration, in contrast to MySQL that typically requires a connection string.

We're going to use [DB Browser for SQLite](http://sqlitebrowser.org/) to access our database, which is available for Windows, OS X, and Linux; please download it from the linked website.

Once it's installed and running, and you've cloned this repository, click _Open Database_, navigate to your copy of said repository, and open _surgery.sqlite_. You'll be greeted with the structure of our database. You may notice that there is a _Browse Data_ tab, but we will not be using this directly; instead, let's write our first query.


## `SELECT`

The `SELECT` statement returns a series of records from