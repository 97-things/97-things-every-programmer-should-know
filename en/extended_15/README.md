# Decouple that UI

Why decouple the UI from the core application logic? Such layering gives us the ability to drive the application via an API, the interface to core logic without involving the UI. The API, if well designed, opens up the possibility of simple automated testing, bypassing the UI completely. Additionally, this decoupling leads to a superior design.

If we build a UI layer cleanly separated from the rest of our system, the interface beneath the UI can be an appropriate point in which to inject a record/replay mechanism. The record/replay can be implemented via a simple serial file. As we are typically simulating user input with the record/replay mechanism, there is not usually a need for very high performance, but if you want it, you can build it.

This separation of UI testing from functional testing is constrained by the richness of the interface between the UI and the core system. If the UI gets massively reorganized then so necessarily does any attached mechanism. From the point of view of tracking changes and effects, once the system is baselined it is probably a good idea to baseline any record/replay logs in the event of needing to identify some subsequent change in system behavior. None of this is particularly difficult to do providing that it is planned in to the project and, eventually, there is a momentum in terms of knowledgeable practitioners in this part of the black art of testing.

Downsides: There is always at least one... usually that the investment in recording and replaying what are typically suites of regression tests becomes a millstone for the project. The cost of change to the suite becomes so high that it influences what can economically be newly implemented. The design of reusable test code requires the same skills as those for designing reusable production code.

Upsides: Regression testing is not sensitive to cosmetic changes in the UI, massive confidence in new releases, and providing that all error triggers are retrofitted into the record/replay tests, once a bug is fixed it can never return! Acceptance tests can be captured and replayed as a smoke test giving a minimum assured level of capability at any time.

Finally, just because the xUnit family of tools is associated with unit testing, they do not have to be restricted to this level. They can be used to drive these system-wide activities,via the UI-API as described above, providing a uniform approach to all tests at all levels.

By [George Brooke](http://programmer.97things.oreilly.com/wiki/index.php/George_Brooke)
