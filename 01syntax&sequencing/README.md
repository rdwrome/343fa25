### Headphones?

### Reading?

## Strudel is a javaScript wrapper for mini-[TidalCycles](https://tidalcycles.org/) and Hydra
- [Everything is pattern-based](https://tidalcycles.org/docs/reference/cycles)
	- can be unexpected from a conductor's perspective...
- Uses javaScript in the browser (so you don't have to download anything!)
- TidalCycles is a Haskell wrapper for SuperCollider, FYI

## mini-tidal starter pattern commands and [syntax](https://strudel.cc/learn/code/#functions-arguments-and-chaining)
- functions
- parameters/arguments
- chained functions

`s` = sound

`" "` = what to fit inside one cycle

`~` = silence

`!` = repeat

`\\` = comment

**starter examples**

`s ("bd")`

`s ("bd hh")`

`s ("bd ~ hh")`

`s ("bd ~ hh!2")`

**everybody now!**

## [Strudel Tour](https://strudel.cc/)
- console
- reference
- sounds
- (but we'll use `bd hh ho sd cp rim` for now!)

## more advanced mini-tidal commands and [cycles](https://strudel.cc/understand/cycles/)

`?` = randomly silence

`[]` = nest these within one pulse of the cycle

`[ | ]` = randomly choose sample from this array per cycle

`"< >"` = chose the next one from this list per cycle

`,` = layer these atop one another within one cycle

**more examples**

`s ("hh!16?")`

`s "(bd ~ [hh!2]")`

`s ("[bd | hh | sd]!4")`

`s ("<bd hh sd>!4")`

`s ("bd, ~ hh")`

**everybody now!**

## [Sample Selection with Banks](https://strudel.cc/workshop/first-sounds/)

## [CPM/BPM](https://strudel.cc/workshop/first-sounds/)

### Small assignment for next week! Percussion Patch
- Make a mini-tidal percussion patch (only using `bd hh ho sn cp rim`) you're proud of.
- This week and ALWAYS! Document your work in a .md file as outlined in syllabus (what you did, how you did it, creative process, technical process, etc. Can be stream of consciousness but should more or less be in complete sentences).
- Submit percussion patch and documentation in a single .md file (with the mini-tidal code embedded as below) and hand in via GitHub.com + Canvas as outlined in syllabus.

### Good people, do we remember markdown?
- and how to format embedded code within it? Take a look at *this* .md file

```javascript

/* man in finance @by v10101a 
+ "das ist bass" @by enelg,froos
*/

samples({
  finance:  ['man-in-finance/finance_00.wav', 'man-in-finance/finance_01.wav', 'man-in-finance/finance_02.wav', 'man-in-finance/murrayhill.wav']
}, 'github:sandpills/v10101a-samples/main/');


$: n("<1 0>").s("finance").slow(2).clip(1)
  .mask("<1 1 1 0>/4")
  ._punchcard()

$: n("0").s("finance").slow(2).clip(1.4)
  .struct("1(<3 5>,8)")
  .mask("<0 0 0 1>/4").gain(0.8).room(1.2)
  ._punchcard()

$: note("<a1 c2>/2")
.sound("supersaw")
.euclidLegato(9,16)
.ftype('24db')
.lpf(tri.rangex(2000,400).slow(8))
.lpenv(6)
.dist("2:.4")
.echo(2, 1/16, .7)
.mul(gain("[.5 1!3]*4")) //side chain
.add(note("<[0 5]*4 [5 10]*4>"))
._pianoroll()
// .hush()

$: s("oh*16")
  .bank("RolandTR909")
  .decay(sine.range(.2,.4))
  .dist("1:.3")
  .mul(gain("[<0!3 1> .2 1 <0!3 .2>]*4")) //groove
  .mul(gain("[.2 1!3]*4")) //side chain
  .pan(tri.range(.7,.3))
  .hpf(800)
  .room(.1)
  .mask("<0 1>/8")
 ._punchcard()
  // .hush()

$: s("bd*4").bank('RolandTR909').dist("1:1")
.scope()


//babyshark a la mehetabel


const seed = slider(12,0,12,1)

// samples('github:tidalcycles/dirt-samples');

// $: n(irand(26)).struct("x")
// .s("alphabet")
// .room("[0|.2|.4]")
// .gain("1.2")

$: s ("bd!4").bank('mc303')

_$: s("hh!16?").bank('mc303')

_$: s("cp(3,8)").bank('mc303')

$: n ("33 2 1 3 6 9")
  //.degradeBy(0.3)
  .ribbon(seed,1)
  .s("supersaw")
  .scale("f:major")._pianoroll()

$: n ("25 1 2 3")
  //.degradeBy(0.1)
  .ribbon(seed,1)
  .s("supersaw")
  .scale("c:major")
._pianoroll()
  
$: note ("g3 a3 [c4 c4] [c4 [c4 c4][~ c4]]")
  .sound("gm_electric_bass_finger")
  .shape("[0|.2|.4]")
  .gain("2")
  .mask("<1 0 0 0>")._pianoroll()

$: note ("[c4 ~ [c4 c4] c4]!3")
 .sound("gm_electric_bass_finger")
  .shape("[0|.2|.4]")
  .gain("2")
  .mask("<0 1 1 0>")._pianoroll()

$: note ("c4 c4 b3 ~")
  .sound("gm_electric_bass_finger")
  .shape("[0|.2|.4]")
  .gain("2")
  .mask("<0 0 0 1>")._pianoroll()
	  
```