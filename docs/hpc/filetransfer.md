
=== "Windows"


    If you are comfortable using the windows command prompt, CMD, then you can download pscp.exe from http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html. To transfer files from or to your computer use the following commands:

    ```
        pscp myfile.txt username@hpc.uct.ac.za:/home/username
        pscp username@hpc.uct.ac.za:/home/username/myfile.txt .
    ```

    !!! note
        
        Note the ‘.’ at the end of the last example.

    Alternately you can download a graphical interface such as WinSCP. You would login to the cluster in much the same fashion as above, except you will be presented with a dual pane graphical interface similar to Windows Explorer where you can drag and drop files between hpc and your computer.



 

=== "Mac"


    `scp myfile.txt username@hpc.uct.ac.za:/home/username`
    `scp username@hpc.uct.ac.za:/home/username/myfile.txt .`


=== "Linux"


    `scp myfile.txt username@hpc.uct.ac.za:/home/username`
    `scp username@hpc.uct.ac.za:/home/username/myfile.txt .`

    Alternately we also recommend rsync, although if you’re transferring files to the cluster this application would need to be installed on the source host.  Rsync is preferred as it will do a sync of data not yet copied in the case of a copy being interrupted.

    To copy a folder from your linux box to hpc use:

    `rsync -avr FolderName username@hpc.uct.ac.za:/scratch/username/`

    This will copy FolderName to your scratch folder. NB do not put a trailing slash on FolderName, otherwise the contents of FolderName will be copied to scratch which is not generally what one wants.


    If you are using a graphical interface you can launch the command line from the menu. In most distros it is called the Terminal, in the example below, Ubuntu, it is found under Applications, Accessories.

