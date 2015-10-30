# add examples of using mocks and doubles
# don't look at the solutions!

[google trends][testing-trends] - cucumber ruby, rspec ruby, test unit ruby

[testing-trends]: http://www.google.com/trends/explore#q=rspec%20ruby%2C%20test%20unit%20ruby%2C%20cucumber%20ruby&cmpt=q

# Links

* [SLIDES](https://docs.google.com/a/appacademy.io/presentation/d/1SfyX0dn_dtDfLUfXH5zn89NCGoxQFTNDCgFxXcxRQWQ/edit?usp=sharing)
* [BetterSpecs.org](http://betterspecs.org/)

## TDD: Test Driven Development

* Automated testing > manual testing
* Having automated tests reduces fear of adding features and refactoring
* Write the tests first
* Writing tests helps you solidify your features and plan out your approach
  * Plan method inputs and outputs
* Red/Green/Refactor:
  1) Write the test
  2) Watch it fail (Red)
  3) Write code to make it pass (Green)
  4) Go back and refactor the code (Refactor)
  - This is the 'Red, green, refactor' approach
  - Not often used irl, but good for practice
  - AND many places admire TDD
  - Good to watch it fail then go green to make sure you're actually testing
    the code you think you're testing

* What to test?
 - Public methods, because if those work the private ones should work too
   * Private methods support public ones
 - ALL the public methods (be thorough today)
 - You already know OO programming; focus on RSpec and testing today.

* Types of tests
 - Unit
 - Integration

* **BDD**: Behavior-Driven Development
  * Basically TDD but with a newer, English-like syntax
  * RSpec uses BDD syntax

## Introduction to RSpec

* What is RSpec?
 - Just a Ruby library
 - All of the 'magic' methods are still Ruby methods
 - Gems are libraries
 - Is an example of a *Domain-Specific Language*
 - Divided into multiple gems: core, expectations, and mocks

* Why learn RSpec?
  - Its easier to have test in place, rather than have to go back and test later
  - Debugging
  - Maintaining
  - Jobs

## RSpec Syntax

* describe/context: Organizes tests
  * Usually specifies a class, method, or feature name
* it: Contains expectations for an actual test
* expect: New way of actually testing a value
  * Has to be inside an `it` block
  * `object.should` is the old way
  * expect { 3 / 0 }.to raise_exception
* subject: Specifies which object RSpec should use for implicit tests
  * e.g. `its(:something) { should... }`
  * Will be implicitly created if you describe a class and don't specify it
* let: *Lazily* defines values for use in your tests
  * Is run once for each `it` block
  * Doesn't run until it's called
    * Can use `let!` to have it created immediately
* before(:each): Holds set up code to be used in multiple it blocks
  * Run for each test so tests don't share state
  * Has to be in describe/context, not inside it
* Conveniences
  * Boolean methods shortcut
    * e.g. `#empty?` called with `be_empty`

## Test doubles
* A "fake" object that steps in for a real object for the run of a test
* Use to decouple specs for a class from the class that it uses
* Can start testing a class that uses a second class before
  writing the second class
* Only need to give the double the things that the method under test needs
* Can use *method expectations* to verify that class under test calls
  specific methods on the double
* Should only be used in unit tests

## guard-rspec

## DEMO

* `rspec --init` to set up `lib` and `spec` directories
  * RSpec adds lib folder to Ruby's `$LOAD_PATH`
  * Adds `.rspec` file where you can add arguments to rspec command
  * Creates `spec_helper.rb`, where you can add additional config
* Write spec file
  * `require 'rspec'` and `require 'code_under_test'`

* Setting Up and Syntax
 - Demo
 - 'should' vs. 'expect' (old and new syntax)
 - You won't use rake today

* Read the Docs
 - In general, towards the end of each unit (Ruby, SQL, Rails),
 we will expect you to read the docs and use google.
 - This is good; reading documentation is a skill.

 ALSO Please do warm-up project first ("First TDD Projects")

 # Projects

 ## TDD Array Exercises

 ## Poker

# Content

Demo hanoi, convert from method to class
```rb
init
  sets up default set of stacks
  sets up default first stack
  sets up first stack with disks specified
over
  tests if the game is over
move_disk
  from and to (raise exception here) expect { 3 / 0 }.to raise_exception
```
