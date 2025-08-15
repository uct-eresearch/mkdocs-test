Once you have been granted an account you will need to login to the head node of one of the clusters. All the clusters run Linux and you will need to be comfortable working with the command prompt. If you have had no experience with the Linux command line interface we have training material as well as a how to guide. Alternately there are numerous web articles on how to use the Linux command prompt.

Our head node is called hpc.uct.ac.za as well as hex.uct.ac.za.  When using these guides we refer to hpc.uct.ac.za, however you can substitute hex for hpc if you wish.

## Logging in from the UCT network (on campus)

=== "Windows"


    You will need to download a ssh client. We recommend PuTTY from http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html.

    We recommend just downloading the 64-bit x86 executable:



    Save putty.exe to your C: drive and run it. Enter the hostname of the cluster, for example hpc.uct.ac.za, and click Open. The first time you do this answer Yes to the security alert.

    

    Now enter your username, press enter, then enter your password and press enter.  NB, the password characters will not appear when you type them, this is a security feature. You are now logged in. Type ls -l and press enter.


    Here we see a folder called bin and a file called example.sh. To navigate to the bin folder enter cd bin. To move back again enter cd ..

    To exit from the cluster type exit. It is beyond the scope of this document to discuss editing files or submitting jobs.




 

=== "Mac"


    Most Apple MAC OS’s come with ssh and scp preinstalled. From Applications, Utilities select Terminal.

    
    Then type:

    `ssh username@hpc.uct.ac.za`



=== "Linux"


    Most Linux distros come with ssh and scp preinstalled. If you are using the command line you would type:

    `ssh username@hpc.uct.ac.za`

 

## Off-campus logins

If you need to access cluster from outside of UCT you will need to do so by making use of the VPN.