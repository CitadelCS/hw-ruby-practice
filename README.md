Ruby Practice
=============

This homework gives some basic practice in Ruby as well as
getting you accustomed to making testing a regular part of your workflow.

**NOTE: Do not post your solutions publicly.**

You do not need a GitHub account to complete this homework, but if you have one you can use it. Follow the steps below to get the starter code ready to go. Commands are shown below the list.

1. Click the green "clone or download" button on this repository's page on GitHub and copy the URL to the clipboard.
2. Access Cloud9 or your IDE of choice and clone the repository (from the root of your workspace).
3. Install the `bundler` gem.
4. Change into the homework directory
5. Run the `bundle` command, which will install necessary gemfiles.

```sh
   $ git clone https://github.com/citadelcs/hw-ruby-practice.git
   $ gem install bundler
   $ cd hw-ruby-practice
   $ bundle
```

When the above completes successfully you'll have RSpec installed and can
run `rspec` from the command line to test your code.


Learning Goals
--------------
After completing this assignment, you will know how to:

* Write simple code that uses basic constructs in the Ruby language, including methods and arguments, conditionals, string and array manipulation, regular expressions, and basic object-oriented programming mechanisms
* Understand the Ruby project conventions for where code files and test files are located in a project's directory hierarchy
* Run individual tests or suites of tests using the RSpec unit testing tool
* Understand the basic syntax of RSpec unit tests
 
Overview
--------

**You may find the [Ruby documentation at ruby-doc.org](https://ruby-doc.org) helpful to have on hand.**

The repo for this assigment follows a fairly standard Ruby convention for codebases: the code
files are stored in `lib/` and the test files are stored in `spec/`.
(We use the RSpec unit-testing framework; if we were using Ruby's default
framework, known as `Test::Unit`, the test files would be under
`test/`.)

**We've placed "starter code" in `lib/`; when you're all done, you
can submit this single file to the autograder.**

However, you can test each of the 3 parts of `ruby_intro.rb` separately.  The files
`spec/intro_part[123]_spec.rb` contain RSpec tests for each of the three
parts.  For example, to test your answers to Part 1, say `rspec
spec/part1_spec.rb`.  `rspec` with no arguments runs the tests in all
the files `spec/*_spec.rb`. You can test the other two parts with the `dessert` and
`fun_with_strings` rspec files.

* The line numbers in the RSpec error report will
give you guidance as to which tests failed.  (You can check the [RSpec
documentation](http://rspec.info) to see how the `.rspec` file can be
used to customize the output format.)

While we provide an explanation of how your code should work in this
handout, you should get accustomed to the idea that the true
specification is in the test files! Initially, all tests are marked
"pending", as indicated by the argument `:pending => true` in each
`describe` block.  To start working on a question, remove this option:

e.g. in `fun_with_strings_spec.rb`, change:

    describe 'palindrome detection', :pending => true do
to

    describe 'palindrome detection' do

and save the spec file.

As you fill in code in the appropriate files under `lib/`, each time
you save changes to that file re-run your tests.
When a test passes, it's displayed in green.  Your goal is to get all
tests for all parts to pass green.


# 1. Arrays, Hashes, and Enumerables

Check the [Ruby 2.x documentation](http://ruby-doc.org) on `Array`,
`Hash` and `Enumerable` as they could help tremendously with these
exercises. :-) 

0. Define a method `sum(array)` that takes an array of integers as an argument and returns the sum of its elements. For an empty array it should return zero.  Run associated tests via:  `$ rspec -e '#sum ' spec/intro_part1_spec.rb`

0. Define a method `max_2_sum(array)` which takes an array of integers as an argument and returns the sum of its two largest elements. For an empty array it should return zero. For an array with just one element, it should return that element. Run associated tests via:  `$ rspec -e '#max_2_sum' spec/intro_part1_spec.rb`

0. Define a method `sum_to_n?(array, n)` that takes an array of integers and an additional integer, n, as arguments and returns true if any two elements in the array of integers sum to n. `sum_to_n?([], n)` should return false for any value of n, by definition. Run associated tests via:  `$ rspec -e '#sum_to_n' spec/intro_part1_spec.rb` 

You can check your progress on the all the above by running `$ rspec spec/intro_part1_spec.rb`.

# 2. Strings and Regular Expressions

Check the documentation on String and Regexp as they could help tremendously with these exercises. :-)

0. Define a method `hello(name)` that takes a string representing a name and returns the string "Hello, " concatenated with the name. Run associated tests via:  `$ rspec -e '#hello' spec/part2_spec.rb`

0. Define a method `starts_with_consonant?(s)` that takes a string and returns true if it starts with a consonant and false otherwise. (For our purposes, a consonant is any letter other than A, E, I, O, U.) NOTE: be sure it works for both upper and lower case and for nonletters!  Run associated tests via:  `$ rspec -e '#starts_with_consonant?' spec/part2_spec.rb`

0. Define a method `binary_multiple_of_4?(s)` that takes a string and returns true if the string represents a binary number that is a multiple of 4. NOTE: be sure it returns false if the string is not a valid binary number!  Run associated tests via:  `$ rspec -e '#binary_multiple_of_4?' spec/part2_spec.rb`

You can check your progress on the all the above by running `$ rspec spec/intro_part2_spec.rb`.

# 3. Object Oriented Basics

Define a class `BookInStock` which represents a book with an ISBN
number, `isbn`, and price of the book as a floating-point number,
`price`, as attributes. Run associated tests via:  `$ rspec -e 'getters and setters' spec/intro_part3_spec.rb` 

The constructor should accept the ISBN number
(a string, since in real life ISBN numbers can begin with zero and can
include hyphens) as the first argument and price as second argument, and
should raise `ArgumentError` (one of Ruby's built-in exception types) if
the ISBN number is the empty string or if the price is less than or
equal to zero.  Include the proper getters and setters for these
attributes. Run associated tests via:  `$ rspec -e 'constructor' spec/intro_part3_spec.rb`

Include a method `price_as_string` that returns the price of
the book formatted with a leading dollar sign and two decimal places, that is, a price
of 20 should format as "$20.00" and a price of 33.8 should format as
"$33.80". Run associated tests via:  `$ rspec -e '#price_as_string' spec/intro_part3_spec.rb`

You can check your progress on the all the above by running `rspec spec/intro_part3_spec.rb`.

# 4. Basic Object-Oriented Programming for Dessert

Specs: `spec/dessert_spec.rb`

Skeleton: `lib/dessert.rb`

1. Create a class Dessert with getters and setters for name and
calories.  The constructor should accept arguments for name and
calories.  

2. Define instance methods `healthy?`, which returns true iff a
dessert has less than 200 calories, and `delicious?`, which returns true
for all desserts. 

3. Create a class JellyBean that inherits from Dessert.  The constructor
should accept a single argument giving the jelly bean's flavor; a
newly-created jelly  bean should have 5 calories and its name should be
the flavor plus "jelly bean", for example, "strawberry jelly bean".

4. Add a getter and setter for the flavor. 

5. Modify `delicious?` to return false if the flavor is
`licorice`, but true for all other flavors.  The behavior of
`delicious?` for non-jelly-bean desserts should be unchanged.

# 5 Fun With Words and Strings

Specs: `spec/fun_with_strings_spec.rb`

Skeleton: `lib/fun_with_strings.rb`

In this problem, you'll implement three functions that perform
basic string processing.  You can start from the template
`fun_with_strings.rb`.

## Part A: Palindromes

A palindrome is a word or phrase that reads the same forwards as
backwards, ignoring case, punctuation, and nonword characters.  (A
"nonword character" is defined for our purposes as "a character that
Ruby regular expressions would treat as a nonword character".) 

You will write a method `palindrome?` that returns true iff its
receiver is a palindrome.

As you can see in the template `fun_with_strings.rb`, we arrange to mix
your method into the `String` class so it can be called like this:

    "redivider".palindrome?    # => should return true
    "adam".palindrome?         # => should return false or nil

Your solution shouldn't use loops or iteration of any kind. Instead, you
will find regular-expression syntax very useful; it's reviewed briefly
in the book, and the [Rubular](http://www.rubular.com) website
lets you try out Ruby
regular expressions "live". Some methods that you might find useful
(which you'll have to look up in the [Ruby
documentation](http://ruby-doc.org)) include
`String#downcase`, `String#gsub`, and `String#reverse`.

The spec file contains a number of test cases.  At a minimum, all should
pass before you submit your code.  We may run additional cases as well.

## Part B:  Word Count

Define a function `count_words` that, given an input string, return a
hash whose keys are words in the string and whose values are the number
of times each word appears:

    "To be or not to be"  # => {"to"=>2, "be"=>2, "or"=>1, "not"=>1}

Your solution shouldn't use for-loops, but iterators like `each` are
permitted. As before, nonwords and case should be ignored. A word is
defined as a string of characters between word boundaries. 

## Part C:  Anagrams

An anagram group is a group of words such that any one can be converted
into any other just by rearranging the letters.  For example, "rats",
"tars" and "star" are an anagram group.

Given a space separated list of words in a single string,
write a method that groups them into anagram groups 
and returns a nested array of those groups (an array of arrays).
Case doesn't matter in classifying string as anagrams
(but case should be preserved in the output),
and the order of the anagrams in the groups doesn't matter. 

Hint: see the rspec tests for an example and check out string class methods such as split, join, chars, sort, etc.

## Extra Challenge

Try getting setup with 
an automated test framework such as [guard](http://code.tutsplus.com/tutorials/testing-your-ruby-code-with-guard-rspec-pry--cms-19974) or [autotest](https://rubygems.org/gems/autotest).  Guard or AutoTest can be set up so that 
they will run all the tests in `spec/`, but every time you edit and save 
your code file, the tests are automatically re-run, so you don't have to 
run them manually.  As we'll see later, this is the "watch the test fail" 
part of the TDD or test-driven process of development: write the tests before
you write the code, watch the test fail, fill in the code and save the code file, 
then watch the test pass!

# Submission Directions

Since we don't have access to an autograder, you must compile a submission document showing your source code and rspec summary output for each of the five parts. Your document must be neat and professionally formatted.

On the first page, make sure to include your name and partner's name, the assignment details, etc.

Next, include the *summary* rspec output for each of the 5 problems. You can get all of this at once by typing `rspec` in the homework directory. This is the first part of the output that shows the red/green results with point values in brackets, as illustrated below. Please do not include the detailed report of any failures.

Please copy/paste the text from the console instead of taking screen shots, which are hard to see. You do not need to reproduce the colors if they don't copy easily, but please choose a good type face and font size to keep it readable. (recommended: consolas 10pt)


```
mverdicchio:~/environment/hw-ruby-practice (master) $ rspec

Ruby intro part 1
  #sum
    should be defined
    returns correct sum [20 points] (FAILED - 1)
    works on the empty array [10 points] (FAILED - 2)
  #max_2_sum
    should be defined
...
...
```

On the next pages, please include your source code for each of the three files (`ruby_intro.rb`, `dessert.rb`, and `fun_with_strings.rb`). Make sure the code is easy to read and doesn't have bad line breaks.

Finally, save this document and upload it to CitLearn by the deadline. Each partner needs to submit the file.