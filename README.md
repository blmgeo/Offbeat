## Introduction  
Offbeat is a new format for music composition. Rather than staves, tabs, GUIs, or APIs to represent music, only the pitch and duration of notes are needed. This yields a data-like structure for any composition. Combined with techniques from machine learning, it is then possible to generate music categorically, e.g. genre, popularity, etc. And that is the aspiration of Offbeat, to be an intelligent tool for music generation and analysis.

The documentation below explains how it works.

### Note duration
A note's duration is the relative amount of time it is played, known as a subdivision. 
The names of common subdivisions are abbreviated as follows:

* ts = thirty-second  
* s = sixteenth  
* s-dot = dotted-sixteenth  
* t = triplet  
* e = eighth  
* e-dot = dotted-eighth    
* q = quarter  
* q-dot = dotted-quarter  
* h = half  
* h-dot = dotted-half   
* w = whole
* w-dot = dotted-whole   

_Note: 3 triplets = 2 eighths_

### Note pitch
A note's pitch is the name for its frequency in Hertz. D in the 5th octave is written as `d5`. Similarly, G-flat in the 3rd octave is `g_3`, and C-sharp in the 6th octave is `c#6`. A pitch can be between `a0` and `g#7`, inclusive.

### Putting duration and pitch together
General format: `[note_duration][space][note_pitch][comma]`   
In practice: `h d5, q g_3, q c#6` etc.

_Note: any amount of tabs, newlines, or whitespace can appear after the comma, but not between the duration and pitch_  

## Usage  
1) Import:
~~~
const Offbeat = require('Offbeat')
~~~
2) Pass in a melody object:  
~~~
const melody = new Offbeat({  
   tempo: 128,                                            //default is 60
   instrument: 'square',                                  //default is 'sine'
   timeSig: '3/4',                                        //default is '4/4'
   notes: 't d4, t d_4, t d4, q a#5, q b5, q rest, w e4', //default is an empty string
   loop: true                                             //default is false  
})
~~~
_Note: Up to six audio contexts can be active on the window object. Each instance of Offbeat creates a new context._

3) Read the rest of the documentation here: https://blmgeo.github.io/Offbeat/out/Offbeat.html


