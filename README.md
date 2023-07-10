# General info
This is a modification of the You drove of the road game by Ian Henderson to allow for tassing.<br>
The html file here includes all code needed for tasing. <br>
To run a tas add it as a script tag at the comment `<!-- load your tasfile(s) here-->`, <br>
The file will run on loading the page, reload to rerun the file. <br>
The tas file manually caps your inputs to between 0-800 as these seem to be the boandries on my machine,<br>
however your actual screensize should not effect the tas. 

# Tas File Layout
tas files are .js files with the following inside them


tasFiles.push({<br>
loadLevel : `[levelname]`,<br>
frameAdvance : `[number] (optional)`,<br>
skipFrames: `[number] (optional)`,<br>
inputs : \`<br>
`[inputlines]`<br>
`<br>
})

levelname = the name of the level you're tasing<br>
frameAdvance = if set the game will run in frameadvance mode, the numer you enter will specify the default amount of frames to advance.<br>
skipFrames = the starting of frameadvance will be delayed by this amount (overwritten by breakpoints)<br>
inputs = the actual inputs of the tas, see below

# Input format
Actual input take two forms<br>
`frames:X,Y` and `frames`<br>
The former will hold the mouse down on those coordinator for that many frames (X and Y are capped between 0-800 and only allow integers)<br>
The latter will release the mouse for that many frames<br>
Spaces are ignored so both `5:200,200` and `5 : 200, 200` are valid inputs

### Further Commands
`***` will create a breakpoint, when running in frameadvance mode, the tas will run and stop the frame before the input after the last breakpoint.<br>
`#anything` is a comment and will be ignored<br>
empty lines will also be ignored

# Frame Advance
**Note: Frame Advance is not perfectly accurate, run tases without it to verify**

When running in frameadvance, there are three buttons to use:<br>
- P: Will run the game for the amount of frames specified in the tas file
- O: Will run the game for 1 frame
- I: Will exit frameadvance mode