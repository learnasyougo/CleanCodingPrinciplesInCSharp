# About
Clean code is the art of writing code that humans can understand. Learn how to write C# in a style that's easy to write, read, and maintain. This course is filled with clear comparisons between "dirty" C# code to avoid, and the "clean" C# equivalent. Check out the course at https://www.pluralsight.com/courses/csharp-clean-coding-principles

# Table of contents
1. [Intro](#intro)
   1. [Code is communication](#codeiscommunication)
   1. [Reasons to care](#reasonstocare)
   1. [We are ahtors](#weareauthors)
1. [Clean Coding Principles](#cleancodingprinciples)
   1. [Three Core Clean Coding Principles](#threeprinciples)

# <a name="intro"></a>Intro
## <a name="codeiscommunication"></a>Code is Communication
> Code is like humor, if you have to explain it, it's bad.
> ~ [Cory House](https://twitter.com/housecor)

> Programming is the art of telling _another human_ what one wants the computer to do.
> ~ Donald Knuth

> Any fool can write code that a computer can understand. Good programmers write code that _humans_ can understand.
> ~ [Martin Fowler](https://twitter.com/martinfowler)

## <a name="reasonstocare"></a>Reasons to Care
1. Reading is harder than writing
1. Technical debt is despressing
1. Laziness (extra care in code up front, so it's easier to adapt/read)
1. Sloppiness equals slowing us down
1. Don't be a verb (aka _this code has been Jimmified_)...

## <a name="weareauthors"></a>We are authors
Each line of code is likely to be read 10 times by another human, so we have to strive to be proper authors, as in fact we are.
Authors are writers of a book, article or text and:
- one who practices writing as a profession (_writing code_)
- one who writes or constructs an electronic document or system (_yes, we make systems)
- an originator or creator of a theory or plan (_we do fall under this category as well_)

An author strive to tell a compelling, clear, story. We have to take this in mind when doing so. 
The tools and conventions of _clean code principles_ help us to achieve this.

# <a name="cleancodingprinciples"></a>Clean Coding Principles
## <a name="threeprinciples"></a>Three Core Clean Coding Principles
1. Right tool for the job. Sometimes the hardest part is selecting the right technology for the job.
1. High signal to noise ratio. Remove noise so the reader can easily extract the intent, intstead of dabbing through the noise.
1. Self-documenting. Comments aren't the key, but expressive code is.

### Picking the right tool for the job
> Let's use _lunatic's favorite tool_ for _everything_.
Not every technology is a good fit for the readibility, the security, the performance, etc... Creatively using the wrong tool isn't something to brag about

*Example*: using regex to validate an e-mail address of standard _RFC822_. 
This is simple not readible, referring to http://ex-parrot.com/~pwd/Mail-RFC822-Address.html. 

### Watch for boundaries
Each technology has a specific purpose, html is for content, css seperates style for the content markup, etc...
Some things to look out for.
- storing html in sql
- html in a js string, or js in html
- inline css styles
- dynamic sql to generate your own sql
- dynamic js made at c#

*Example*:
- bad practice ```var string = @"<script type=""text/javascript"">...</script>"; this.Header.Controls.Add(new LiteralControl("\r\n" + script));```
- good practice
  - put the js inside a seperate js file
  - use C# to load up or inject dynmaic data in the header in a http call.