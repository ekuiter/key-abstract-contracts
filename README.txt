key-abstract-contracts (based on KeY 2.1)
======================

This version of the KeY verification system (http://key-project.org) can be used to evaluate abstract method contracting.
(Works with Java 8 by running key.sh/key.bat on Linux or Windows accordingly.)

The idea is to only substitute abstract placeholders for method calls instead of the concrete requires, ensures, and assignable clauses.
Such a proof is called a partial/incomplete/cached/abstract proof (with abstract placeholders), which leads to only first-order open obligations.

To create such a proof, load a file/directory in which some methods are annotated with @requires_abs, @ensures_abs, @assignable_abs and/or @def.
(@defs can be omitted at this point, as they provide the concrete clauses which are only filled in at a later step.)
Then right-click on 0: OPEN GOAL and select Strategy macros > Finish abstract proof part (or press Shift+X) - DO NOT use the green start button for this.
The resulting partial proof can be saved as a .proof file as usual.

To complete a partial proof later on (possibly with different concrete instantiations), again load the file/directory (now the @defs MUST be present).
When KeY is ready to prove (0: OPEN GOAL), run File > Reuse proof and select the .proof file saved above. The partial proof is replayed.
Now simply click the green start button to complete the proof with the given @defs.

(Note that for some of the given examples, setting "Arithmetic treatment" to "Model Search" may be required.)