[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

vendor quirks ontology (vqo)
============================

The vendor quirks ontology (vqo) provides vocabulary to classify and
relate certain synthetic contract variants of exchange-listed
derivatives.


Why?
----

FIBO's official ontology heavily focusses on modelling the backoffice
and regulatory reference side of things, real instruments, real
entities, and real venues.  Analytical and strategy development
workflows only exist as an afterthought.

In the realm of exchange-listed derivatives, the number one analytical
tool would be a *synthetic* contract that spans the lifetime of many
individual *specific* contracts and inheres a roll-over strategy.
Unlike the actual underlying benchmark (which sometimes wouldn't even
exist) the synthetic contract is fully and easily replicable.

With a few exceptions, exchanges don't offer perpetual contracts off
the shelf, presumably not to fragment liquidity any further, given the
sheer number of possible combinations between front-month and
back-month exposure (possibly stretching out to further terms) and/or
roll-over strategies.


How?
----

Classes `vqo:FutureChain` and `vqo:OptionChain` are introduced as
collections that share the same contract specification on one
exchange, pretty much a vendor's definition of the futures or option
chain.  And because chains (the collections) and contract
specifications are intricably linked and inseparable in practice (one
might say they are coextensive), they are not modelled as separate
classes, instead the chain itself serves as the unified conceptual
entity.

Next, and probably more controversial, `vqo:SyntheticFuture` is
created as subclass of `fibo-fbc-fi-fi:Future` to allow for
vendor-specific perpetual contracts.  Of which there are:

- vqo:BloombergGeneric
- vqo:RefinitivContinuation

and defined as synthetic futures created and maintained by
`vqo:Bloomberg` and `vqo:Refinitiv`, two individuals of type
`vqo:Vendor`.


Where?
------

The [official github repository](https://github.com/ga-group/vqo/) contains the
published ontology.

The project's canonical home is <http://schema.ga-group.nl/vqo/>.
