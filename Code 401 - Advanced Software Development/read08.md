
# Don't repeat yourself"

> Rule of three ("Three strikes and you refactor") is a code refactoring rule of thumb to decide when similar pieces of code should be refactored to avoid duplication. It states that two instances of similar code do not require refactoring, but when similar code is used three times, it should be extracted into a new procedure. The rule was popularised by Martin Fowler in Refactoring[1] and attributed to Don Roberts.

> Duplication is considered a bad practice in programming because it makes the code harder to maintain. When the rule encoded in a replicated piece of code changes, whoever maintains the code will have to change it in all places correctly.

> "Refactor" redirects here. For the use of "refactor" on Wikipedia, see Wikipedia:Refactoring talk pages.
This article is about a behaviour-preserving change. It is not to be confused with Rewrite (programming).

> Refactoring is usually motivated by noticing a code smell.[2] For example, the method at hand may be very long, or it may be a near duplicate of another nearby method. Once recognized, such problems can be addressed by refactoring the source code, or transforming it into a new form that behaves the same as before but that no longer "smells".

For a long routine, one or more smaller subroutines can be extracted; or for duplicate routines, the duplication can be removed and replaced with one shared function. Failure to perform refactoring can result in accumulating technical debt; on the other hand, refactoring is one of the primary means of repaying technical debt.[3]


> "You aren't gonna need it"[1][2] (YAGNI)[3] is a principle of extreme programming (XP) that states a programmer should not add functionality until deemed necessary.[4] XP co-founder Ron Jeffries has written: "Always implement things when you actually need them, never when you just foresee that you need them."[5] Other forms of the phrase include "You aren't going to need it"[6][7] and "You ain't gonna need it".[8]