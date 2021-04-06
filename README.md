# spyder_notes
A place for my personal notes about Spyder IDE that others may find useful.

#### CWD:
Spyder has this slight annoyance when restarting in that it changes the directory back to a standard 'C:\Users\USERNAME\'  
directory everytime it restarts. Adding the following lines to your script gets around that:
```python
import os
# either assign directory to a variable
DIRECTORY = "YOUR DESIRED DIRECTORY PATH"
# or just place it here in a string
os.chdir(DIRECTORY)
```

If you right click on the tab with the open script in the editor and select 'set as console working directory', you can copy the  
directory path from the top right of the window into your DIRECTORY variable and save yourself the headache.

Use #### to enable custom selections in the outline pane.  
	- open the outline pane with CTRL+SHIFT+O  


There seems to be some issue with using the console in Spyder when the script makes use of argparse. When calling script  
with an argument specified with action='store_const', 'store_true' or 'store_false', the console hangs and nothing happens.  
The only way around this that I've found is to call your script from outside of Spyder IDE. None of the rest of the arguments  
will cause this issue, just an argument with 'action=' defined as a parameter to add_argument(). I've done a few hours  
worth of frustrated testing and I have come up with no better solution. It's just something to note. My current version,  
since 5.0.0 is bugged as of this writing, is 4.2.5. My hope is that it's some underlying issue with Spyder and that it will  
be fixed in short order.






