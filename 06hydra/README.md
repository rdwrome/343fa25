### Accessibility
- Don't give someone a seizure
- Let your musicians see the screen

# [video synth basics](https://hydra.ojack.xyz/docs/docs/learning/video-synth-basics/)

# [functions](https://hydra.ojack.xyz/functions)
- arguments
- chained functions like minitidal in strudel

## sources
	- osc
	- solid ([alpha](https://en.wikipedia.org/wiki/Alpha_compositing))
	- shape
	- [noise](https://en.wikipedia.org/wiki/Perlin_noise)
	- [voronoi](https://en.wikipedia.org/wiki/Voronoi_diagram)
	- [gradient](https://en.wikipedia.org/wiki/Gradient)
	- src
	- out

# [Examples](https://hydra.ojack.xyz)
- roll through examples
- change parameters
- show and tell
- code reuse!

## synth settings
	- render
	- update
	- setResolution
	- hush
	- setFunction
	- speed
	- bpm
	- width
	- height
	- time
	- mouse

## geometry
	- rotate
	- scale
	- pixelate
	- repeat
	- repeatX
	- repeatY
	- kaleid
	- scroll
	- scrollX
	- scrollY
		
## color
	- color
		- r,g,b,a
	- saturate
		- how intense color is
	- hue
		- base color
	- colorama
		- remaps greyscale to colorscale
	- invert
	- contrast
	- [posterize](https://en.wikipedia.org/wiki/Posterization)
	- [shift](https://en.wikipedia.org/wiki/Visible_light_communication#Color_Shift_Keying)
	- [brightness](https://en.wikipedia.org/wiki/Brightness)
	- [luma](https://en.wikipedia.org/wiki/Luma_(video))
		- cuts off pixels with intensity less than the threshold parameter
	- thresh
		- luma but 'color of the bright part of the image is preserved'

## eternal sources
	- initCam
	- initImage
	- initVideo
	- init
	- initStream
	- initScreen
	
## blend
	- add
	- sub
	- layer
	- blend
	- mult
	- diff
	- mask
		- like a stencil
		```javascript
		osc(10,0,1).hue(0.5).layer(osc(10,0,1).mask(shape(4,0.5,0.001))).out()
		```
	
## modulate
	- modulate
	- modulateRepeat
	- modulateRepeatX
	- modulateRepeatY
	- modulateKaleid
	- modulateScrollX
	- modulateScrollY
	- modulateScale
	- modulatePixelate
	- modulateRotate
	- modulateHue

# [advanced tutorial](https://hydra-book.glitches.me/#/)

# [minitidal + hydra in strudel](https://strudel.cc/learn/hydra/)

## [so you don't want to show your code...](https://www.youtube.com/watch?v=b9VS7Q86T-Y&list=PL82ekYXUXbcSDipIPs6Df1YpG6s68WJRu&index=13&t=2s)