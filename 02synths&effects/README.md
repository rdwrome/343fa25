## percussion patches!

## samples vs [synths](https://strudel.cc/learn/synths/)

### n vs note
- With Samples: n means iNdex, so it was which sample from the index you wanted to play
- With Samples: note means: take this one sample but slow/speed it up to pitch it down and up and play the pitches as notes
- With Synths: note and n can mean the same thing, but you still can't mix them within a single expression BUT pitch names == scale degree and ARE interchangeable, e.g.
`note ("0 2 e 6 0 b 6 8")`

## [noted](https://strudel.cc/workshop/first-notes/)

- define by pitch name

`note ("c3").sound("sawtooth")`

- sequence away

`note ("c2 d3 e2").sound("sawtooth")`

- sequence over multiple cycles

`note ("[c3 d3 e3]/4").sound("sawtooth")`

- play one per cycle

`note ("c2 <c 3d e2> e3").sound("sawtooth")`

- scale (use `n`)

`n("0 2 4 6 4 2").scale("C:major").sound("sawtooth")`

- elongate
`n("[4@2 3] [5@2 4] [6@2 5]")
.scale("C:ritusen")
.s("sine")`

- scale with rand.range and segment
`n(rand.range(0,12).segment(8))
.scale("C:major")
.s("sine")`

- patterns in parallel with orbit
`$: s("bd sd")
$: note("c eb g")`

**everybody now!**

## share a synth sequence

## [effects](https://strudel.cc/learn/effects/)

- pan

`s("bd").pan("<.5 1 .5 0>")`

- crush

`s("<bd sd>,hh*3").fast(2).crush("<16 8 7 6 5 4 3 2>")`

- vowel

`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>").vowel("<a e i o u>")`

- gain, lpf/hpf, room
`
// @title dash on the train @by todepond [rdwr edit]

$: note("[C G], <D Fb B C A>*[0.5,2]")
  // .rev()
  .sound("sawtooth").cpm(30).gain(.4)
.lpf("<100 200 300 400 500 600 700 800 900 1000 1100 1200 1300 1400 1300 1200 1100 1000 900 800 700 600 500 400 300 200>/4")
  .room(1)
  // .jux(pan)
  .pan("<0 1>/2")  
.delay(1)
.roomsize("10")

__$: note("F")
  .sound("piano").cpm(30)
  .lpf(800)
  
.slow(".1275").gain(.8)`

## livecoding evaluation!
`
_$: n("[0 .. 8]!8/9").scale("C:minor:pentatonic")

// command-/
//$: s("bd!4").bank('RolandTR909')

.hush()
`
`
// "Polish cow song" @by Rogolop
// "Gdzie jest biały węgorz ? (Zejście)" by Cypis
// Abridged

setcpm(120)
// DRUMS
$: sound("<bd sd>").bank("RolandTR909").gain("0.3")
// VIOLIN
$: n(`< -!16
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2 
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
[7 -]*2!4    [4 -]*2!4    [3 -]*2!4    [3 -]*2!2 -!2
>`).scale("A:minor").transpose("<[8P 0]>").sound("gm_violin:6").room(0.5).gain("3")
.velocity(`< .9 .7 .4 .2    .9 .7 .4 .2    .9 .7 .4 .2    .2 .2 .2 .2 >`)
// BASS
$: n(`< -!15 [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
7 - - [- 2]    [4 4] [4 -] - [- -2]    [3 3] [3 3] - -    - - - [- 4]
>`).scale("A:minor").transpose("<-15P>").sound("gm_fretless_bass").decay(0.3).room(0.2).gain("3")
// INTRO
$: n(`<
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!32
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!32
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!32
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
>`).scale("A:minor").sound("gm_accordion:1").decay(0.5).room(0.3).gain("3").pan("0.4")
// CHORUS
$: n(`< -!31 [4 4]
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!31 [4 4]
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!31 [4 4]
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
-!31 [4 4]
[7 7] [4 4] 2 [- 4]    [- 4] [4 -] [4 -] [- 3]    [- 3] [3 -] [3 -] [- 4]    [7 7] [4 4] 2 4
[7 7] [4 4] 2 [2 2]    [4 4] [4 4] [- 4] [- 4]    [3 3] [3 3] [3 -] [- 4]    [7 7] [4 4] 2 4
>`).scale("A:minor").transpose("-8P").sound("gm_bassoon:0").decay(0.5).room(0.3).gain("3").pan(0.6)
// VERSE
$: n(`< -!32 -!32
[6 6] [[6 4] -] [[6 6] 6] [6 4]    [6 6] [6 6] [6# 6] [5 4]    [6 6#] [4 -] [6 6] [6# 4]    [- 6] [6 6] [7 6] [5 4]
[6 6]!4    [6 6] [[6 7] -] [7 6] [7 4]    [- 6] - [6 6] [7 4]    [- 9] [8 7] [6 6] [7 4]
-!32
[6 6] [[6 4] -] [[6 6] 6] [6 4]    [6 6] [6 6] [6# 6] [5 4]    [6 6#] [4 -] [6 6] [6# 4]    [- 6] [6 6] [7 6] [5 4]
[6 6]!4    [6 6] [[6 7] -] [7 6] [7 4]    [- 6] - [6 6] [7 4]    [- 9] [8 7] [6 6] [7 4]
-!32
[6 6] [[6 4] -] [[6 6] 6] [6 4]    [6 6] [6 6] [6# 6] [5 4]    [6 6#] [4 -] [6 6] [6# 4]    [- 6] [6 6] [7 6] [5 4]
[6 6]!4    [6 6] [[6 7] -] [7 6] [7 4]    [- 6] - [6 6] [7 4]    [- 9] [8 7] [6 6] [7 4]
-!32
>`).scale("A:minor").transpose("-8P").sound("gm_synth_bass_2:0").room(0.3)
  .gain("2.5").pan(0.5)
`

## [sophisticated pattern transformations](https://strudel.cc/workshop/pattern-effects/)

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

## Research Presentation Due Next Week!
**Research Presentation**
- 7 min. presentation on a SPECIFIC livecoding artist, topic or project of your choice (with instructor preapproval!!!)
- Be SPECIFIC! one artist, one coding language/tool, one city's algorave scene, one technique, analysis of one particular work
  - can't be Hydra, SuperCollider, Strudel, TidalCyles, miniTidal
- Documentation for submission: .md bibliography using [MLA format](https://owl.purdue.edu/owl/research_and_citation/mla_style/mla_formatting_and_style_guide/mla_general_format.html).