# KFilter

Tiny SuperCollider quark that adds a nodeproxy role for \kfilter

### Installation

In SuperCollider, evaluate the following code to install it as a quark:
`Quarks.install("https://github.com/madskjeldgaard/KFilter.git");`

### Usage

```
Ndef('hej', {|f=110, w=0.5| VarSaw.ar(f, 0, w) * 0.1})
Ndef('hej')[1] = \kfilter -> {|in, pitch| PitchShift.ar(in,0.2,pitch)}; // The pitch arg becomes pitch1
Ndef('hej')[2] = \kfilter -> {|in, pitch| PitchShift.ar(in,0.2,pitch)}; // The pitch arg becomes pitch2
Ndef('hej').play
Ndef('hej').gui
```
