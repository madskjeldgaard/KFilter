# KFilter

Tiny SuperCollider quark that adds a nodeproxy role for \kfilter

### Installation

In SuperCollider, evaluate the following code to install it as a quark:
`Quarks.install("https://github.com/madskjeldgaard/KFilter.git");`

### Usage

```
// Simple synth
Ndef('hej', {|f=110, w=0.5| VarSaw.ar(f, 0, w) * 0.1})

// Make a filter function
f = {|in, pitch| PitchShift.ar(in,0.2,pitch)};

// Add the filter function once: The pitch arg becomes pitch1
Ndef('hej')[1] = \kfilter ->  f;
// Add the filter function again: The pitch arg becomes pitch2
Ndef('hej')[2] = \kfilter -> f;
// Add the filter function a third time: The pitch arg becomes pitch3
Ndef('hej')[3] = \kfilter -> f;

// Listen
Ndef('hej').play

// See in the gui version
Ndef('hej').gui
```
