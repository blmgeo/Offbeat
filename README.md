# Offbeat
Create melodies quickly with the Web Audio API. Try it here: https://blmgeo.github.io/Offbeat/

## Introduction  
### Note duration
A note's duration is the relative amount of time it is played, known as a subdivision. 
The names of common subdivisions are abbreviated in Offbeat as follows:

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
In Offbeat, D natural in the 5th octave is written as `d5`. Similarly, G-flat in the 3rd octave is `g_3`, 
and C-sharp in the 6th octave is `c#6`. A pitch can be between `a0` and `g#7`, inclusive.

### Putting duration and pitch together
General format: `[note_duration][space][note_pitch][comma]`   
In practice: `h d5, q g_3, q c#6` etc.

_Note: any amount of tabs, newlines, or whitespace can appear after the comma, but not between the duration and pitch_  

## Usage  
1) Import the Offbeat library:
~~~
const Offbeat = require('Offbeat')
~~~
2) Create a melody object:  
~~~
const melody = {  
   tempo: 128,                                            //optional; default is 60
   instrument: 'square',                                  //optional; default is 'sine'
   timeSig: '3/4',                                        //optional; default is '4/4'
   notes: 't d4, t d_4, t d4, q a#5, q b5, q rest, w e4'  //not optional; default is an empty string
}
~~~
3) Pass the melody object to Offbeat's .layer() method to create an instance of the library:
~~~
const layer = Offbeat.layer(melody) 
~~~
### Offbeat.layer(melody)  
__Input:__ melody object   
__Return:__ instance of Offbeat  

Create an instance of Offbeat. Object properties are set to default if a melody object is not provided.  

### layerInstance.layer(melody)  
__Input:__ melody object  
__Return:__ updated instance 

Update current instance of Offbeat.

### layerInstance.play()  
__Input:__ no parameters  
__Return:__ no return value  

Output audio through a single audio context, which closes after the last oscillator node ends.

### layerInstance.playReverse()  
__Input:__ no parameters  
__Return:__ no return value  

Output audio in reverse.

### layerInstance.playLoop()
__Input:__ no parameters  
__Return:__ no return value  

Loop audio until .stop() is called.

### layerInstance.playReverseLoop()
__Input:__ no parameters  
__Return:__ no return value  

Loop audio in reverse until .stop() is called.

### layerInstance.stop()  
__Input:__ no parameters  
__Return:__ no return value  

Close current audio context and end looping.

### layerInstance.time()  
__Input:__ no parameters  
__Return:__ float  

Calculate the duration of audio in seconds.

### layerInstance.ended()
__Input:__ no parameters  
__Return:__ no return value 

Ends current audio loop.


