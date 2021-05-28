# +sounds #
Package with sound files (if initialized repo with Git-LFS) and function to play them.

## Usage ##

### GIT ###
To add this file as a submodule package to a MATLAB project:
1. Open a git bash in the desired project folder.
2. Use the following syntax to add the submodule as a package folder:  
```(git)
git submodule add https://github.com/m053m716/-sounds +sounds
```

### MATLAB ###
Play the default `alert` sound.
```(matlab)
sounds.play();
```  

Play a specific sound (add more `.mat` files to package and use their name).
  * Current options are: `'alert'`, `'bell'`, `'camera'`, or `'pop'`
  * See the **[adding sounds](#adding-sounds)** for file format.
```(matlab)
sounds.play('camera');
```  

Play the `alert` sound with twice the frequency (twice as fast).
```(matlab)
sounds.play('alert', 2);
```

Play the `alert` sound at the normal frequency but with 50 dB attenuation.  
  + _Note: the signal is first normalized so that its maximum absolute deviation is equal to one, then attenuated._
```(matlab)
sounds.play('alert', 1, -50);
```

## Adding Sounds ##

All sound files are in `.mat` (`'-v7.3'`) files. Each file contains two variables:  
* **`sfx`** - The sound-effect vector, a 1 x nSamples (single) vector of the audio waveform.
  + _Note: output is automatically rescaled by its maximum value prior to applying any attenuation._
* **`fs`** - The sample frequency of the file (Hz). Default value is 44100 (double).

## Version Info ##
* _Initial_: MATLAB Version 9.2.0.538062 (R2017a) 06-Aug-2020
* _Current_: MATLAB Version: 9.9.0.1592791 (R2020b) Update 5
  + _Operating System_: Microsoft Windows 10 Home Version 10.0 (Build 19042)
  + _Java Version_: Java 1.8.0_202-b08 with Oracle Corporation Java HotSpot(TM) 64-Bit Server VM mixed mode
