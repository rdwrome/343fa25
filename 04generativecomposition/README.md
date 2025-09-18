## TODO RECORDING

## [sophisticated pattern transformations](https://strudel.cc/workshop/pattern-effects/)


- fast, slow

- degradeBy

`s("hh*8").degradeBy(0.2)`

- struct

`note("c,eb,g")
  .struct("x ~ x ~ ~ x ~ x ~ ~ ~ x ~ x ~ ~")
  .slow(2)`

- mask

`note("c [eb,g] d [eb,g]").mask("<1 [0 1]>")`

- palindrome

`note("c d e g").palindrome()`

## sophisticated rhythms

- linger

`s("lt ht mt cp, [hh oh]*2").linger("<1 .5 .25 .125>")`
	
### what are euclidean rhythms?
-- poly meter? poly rhythm?...euclidean rhythm?
-- https://www.youtube.com/watch?v=bKazVnHh2w4 (@1:55)

- euclid

`note("c3").euclid(3,8)`

## [Yes, you may have your own samples & sampler effects](https://strudel.cc/learn/samples/#loading-custom-samples)


## [Signal Modifiers](https://strudel.cc/learn/signals/)

## ["Random" Modifiers](https://strudel.cc/learn/random-modifiers/)

## [Conditional Modifiers](https://strudel.cc/learn/conditional-modifiers/)

## [Accumulation](https://strudel.cc/learn/accumulation/)

## [Pitch Functions](https://strudel.cc/learn/tonal/)

## ["Experimental Step-wise Patterning"](https://strudel.cc/learn/stepwise/)

### Small assignment for next week! Create a 2 min livecoding set using ONLY ONE SAMPLE. Documentation due as always.