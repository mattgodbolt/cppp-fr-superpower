# Notes

## Runthrough Oct 31
* 4m backstory
* switch MUD and xania slides
* "do no harm" drop
* TODOs add more
* show version?
* after first simple fix need
    * build
    * run
    * manual test
* 20m to here
* What's next highlight
* 25m
* TODO on STL-i-f-cation on ptr stability
* 30m to class-i-fy slides
* Ranges...seems weak
* 50m to string formatting
* No joined up thinking about fmt (can't read my handwriting)
* fmt-> show variadic
* total 1h10


## Recent notes

What do I want folks to get from this talk?

* C++'s most criticised issues stem from backwards compatibility
    * Backwards compatibility is sometimes a real blessing
    * We can incrementally improve our codebases as standards evolve without ever breaking our apps and tools
    * Even as far back as 25 year-old-code
    * So, maybe cut C++ some slack, eh?
* Demonstrate some solid incremental change techniques
    * Testing, TDD
    * Refactoring in the genuine sense
* (also Matt is very human and is prepared to embarrass himself for some cheap laughs)

## Some kind of script?

* C++ super powers
* Before we talk about superpowers
* what things do we dislike?
* ... slide of them
    * https://twitter.com/mattgodbolt/status/1451997719367667714
        * Wrong defaults XXX
        * No standard package mgr XXX
            * Rich Felker "this is the best thing about it"
        * ABI compat XXX
        * "'70s design that is still all visible even in the latest versions"
        * "The syntax"
        * "Too big"
        * "UB"
        * "Implicit conversions"
        * "Based on C" https://twitter.com/richardmatthias/status/1452005934163759109?s=20
* What do I think C++'s super power is?
* All of these!
* "But Why Matt?!"
* Well, ok
* Backwards compatibility
* Whyso?
    * I can incrementally update my code as new things come in
    * C++11, C++14, I could opt in one part at a time inside the codebase
    * C++20 is quite a different language from C++98
        - show example
* Let me show you!
* I need some codebase to show this. Something I understand well, something that's open source, something that's been
  around a while.
* Let's bring it up to date to at least C++17, using new and cool features and libraries available.

----

* Xania! MUD from the mid-90s
* Backstory time, Exeter Uni, Physics, housemates and I played a lot of MUDs
* What is a MUD?
* We ran our own, got source, based on Diku/ROM, some code sharing with MadROM
* Ran until 2000s ish (check with Faramir)
* Found the source on an old hard disk
* C and some early C++
* Perfect!
* So! What does the code look like?!
* zomg pre-K&R C, and some C++
* DEMONSTRATE!
* What can we do to start cleaning it up?
* goals
    * make small changes
    * be able to keep running at each step
    * increase confidence nothing's broken as we go

----
* PREP WORK
* cmakify, git, wall extra rename
    * "What C isn't valid C++"
    * C/C++
    * `class`, `template`
* sanitizers
* Where to start?

----
* Memory management!
* Lots of strings copied all over the place!
* Let's start with a single field
* CRASH/etc - handle leaks/free() stuff
* sanitizers
* Leaving some noise, TODOs in the code, attributed, to come back to
    * things needing mutable strings? const char
* unique_ptr, gsl stuff?

----

* String formatting and manipulation
* fmt :allthethings:
* fmt and ranges
* intro testing here?

MORE NOTE FORM
* Section: strong types?
    * enum stuff
    * std array of things - all naked arrays gone
* Section: class-i-fication
    * collating functions
    * hiding members away
    * simplifying
    * testing!
* Section: unglobalisation (!)
* Conclusion!
* Some stats
* Reiterate goals
* THE FUTURE
    * C++20
    * fuzzing
    * epochs not a thing, but maybe there's a solution
    * BUT just remember not all languages get to do this!

## Transcribed from notebook:

### Timeline:

* code Sep 26, Oct 17 First draft (Fail)
* Oct 31 second draft (nearly failed)
* Nov 7 work runthrough
* Nov 15->21 practice, final draft
* Nov 21-Dec practice

### Diagram:

* Tell a story
* Personal
    * My journey
    * uni pics (!?) lan party
    * How I learned C and C++
* C++
    * ranges
    * Concepts
    * fmt
    * C++20?
* MUDs
    * "class" and "template" :D
    * compile old code. exactly
* 25+ year old C code
    * Incrementally update to C++17 (?20?)
        * show techniques
        * strong types
        * en-enumeratalizing
        * individual field updates
            * strings, string_views
        * "Class"ification
            * bringing groups of functions together
            * hiding impl details
            * all that good stuff
        * "de-globalling"
    * Herb keynote about language improvements
* funny old code practices
    * own mem mgr!
* Improvements in dev
    * testing!
    * fuzz testing?
    * conan

### Second handwritten notes

* Story -> ABI, backwards compaitability
* Day job, pain live at head, wrong defaults!?
* Things I love about C++
    * (list of terrible things)
    * No, really!
    * "But why, Matt?"

...

