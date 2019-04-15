# Elm Web GL Experiments

I am experimenting with WebGL in Elm and thought I would collect anything useful that comes out in this repo. This code is intended to be more a learning resource than a code resource. I have no prior experience in WebGL and would have liked more basic examples done in Elm than what is currently available.

## Landscape
- Generates landscape/terrain geometry using a noise function.
- A "player" can be moved across landscape using arrow keys.
- Has shader with directional lighting.
- Rotate "scene" using mouse drag

### Try it
https://mika.xyz/elm-webgl-experiments/landscape.html

### Notes
- Landscape.Generator returns vertices with normals needed for lighting in the shader. There seems to be MANY ways to calculate normals for a mesh. The simple one used here is sufficient for geometry that "points in one direction" and does not curve into itself.
- Landscape geometry generated is the simplest possible: quads triangulated in order. I understand some other pattern ([Diamond-square](https://en.wikipedia.org/wiki/Diamond-square_algorithm)) would be more optimal.
- Lighting is done in vertex shader. One is supposed to get better results calculating lighting in fragment shader...
- Noise function is a quick implementation of [Perlin Noise](https://en.wikipedia.org/wiki/Perlin_noise). Not sure it is at all "correct" but it seems to do its job.
- Keyboard.elm handles keyboard input. It is not in a production state in any way. :)

### Build
    yarn/npm install
    yarn/npm run landscape
    
Browse dist/landscape.html
