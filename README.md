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









