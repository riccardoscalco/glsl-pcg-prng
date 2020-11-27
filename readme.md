# glsl-pcg-prng

PCG random number generators ported to an NPM package, so that you can require it from glslify.

The code is based (mostly copied) from https://www.shadertoy.com/view/XlGcRh by Mark Jarzynski.

References:

* Mark Jarzynski and Marc Olano, Hash Functions for GPU Rendering, Journal of
  Computer Graphics Techniques (JCGT), vol. 9, no. 3, 21-38, 2020
  Available online http://jcgt.org/published/0009/03/02/

* https://www.pcg-random.org/

## Install

```sh
npm install glsl-pcg-prng
```

## Usage

Note that **glsl-pcg-prng** needs OpenGL ES 3.0 (WebGL 2.0).

```glsl
#pragma glslify: prng = require(glsl-pcg-prng)

// Create a seed
vec4 seed = vec3(1000., 2000., 3000., 4000.);

// Return one random number, it takes a float or a vec2 as input
float r1 = prng(seed.x);
float r2 = prng(seed.xy);

// Return three random numbers
vec3 r3 = prng(seed.xyz);

// Return four random numbers
vec4 r4 = prng(seed.xyzw);
```
