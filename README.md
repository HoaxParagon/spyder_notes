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

 Something to note is that in a smaller test file containing the exact argparse code that caused the issue  
with a much larger program DIDN'T have the issue, the small test script worked. The case where the console hangs is in a large,  
~1,500 line script, where four classes and two functions are defined above if __name__ == '__main__':. Further testing is required,  
however I'm moving on with the project and simply calling to script with a console not related to Spyder.

EXAMPLE:
```python
	parser = argparse.ArgumentParser()
	parser.add_argument('-a', action='store') # this causes difficulties, I'm unsure why. TODO: add what the difficulties are, find out, with the latest update, if this still happens.  
```
\# calling to the script in Spyder console as follows would produce the error:
!python script_name.py -a # upon execution, this hangs the kernel without output, no debug prints execute, console hangs.


This isn't specifically a Spyder IDE note. It's about anaconda. I recently learned that there's a revision system. ```conda list --revisions``` will list the available revisions, their dates and the changes made. ```conda install --revision NN``` where NN is your own revision number will let you revert changes. It will take a few minutes to prompt you with a list of changes then asks if you'd like to proceed. Reverting back has fixed one of my issues after an update. The other one will have to wait until spyder-kernels is updated to 2.1.0 on conda forge.  

Spider has been updated to 5. Some UI elements don't line up and the outline tab doesn't work if you restart the application but not your PC...  
Not the best but spyder-kernals is updated to 2.10 now.  


There's an issue with the latest version, as of 9/10/21, where the outline and the alignment markers don't show up. This can be fixed by making a change to the file, pressing  
space and deleting it.  

Also seems to be a bit of a long term stability issue with Spyder where the longer it's open the slower it gets. I can't be sure but it seems to be some memory issue.  
I also think that there could be an issue with github desktop being open at the same time that files are being accessed.  

#### STARTING ALL OVER
(this video)[https://www.youtube.com/watch?v=Ul79ihg41Rs] from one of the developers is a pretty good tutorial on fixing your broken install or starting over. This isn't the first time I've had to start all over either.  
relevent commands to start a new env are as follows:
```
conda create -n {THE NAME} python=3 -y  
conda activate {THE NAME}  
conda install -y spyder  
```
