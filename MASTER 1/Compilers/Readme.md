# Compilers: exam questions

Most questions can be answered in a few words in under a minute, but some might
require one hour of explanation, if explained in detail.  For this last kind of
questions, we do not expect from you a very detailed (e.g. one hour)
explanation, but rather that you provide a 2-minute brief answer, and that we
interact on a few points so that we get an idea of to what extent you do
actually understand the details.

These are examples of questions, so that you are not surprised at the exam.  Be
aware that we may ask you several questions and, in the interactive part, we
might ask more detailed questions that are not in this list, but the idea is
always that we try to evaluate if you understand how things work.  We will not
ask you to write code, or even explain details about code in the slides.

If some part of the project is weaker, we might specifically ask theoretical
questions about that part, so that we get reassured that you master the big
ideas about that part.

We refer to slide numbers, but notice that some questions are not understandable
if you do not understand what precedes.  So most of the material in the slides
has to be **understood** (but not memorized).  We will forgive that you do not
**remember** some things, but not that you do not understand what you are
talking about: it is not useful to memorize the answers to those questions. 
Your time is best used understanding the questions and find out the answer by
yourself, so that you get a deep understanding of the material.  If you are
unsure about the answer of a question, post the question and your answer in the
forum, and we will comment, and it will help everybody.  By the way, you do have
**access to your slides** to answer the questions during the exam, and you will
have a bit of time (in minutes) to think: again, one further reason not to
memorize, and use the available time to work on this course to understand the
questions and their answers.

## Generalities

- [What is bootstrapping? (Slide 1-5)](Questions/Q1/Q1.1.md)
- [How do you compare compiling and interpreting? (Slides 1-6, 1-7)](Questions/Q1/Q1.2.md)
- [What is a linker, and what is its purpose? (Slide 1-8)](Questions/Q1/Q1.3.md)
- [Why do we use an intermediate representation in compilers? (Slides 1-10, 1-11, 5-6)](Questions/Q1/Q1.4.md)
- [What are the various stages of a typical compiler?  Shortly describe their purpose. (Slide 1-12)](Questions/Q1/Q1.5.md)

## Lexical analysis 

- [How is lexical analysis performed efficiently?  Assume you have a  certain amount of regular expressions describing tokens: how do you  generate a lexer?](Questions/Q2/Q2.1.md)
- [Describe the steps to transform a regular expression into an  non-deterministic finite automaton. (See slides 2-20, 2-21)](Questions/Q2/Q2.2.md)
- [How to use for a lexer a non-deterministic finite automaton  representing a language? (Slides 2-22 -- 2-31)](Questions/Q2/Q2.3.md)
- [Why transform a non-deterministic finite automaton into a  deterministic one, in the context of lexical analysis? (Slides 2-34 -- 2.40)](Questions/Q2/Q2.4.md)
- [How to use for a lexer a deterministic finite automaton representing a  language? (Slides 2-36 -- 2-37)](Questions/Q2/Q2.5.md)
- [Explain how lexical analysis should be tweaked to handle languages  where blocks are indentation based. (Slide 2-43)](Questions/Q2/Q2.6.md)

## Syntax analysis

- Why not merge lexical analysis into syntactical analysis (describing
  the grammar to a sub-token level)? (Slide 1-19, 2-7)
- Assuming we know what a grammar is, what is the particularity of a
  regular grammar?  A context-free grammar? (Slide 3-12)
- What are the Chomsky's types for context-free grammars and regular
  grammars?  What does it mean for a grammar to have a small/large
  Chomsky's type w.r.t. automation and expressivity?  Where are, in the
  Chomsky's hierarchy, the languages that can be decided (i.e. such that
  there is program that always terminates and decides whether some text
  belongs to the language or not). (Slide 3-12)
- Give an example of a language that can be represented by a
  context-free grammar and not a regular one.  (Slide 3-13)
- What is a left-most/right-most derivation of a context-free grammar?
  (Slide 3-15)
- Are there words that only have left-most derivations? (Slide 3-15)
- How could you describe the purpose of syntax analysis, w.r.t. the
  parse tree of a sequence of tokens?  (Slide 3-16)
- Is the parse tree unique?  How do you call a grammar such that parse
  trees are unique?  Should we enforce working only with such grammars?
  (Slides 3-18 -- 3-20, 3-125)
- Could you provide an example of an ambiguous grammar? (Slide 3-18, or
  3-21, or many other possibilities)
- What is left/right-associativity of an operator? (Slide 3-22)  Why is
  it useful to consider an associative operator to be only left or right
  associative? (Slide 3-23)
- What parsing problem (called dangling else) is linked to parsing of
  if-then(-else), and how to solve it?  (Slides 3-25, 3-26, 3-58)
- Could you cite a few examples of things that are commonly used in
  programming languages but that are not captured by context-free
  grammars? (Slide 3-28)  How is this typically solved?  Why not simply
  go for more expressive grammars?
- Why are left-recursive grammars a problem with top-down parsers. How
  can this be solved, when the grammar is left-recursive because of
  associative symbols?  (Slides 3-37, 3-55, 3-56)
- What is an LL(1) grammar?  (Slide 3-39)  How does this relates to
  top-down parsing? (See 3-42 and following)
- Describe in your own words what `Nullable(alpha)`, `First(alpha)` and
  `Follow(A)` are, where `alpha` is a sequence of symbols, and `A` a
  non-terminal.  (Slide 3-44)  How can this help to build a top-down
  parser?  (Slide 3-46, 3-47)
- Sometimes, several rules might have the same prefix, which is
  typically a problem for top-down parsing, to decide which rule
  applies.  Could you explain a possible solution? (Slide 3-58)
- Explain in a few sentences and in your own words how a bottom-up
  shift-reduce parser works.  (Slides 3-66 -- 3-80)
- What is the configuration of an LR parser?  (Slide 3-84)
- Given a configuration of an LR parser, what information give the
  `Action` and `Goto` tables? (Slides 3-85, 3-86, see also examples
  slides 3-87, 3-88)
- I will not ask questions on the inner workings of an SLR parser and
  the building of the SLR table. (Slides 3-91 -- 3-103)
- I will not ask questions on slide 3-104.
- I will not ask questions on weak precedence parsers. (3.107 -- 3-124)
- But I assume you can explain how to remove an epsilon rule from a grammar
  (Slide 3-122), how to fix ambiguous grammars with precedence rules
  (Slide 3-125) and all practicalities at the end of the chapter about Syntax
  analysis.  If the subject comes up, I might ask easy questions, but I
  will not particularly target this.

## Semantic analysis

- Why is semantic analysis required?  That is, why all this is not
  captured in the syntax analysis? (See e.g. slide 3-28, 4-5)
- What is a syntax-directed definition? (Slide 4-8)  Could you provide
  an easy example? (See for instance slide 4-9: the SDD gives clear
  rules to compute the numbers of a's and c's)
- What is a synthesized/inherited attribute?  (Slide 4-10)  Provide an
  example.  (Slide 4-11 for synthesized attribute, an example of
  inherited attribute is the symbol table with types in a type checker
  for the expressions)
- In the context of syntax-directed definitions, where you have both
  synthesized and inherited attributes, what kind of problems could you
  face (solution: dependency cycles), and how to solve that? (solution:
  for instance only synthesized attributes, or L-attributed grammar,
  where attributes can be computed by a Euler-tour traversal, or in
  general, make sure a topological order exists) (Slides 4-13 -- 4-15)
- In what respect does the abstract syntax tree differ from the parse
  tree?  Could you give an example?  (Slide 4-29)
- What does *syntactic sugar* means?  What shall we do with it in the
  compiler and why? (Slide 4-32)
- What is scope checking and type checking? (Slide 4-34)
- I will not ask questions on technicalities of scope and type checking.
  (Slides 4-35 -- 4-57)

## Intermediate representation

- What is static single-assignment form (SSA)?  Can any program be
  transformed into SSA? (Slides 5-10 -- 5-13)
- I will not ask questions on continuation-passing style (Slides
  5-14 -- 5-16)
- I assume that the translation into intermediate language is understood
  from the project, but be ready to answer questions about this on the
  project.
- What is dead code elimination? (Slide 5-45)

## Code generation

- I will not ask details about the various architectures. (Slides
  6-6 -- 6-20)
- I assume your understand how instruction selection could work (Slides
  6-22 -- 6-30) but I will not ask specific questions on this.
- What is the problem with register allocation and translation of
  intermediate language into assembly?  (Slide 6-32)
- Could you provide a naive, yet working, way to circumvent the problem
  of scarce registers when translating intermediate language into
  assembly? (Slides 6-34 -- 6-35)
- How is register allocation (when translating intermediate language
  into assembly) related to graph colouring?  (understand the high level
  idea of slides 6-36 -- 6-45)
- Describe in a few words Chaitin's algorithm for graph colouring.
  (Slides 6-46 -- 6-49)
- What are the heap and the stack?  Where do global variables go? What
  about local variables for a function, or an array of integer allocated
  using malloc? (Slides 6-53 -- 6-56)
- How can garbage collection be implemented with reference counting?
  (Slide 6-63 -- 6-65)
- Explain briefly the idea behind tracing garbage collectors.
  (Slide 6-66 -- 6-68)