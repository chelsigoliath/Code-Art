
[Canvas-Sketch Documentation](#canvas-sketch)

- [Quick Start](#quick-start)
- [Canvas-Sketch Example](#code-example)



![Blocks in black](finalProjectRenders/low/unit2Fundamentals1.jpg)
![Blocks in neumorphism style](finalProjectRenders/low/unit2Fundamentals2.png)


![Randomized circles in different styles](finalProjectRenders/low/unit3SketchTransform1.jpg)
![Circles in neumorphism style](finalProjectRenders/low/unit3SketchTransform2.jpg)



![Randomized dots connected by rules](finalProjectRenders/low/unit4SketchAgents1.jpg)
![Randomized dots connected by rules in different styles](finalProjectRenders/low/unit4SketchAgents2.png)



![Dashes following random wave](finalProjectRenders/low/unit5SketchNoise.jpg)



| ![Abaporu by Tarsila do Amaral](finalProjectRenders/low/unit6SketchTypeAvatarAbaporuTarsilaDoAmaral.jpg) | ![Meisje Met de Parel by Johannes Vermeer](finalProjectRenders/low/unit6SketchTypeMeisjeMetDeParelJohannesVermeer.jpg) |
| ------------- | ------------- |

| ![Avatar from Github](finalProjectRenders/low/unit6SketchTypeAvatar.jpg) | ![Avatar from Linkedin](finalProjectRenders/low/unit6SketchTypeLinkedin.jpg) | ![Old avatar](finalProjectRenders/low/unit6SketchTypeOldAvatar.jpg) |
| ------------- | ------------- | ------------- |

[Course of Creative Coding with Javascript by Bruno Imbrizi on Domestika.](https://www.domestika.org/pt/courses/2729-programacao-criativa-produza-pecas-visuais-com-javascript)



`canvas-sketch` is a loose collection of tools, modules and resources for creating generative art in JavaScript and the browser.

<!-- - :sparkles: Website (not yet public) -->

- :closed_book: [Documentation](https://github.com/mattdesl/canvas-sketch/blob/master/docs/README.md)

- :wrench: [Examples](https://github.com/mattdesl/canvas-sketch/blob/master/examples)

#

<p align="center">
  <sub>example of <code>canvas-sketch</code> running in Chrome</sub>
</p>

<p align="center">
  <sub>↓</sub>
</p>

<p align="center">
  <img src="https://github.com/mattdesl/canvas-sketch/raw/master/docs/assets/images/chrome-example.png" width="50%" />
</p>

### Quick Start

To jump directly into `canvas-sketch`, try the following terminal commands with `node@8.x` and `npm@5.x` or newer.

```sh
# Install the CLI tool globally
npm install canvas-sketch-cli -g

# Scaffold a new 'sketch.js' file and open the browser
canvas-sketch sketch.js --new --open

# Start a project
canvas-sketch sketch.js --open
```

Some other commands to try:

```sh
# Start the tool on an existing file and change PNG export folder
canvas-sketch src/foobar.js --output=./tmp/

# Start a new sketch from the Three.js template
canvas-sketch --new --template=three --open

# Build your sketch to a sharable HTML + JS website
canvas-sketch src/foobar.js --build

# Develop with "Hot Reloading" instead of full page reload
canvas-sketch src/foobar.js --hot
```

For more features and details, see the [Documentation](https://github.com/mattdesl/canvas-sketch/blob/master/docs/README.md).

### Code Example


```js
const canvasSketch = require('canvas-sketch');

// Sketch parameters
const settings = {
  dimensions: 'a4',
  pixelsPerInch: 300,
  units: 'in'
};

// Artwork function
const sketch = () => {
  return ({ context, width, height }) => {
    // Margin in inches
    const margin = 1 / 4;

    // Off-white background
    context.fillStyle = 'hsl(0, 0%, 98%)';
    context.fillRect(0, 0, width, height);

    // Gradient foreground
    const fill = context.createLinearGradient(0, 0, width, height);
    fill.addColorStop(0, 'cyan');
    fill.addColorStop(1, 'orange');

    // Fill rectangle
    context.fillStyle = fill;
    context.fillRect(margin, margin, width - margin * 2, height - margin * 2);
  };
};

// Start the sketch
canvasSketch(sketch, settings);
```

Resulting image looks something like this:
<p align="center">
<img src="https://github.com/mattdesl/canvas-sketch/raw/master/docs/assets/images/gradient.png" width="50%" /><br>
<sup>Note: The above PNG file has been scaled/optimized for web.</sup>
</p>
