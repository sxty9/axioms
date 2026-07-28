---
id: ax_t3ztomv256bqw64t
titel: Erledigtes vor dem Start feststellen
---
Vor dem Start eines Vorgangs wird festgestellt, welcher Teil seiner Arbeit bereits vorliegt und wie weit dieser Teil auf dem Weg zum Standard-Branch gekommen ist. Die Feststellung erfolgt aus dem tatsächlichen Zustand der Repositories — Arbeitsstand, Lieferungen, Pull Requests, Standard-Branch — und nicht aus einem Merkmal, das der Vorgang über sich selbst führt.

Unterschieden werden drei Fälle: nicht umgesetzt; umgesetzt und nicht ausgeliefert; ausgeliefert. Ein einzelnes Merkmal "offen" genügt nicht, weil es den zweiten Fall mit dem ersten verwechselt.

Liegt Arbeit bereits vor, wird sie nicht erneut erzeugt. Der Vorgang beschränkt sich auf den noch nicht zurückgelegten Teil des Weges und meldet das als solches.
