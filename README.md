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
