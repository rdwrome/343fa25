#### remember p5.js?

# [p5.live](https://teddavis.org/p5live/)

### shortcuts
```
CTRL + ENTER	softCompile
CTRL + SHIFT + ENTER	hardCompile
CTRL + E	editor toggle
CTRL + N	new sketch
CTRL + SHIFT + C	clone sketch
CTRL + A	autocompile toggle
CTRL + ,	settings toggle
CTRL + R	references toggle
CTRL + B	chalkboard toggle
CTRL + T	tidy code
CTRL + SPACE	autocomplete
CTRL + +	increase fontsize
CTRL + -	decrease fontsize
CTRL + S	save png [ + code ]
CTRL + 1, 2, 3...0	jump to first 10 sketches
CTRL + SHIFT + ⇡⇣	jump to previous/next sketch
CTRL + SHIFT + DELETE	delete current sketch
```

### sketches
- math with lissajous

```

	function setup() {
		createCanvas(windowWidth, windowHeight)
		background(0)
	}

	function draw() {

		let xSpeed = 2.1 // rate of left-right
		let ySpeed = 1 // rate of up-down
		let sSpeed = 10 // rate of ellipse

		fill(255)
		stroke(255)
		if(frameCount % 2 === 0) {
			stroke(0)
		}
		strokeWeight(5)

		let oscX = sin(frameCount * 0.01 * xSpeed) * height * .4
		let oscY = cos(frameCount * 0.01 * ySpeed) * height * .4
		let s = sin(frameCount * 0.01 * sSpeed) * 150

		translate(width / 2, height / 2)
		ellipse(oscX, oscY, s, s)
	}
```

- math with sine
	
```

	function setup() {
		createCanvas(windowWidth, windowHeight)
		mouseX = width * 0.4
	}

	function draw() {
		background(0)
		let lc = 20
		fill(255)
		for(let i = 0; i < lc; i++) {
			let s = width / lc
			let x = map(i, 0, lc - 1, 0, width)
			let osc = sin((frameCount * .01) + i * map(mouseX, 0, width, 0, 5))
			let y = height / 2 + osc * abs(mouseY - height / 2)
			stroke(255)
			strokeWeight(3.1 - (osc * 3))
			line(x, y, x, 0)
			noStroke()
			ellipse(x, y, s, s)
		}
	}
```
	
- [webgl](https://en.wikipedia.org/wiki/WebGL)
	
```

	let v = .3

	function setup() {
		createCanvas(windowWidth, windowHeight, WEBGL)
		angleMode(DEGREES)
	}

	function draw() {
		background(0)
		orbitControl(5)

		ortho()

		if(mouseIsPressed) {
			lights()
			noStroke()
			fill(255)
		} else {
			stroke(255)
			noFill()
		}


		push()
		translate(rPos(0))
		rotateX(frameCount / 4)
		rotateZ(frameCount / 2)
		plane(150, 150)
		pop()

		push()
		translate(rPos(50))
		rotateX(frameCount / 4)
		rotateZ(frameCount / 2)
		box(150)
		pop()

		push()
		translate(rPos(100))
		rotateX(frameCount / 4)
		rotateY(frameCount / 4)
		sphere(100)
		pop()

		push()
		translate(rPos(150))
		rotateX(frameCount / 4)
		rotateY(frameCount / 4)
		ellipsoid(100, 30)
		pop()

		push()
		translate(rPos(200))
		rotateY(frameCount / 2)
		rotateX(frameCount / 3)
		cone(100, 150)
		pop()

		push()
		translate(rPos(250))
		rotateX(frameCount / 4)
		rotateZ(frameCount / 3)
		torus(100, 50)
		pop()

		push()
		translate(rPos(300))
		rotateY(frameCount / 2)
		rotateZ(frameCount / 4)
		cylinder(100, 100)
		pop()
	}

	function rPos(off) {
		let x = (sin(off + frameCount * v) * width / 3)
		let y = (cos(off + frameCount * v) * height / 3)
		return createVector(x, y)
	}
```
	
```
	
	let lc = 8

	function setup() {
		createCanvas(windowWidth, windowHeight, WEBGL)
		noCursor()
		noStroke()
	}

	function draw() {
		ortho()
		background(0)
		for(let i = 0; i < lc; i++) {
			for(let j = 0; j < lc; j++) {
				let mx = map(i, 0, lc - 1, -width / 2, width / 2)
				let my = map(j, 0, lc - 1, -height / 2, height / 2)

				boxsphere(mx, my)
			}
		}
	}

	function boxsphere(x, y) {
		push()
		translate(x, y)
		let mmx = map(mouseX, 0, width, -width / 2, width / 2)
		let mmy = map(mouseY, 0, height, -height / 2, height / 2)
		let roff = -dist(mmx, mmy, x, y) / 2
		rotateY(radians(frameCount + mouseX))
		rotateX(radians(mouseY))
		let s = (width / lc / 2) + roff

		fill(255)
		if(mouseIsPressed) {
			fill(0)
		}
		box(s)

		fill(0)
		if(mouseIsPressed) {
			fill(255)
		}
		sphere(s * 0.65)
		pop()
	}
```
	
	
- hydra

```

	let libs = ['https://unpkg.com/hydra-synth', 'includes/libs/hydra-synth.js']
	let hydra = new Hydra()
	hydra.setResolution(window.innerWidth*2, window.innerHeight*2) // retina res

	 // sandbox - start

	osc(10, .05, 1.3)
	.kaleid(8)
	.modulateScale(src(o0)
		.scale(1.5)
		.repeat(4, 4)
		.rotate(0, .1)
		.modulate(src(o0).scale(.4))
	)
	.out()

	// sandbox - stop
```

### recoding

### [cocoding](https://teddavis.org/p5live/?cc=z212z)
- The code is synced while the visuals are rendered locally.


## in-class assignment
- working with 1 or 2 others, create a 2 min live 'cocoded' p5.live or hydra in p5.live performance
- chose sound to play while you're doing it!
- performances start at 10:15am
- documentation file due at 11am