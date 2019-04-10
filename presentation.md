## From GOTO to
## Gang of Four


##### A tour of programming paradigms
##### up to how we do things now.

<hr>

#### Why is programming hard?

Notes: To form an idea of why we have design principles and
paradigms, we should first ask ourselves, "Why is programming
hard?". You probably have some answers that are relative to your
day-to-day relationship with your job, or someone you are mentoring's
struggles, but to really get a grasp of why programming is so hard, we
need to ask a different question.

<hr>

#### How does a computer work?

Notes: If we take a moment to reflect on how complex computers really
are, it becomes glaringly obvious in short order not only why
programming is so hard, but why we as engineers and developers have
had to continue to build ever-more innovative ways of thinking about
how we compute things.

<hr>

### Part 1

## How a computer works

##### a retrospective

<hr>

### Early Computers

<hr>

### The Difference Engine

![The Difference
Engine](https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Babbage_Difference_Engine_%28Being_utilised%29.jpg/1009px-Babbage_Difference_Engine_%28Being_utilised%29.jpg)
<!-- .element: width="70%" height="70%" -->

Notes: Very early computers were devices we would now think of as
calculators. They did have programmable registers, but could only do
math. Babbage's Difference engine could calculate solutions to
single-variable polynomials up to x^7 with 31-digit numbers.

<hr>

### Alan Turing

![Alan
Turing](https://www.biography.com/.image/t_share/MTE5NDg0MDU1MTUzMTE2Njg3/alan-turing-9512017-1-402.jpg) <!-- .element: width="60%" height="60%" -->

Notes: By 1936, engineers had advanced computers enough to move from
spinning gears to electric switches driving mechanical relays. Due to
this increase in speed and automation, they had also derived how to
encode the idea of fixed-point arithmetic into their very large
calculators. In this same year, Alan Turing thought up the concept for
how a general-purpose programmable computer should work, the Turing Machine.

<hr>

### Turing Machine

![Turing Machine](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Turing_machine_2b.svg/550px-Turing_machine_2b.svg.png)

Notes: A Turing machine is an imaginary machine consisting of an
infinitely long tape, a movable head, and an instruction set to read a
value from a cell in the tape, write a value to a cell in the tape, or
to move the head in one direction or another. He hypothesized that
with this architecture any state could be represented, and that
therefore there must be some set of instructions to move from any one
state to any other state.

<hr>

### Zuse Z3

![Zuse
Z3](https://upload.wikimedia.org/wikipedia/commons/4/4c/Z3_Deutsches_Museum.JPG)<!-- .element: width="60%" height="60%" -->

Notes: by 1939, engineers had figured out how to move from electric
switches to relays, as well as represent Boolean logic and float-point
arithmetic. The Zuse Z3 which was finished in 1941 was the first
fully automatic programmable digital computer. Its programs were
stored on punched film and popularized the use of binary, probably
making it the first Turing-complete computer.

<hr>

### Colossus

![Colossus](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Colossus.jpg/1920px-Colossus.jpg)<!-- .element: width="60%" height="60%" -->

Notes: The following years brought a move from relays to vacuum tubes
to improve speed and reliability. This meant a move to a fully
electronic computer with no mechanical parts.

<hr>

### ENIAC

![ENIAC](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Eniac.jpg/1280px-Eniac.jpg)<!-- .element: width="60%" height="60%" -->

Notes: The move to fully electronic, fully digital, Turing complete
computers allowed for the advent of innovations such as loops and exceptions.

<hr>

### EDSAC

![EDSAC](https://upload.wikimedia.org/wikipedia/commons/2/22/EDSAC_%2819%29.jpg)

Notes: 1948 brought to life the concept of a stored-program computer
with the EDSAC. Zuse hypothesized in 1936 that the instructions or
program a computer would run could be stored in the same memory used
to hold the values used in computation, which the EDSAC realized. This
heralded the birth of Von Neumann architecture.

<hr>

### Second Generation

<hr>

### Metrovick 950

![MetroVick
950](http://worldpowersystems.com/archives/Ivall/Metrovick-transistor-digital-computer.jpg)<!-- .element: width="60%" height="60%" -->

Notes: By 1955 transistors began to replace vacuum tubes, once again
making computers smaller, faster, more reliable, and requiring less energy.

<hr>

### Harwell CADET

![Harwell
CADET](https://upload.wikimedia.org/wikipedia/commons/1/17/HarwellCadetComputer.jpg)

Notes: These improvements meant innovations such as the concept of
firmware for this new concept of stored program computers, as well as
the first interpreted programming language, and the first compiled
programming language.

<hr>

### Software

<hr>

### FORTRAN

![FORTRAN punch
card](https://upload.wikimedia.org/wikipedia/commons/5/58/FortranCardPROJ039.agr.jpg)<!-- .element: width="70%" -->

Notes: 1954 brought the implementation of the first high level general
purpose programming language from John Backus at IBM. FORTRAN could be
implemented to run on many machines, meaning that architecture become
much less important in how computing was approached and cause software
to take off. FORTRAN followed the long standing tradition of being a
purely imperative language.

<hr>

### LISP

![John McCarthy](https://upload.wikimedia.org/wikipedia/commons/thumb/4/49/John_McCarthy_Stanford.jpg/1920px-John_McCarthy_Stanford.jpg)<!-- .element: width="70%" -->

Notes: In 1958 John McCarthy designed LISP at MIT. Originally meant as
a language to express Turing-complete programs in, it was soon after
implemented and was the first language to treat the program's code as
data that could be edited by the program itself, as the program's code
was the stored in the same data structure of nested lists that the
program's data was stored in.

<hr>

### The Fundamental Paradigms

Notes: Now that the world had fast computers that could support any
kind of software and software had become complex enough to support any
representation of state as well as the power to change as it ran,
complexity began to become a problem. What was the right way to
program a computer? What was the best way to think about a problem and
translate that into a program to calculate the things you wanted? Out
of these questions and the late 60s to early 70s, the fundamental
paradigms arose.

<hr>

### C - Procedural

![Ken Thompson and Dennis Ritchie](https://upload.wikimedia.org/wikipedia/commons/4/46/Ken_Thompson_and_Dennis_Ritchie.jpg)

Notes: In 1969 at Bell Labs while attempting to write a universal
operating system that would run on any computer, the need arose for a
systems programming language to write the operating system in. From
this came the C programming language. Like FORTRAN, it was imperative,
but rather than forcing GOTO statements, C divided code into
procedures that could have data passed between them. It was also
statically typed, so data needed to be marked by a type to compile,
but the typing was weak, allowing C to adapt to any platform. The
structure of procedures combined with the safety of type checking
provided the Unix team at Bell Labs assistance in their ability to
reason about something as complex as an operating system that would
run on machines that had not been invented yet.

<hr>

### Prolog - Logic

![Alain
Colmerauer](http://www.fanphobia.net/uploads/actors_3/72958/alain-colmerauer-hd-wallpaper-pic.jpg) <!-- .element: width="70%" -->

Notes: Prolog was developed by Alain Colmerauer and shipped
in 1972. Intended for use in natural language processing, Prolog was
the first logic programming language, which given a set of facts and
rules about the relations between the data in a program, would compute
the answers to queries. Prolog remains the most popular of logic
programming languages today, used in AI such as IBM's Watson as well
as theorum proving and expert systems programming.

<hr>

### ML - Functional

![Robin Milner](https://i.imgur.com/SDUwSXo.jpg)

Notes: ML was the first general purpose functional programming
language, first appearing in 1973. Like C, it was statically typed,
however unlike C, in ML the types were an important part of the data
for what kind of computation were to be executed on data, making it
strongly typed as well. Unlike C's procedures, ML relied on functions
which intended to mimic their use in mathematics. ML is the direct
inspiration for popular languages today such as Haskell, Idris and
F#.

<hr>

### Smalltalk - Object-Oriented

![Alan Kay](https://i.imgur.com/70LdG1p.jpg)

Notes: Developed throughout the early 70s by Alan Kay, Smalltalk
became publicly available in 1980. Smalltalk was the first truly
object oriented programming language, modeling its data as
objects which had actions they could perform, as opposed to functions
which operated on structured data. Unlike other attempts at object
oriented languages before it, every piece of data in Smalltalk was an
object. Objects could hold data, receive messages from other objects,
or in the course of receiving a message, send messages to itself or
others.

<hr>

### Multi-paradigm Languages

Notes: With falling costs of computer hardware and the exploding
prevalence of microcomputers in workplaces and homes, the need for
general purpose programming languages that could solve many problems
at once swelled. Throughout the late 80s and 90s, a surge of
multi-paradigm languages hit the market.

<hr>

* C++ - Procedural, OO, static/weak
* Perl - Procedural, interpreted, dynamic/weak
* Java - Procedural, OO, static/weak
* Javascript - Procedural, functional, dynamic/weak
* Scala - Functional, OO, static/string
* F# - Functional, OO, static/strong
* Clojure - Functional, OO, dynamic/strong
* Kotlin - all the things, static/weak
* Swift - all the things, static/weak

<hr>

### Part 2

## The Purpose of Paradigms

<hr>

### Problems of Early Languages

* Repeated code
* GOTO
* Global state

Notes: In early languages, encoding a problem as a computer program
was significantly different from how we might think of solving the
same problem without a computer. This required very specific
understanding of how the computer and language worked to even approach
encoding a problem to be solved as a computer program. The programmer
was responsible for keeping track things mentally.

<hr>

### Structured Programming

* Code re-use
* Flow control
* Local scope

Notes: All of the advantages structured programming brought allowed
programmers to reduce the mental strain of paying attention to many
varying pieces all at the same time.

<hr>

### The Fundamental Paradigms

* Procedural
* Logic
* Functional
* Object-Oriented

Notes: Each of these paradigms gives programmers a framework to reason
about their program before encoding whatever problem we're trying to
solve as a program. They provide techniques for arranging complexity
to make it easier to reason about.

<hr>

### Abstraction

* Code can be grouped and run many times
* Data can be queried
* Programs work like math problems
* Mimic real-world objects

Notes: A technique for arranging complexity is called an
abstraction. These can be over data via the use of data types or over
control flow via functions, pattern matching, conditionals, loops, etc.

<hr>

### Methods of Abstraction

Notes: Most techniques for managing complexity can be called
abstractions. There are a few concepts that most methods of
abstraction boil down to. We're going to take a look at the most
popular of these.

<hr>

### Encapsulation

``` java
public class Account {
    private BigDecimal balance = new BigDecimal(0);

    public BigDecimal getBalance() {
        return balance;
    }

    public void deposit(Bigdecimal amount) {
        balance = balance.add(amount);
    }
}
```

``` ocaml
datatype account = Account real

fun getBalance (Account b) = b
fun deposit (Account p, b : real) = Account (p + b)
```

Notes: Encapsulation is the practice of restricting access to data to
localize its scope, or to bundle the methods of operating on data
with the data itself.

<hr>

### Encapsulation

``` javascript
function Account () {
  var balance = 0;

  return {
    deposit: function (amount) {
      balance += amount;
    },
    getBalance: function () {
      return balance;
    }
  };
}
```

Notes: Encapsulation intends for programmers to think about the
relationship between their data by what it represents, rather than the
specifics of the language it is written in.

<hr>

### Polymorphism

* `Animal`s make noise
* `Dog`s are Animals
* `Cat`s are Animals

Therefore, `Dog`s and `Cat`s make noise.

Notes: Polymorphism is a method of thinking about acting on data based
on generalizations of its type.

<hr>

### Subtype Polymorphism

``` java
abstract class Animal {
    abstract void makeNoise();
}
class Dog extends Animal {
    public void makeNoise() {
        bark();
    }
}
class Cat extends Animal {
    public void makeNoise() {
        meow();
    }
}
```

<hr>

### Ad-Hoc Polymorphism

``` java
class Owner {
    public void pet(Dog d) {
        say("Good girl!");
        d.makeNoise();
    }
    public void pet(Cat c) {
        say("Who likes snuggles?");
        c.makeNoise();
    }
}
```
Notes: Ad-hoc polymorphism allows methods with the same name to
respond differently based on the type of the data being passed to
them.

<hr>

### Parametric Polymorphism

``` java
ArrayList<String> strings = new ArrayList<String>();
ArrayList<Integer> ints = new ArrayList<Integer>();
ArrayList<Animal> pets = new ArrayList<Animal>();

public <T> T getFirst(ArrayList<T> list) {
    return list.get(0);
}
```

Notes: Parametric polymorphism allows functions to be written to act
uniformly without knowing all of the types they will deal with,
because those types are irrelevant to the functionality.

<hr>

### Composition

Notes: Composition is the practice of combining multiple pieces of
data or functions such that they can be treated as a single piece.

<hr>

### Object Composition

``` java
class CheckboxButton extends Button {
    private Image image;
    private Text title;

    public void onClick() {
        this.image.changeToChecked();
        this.title.italicize();
    }
}
```

Composition

<hr>

### Object Composition

``` java
class Barnyard {
    private ArrayList<Animal> animals;

    public void adopt(Animal a) {
        animals.add(a);
    }
}
```

Aggregation

<hr>

### Function Composition

``` javascript
function deposit(balance, amount) {
    return balance + amount;
}
function display(balance) {
    return "Your new balance is " + balance;
}
function deposityMessage(balance, amount) {
    return display(deposit(balance, amount);
}
```

Composition

<hr>

### Function Composition

``` java
class CallbackQueue implements OnClick {
    private ArrayList<OnClick> callbacks = new ArrayList<>();

    public void addOnClick(OnClick o) {
        callbacks.add(o);
    }

    public void onClick(View v) {
        for(OnClick o : callbacks) {
            o.onClick(v);
        }
    }
```

Aggregation

<hr>

### Inheritance

``` java
class Button {
    private String color = "grey";
    public void draw() { // do a thing }
}
class RedButton extends Button {
    private String color = "red";
}
class BlueButton extends Button {
    private String color = "blue";
}
```

Notes: Not the same as subtype polymorphism even though they use the
same keyword in Java. Inheritance intends to simplify code by allowing
the re-use of existing implementation.

<hr>

### Principles for Abstraction

<hr>

### SOLID

* Single-responsibility principle
* Open-closed principle
* Liskov substitution principle
* Interface segregation principle
* Dependency inversion principle

Notes: A class or typeclass should only do one thing. Entities can be
extended but not modified. Objects should be replaceable with their
subtypes. Interfaces should be as small and diverse as
possible. Program to interfaces, not implementations.

<hr>

### DRY

Don't repeat yourself.

<hr>

### KISS

Keep it stupid simple.

<hr>

### YAGNI

You aren't going to need it.

<hr>

### Design Patterns

* Builder
* Factory
* Singleton
* Decorator

and dozens more...

Notes: Throughout the 1990s, developers began to agree on design
patterns to standardize and inform design of programs with their now
powerful and flexible multi-paradigm languages. These eventually
coalesced into what we now call design patterns.

<hr>

### Design Patterns

[Design Patterns: Elements of Reusable Object-Oriented
Software (Gang of Four)](https://en.wikipedia.org/wiki/Design_Patterns)
[Code Complete](https://en.wikipedia.org/wiki/Code_Complete)

<hr>

Congratulations
---------------

You now know enough about programming paradigms to trick someone
into thinking that you know what the heck you are talking about.
