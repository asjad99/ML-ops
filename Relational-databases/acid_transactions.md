

ACID is an extremely important & successful paradigm, but still debated!

Many debates over ACID, both **historically** and **currently**

Some “NoSQL” DBMSs relax ACID

In turn, now “NewSQL” reintroduces ACID compliance to NoSQL-style DBMSs…



**Transactions**

Definition: A transaction (“TXN”) is a sequence of one or more *operations* (reads or writes) which reflects *a single real-world transition*.

``` sql
	SET Price = Price – 1.99
	WHERE pname = ‘Gizmo’
	COMMIT
```



In “ad-hoc” SQL, each statement = one transaction

In a program, multiple statements can be grouped together as a transaction



```sql
START TRANSACTION
	UPDATE Bank SET amount = amount – 100 
	WHERE name = ‘Bob’
	UPDATE Bank SET amount = amount + 100 
	WHERE name = ‘Joe’
	COMMIT 

```



**ACID:** **A**tomicity

TXN’s activities are atomic: all or nothingC*ommits*: all the changes are made
A*borts*: no changes are made
(Intuitively: in the real world, a transaction is something that would either occur *completely* or *not at all)*

A**C**ID:**C**onsistency

The tables must always satisfy user-specified *integrity constraints**Examples:*Account number is uniqueStock amount can’t be negativeSum of *debits* and of *credits* is 0

How consistency is achieved:Programmer writes a TXN to go from one consistent state to a consistent state*System* makes sure that the TXN is atomic (e.g., if EXCEPTION, rolls back)

AC**I**D:Isolation

A transaction executes concurrently with other transactions

**Isolation**: the effect is as if each transaction executes in *isolation* of the others.
Conceptually similar to OS processes. Also, your browser tabs are “isolated” and do not see the behavior of other tabs. (Ignore “shared” cookies for this analogy)E.g. Should not be able to observe changes from other transactions during the run

ACI**D**: **D**urability

The effect of a TXN must continue to exist (*“persist”*) after the TXN

And after the whole program has terminatedAnd even if there are power failures, crashes, etc.And etc…
Means: Write data to disk (or durable IO system)