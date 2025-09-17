## SUBMITTING YOUR FIRST JOB

Create a shell script with paramaters similar to the one below:

``` console
#!/bin/sh
#SBATCH --account maths
#SBATCH --partition=ada
#SBATCH --time=10:00:00
#SBATCH --nodes=1 --ntasks=4
#SBATCH --job-name="MyMathsJob"
#SBATCH --mail-user=MyEmail@uct.ac.za
#SBATCH --mail-type=ALL

/opt/exp_soft/softwareX/xyz -o /home/fred/testA15/myfile.txt

```

=== "SBATCH script for R jobs"

    ``` console
    #!/bin/sh
    #SBATCH --account=myaccount
    #SBATCH --partition=ada
    #SBATCH --nodes=1 --ntasks=1
    #SBATCH --time=10:00
    #SBATCH --job-name="MyJob"
    module load software/R-4.3.3
    R CMD BATCH MyRScript.R
    ```

=== "SBATCH script for Python jobs"

    ``` console
    #!/bin/sh
    #SBATCH --account=myaccount
    #SBATCH --partition=ada
    #SBATCH --nodes=1 --ntasks=1
    #SBATCH --time=10:00
    #SBATCH --job-name="MyJob"
    module load python/miniconda3-py3.12
    python MyPythonScript.py
    ```

    !!! note

        We make use of Miniconda to deploy Python. The version of Python is appended to the module name, in this case it is version 3.12.

=== "SBATCH script for MATLAB jobs"

    ```console
    #!/bin/sh
    #SBATCH --account=myaccount
    #SBATCH --partition=ada
    #SBATCH --nodes=1 --ntasks=1
    #SBATCH --time=10:00
    #SBATCH --job-name="MyJob"
    module load software/matlab-R2024b
    matlab -batch MyMatlabScript
    ```

    !!! note

        It is essential to add the `-batch` parameter and also exclude the `.m` extension of the MATLAB script.

---

## RUNNING INTERACTIVE JOBS

An interactive job gives you command line access to a worker node. 

From the head node type:

```
    sintx
```

The cluster will indicate that you are starting an interactive job and your prompt will change to that of a worker node.  In addition the hostname format changes to black on white text:

![running sintx for interactive jobs](interactive.jpg)

Now any command you type is executed on that node. If you do not see the text “_Starting interactive job_” then you are still on the head node and should not run any heavy load processes.

Unlike `salloc` your commands do not need to be prefaced with `srun` unless you are running OpenMPI code.

Type `exit` to end the job and you will return to the head node.

You can specify additional cluster parameters with the sintx command just as in an sbatch file:

```
      sintx --ntasks=20 --account=maths --partition=ada
```

Account and partition parameters are not mandatory unless you have access to more than one partition.

In addition `sintx` automatically creates a `DISPLAY` environment variable should you wish to export a graphical display back to your workstation. You will however need to be running an Xclient on your desktop.

### Advanced node selection

The _ada_ partition consists of several tranches of worker nodes purchased over time.  The characteristics of these nodes are uniform within their tranches, however the 100 series are more powerful than the 200 series.  The architecture of these nodes can be viewed here.  By default your jobs will target the 100 range in the ada partition.  When this fills up jobs will spill over into the 200 series. If you want to avoid this and rather have your job queue until a faster node is available you must use the following directive:

```
    #SBATCH --constraint=large
```

The 200 series have a slightly better RAM\core ratio, if you want your jobs to target these nodes then specify the following directive:

```
    #SBATCH --constraint=small
```

---

## Monitoring & Efficiency

### HPC Dashboard

The HPC Dashboard offers a real-time view of the system.

[:fontawesome-solid-square-check: Check cluster status](http://srvrochpc001.uct.ac.za/db){ .md-button .md-button--primary }

### File System Quota Check

Users are encouraged to check their quotas by executing the following command:

``` shell
myquota
```

This will produce two results, your quota in /home and /scratch for example:

``` shell
The quota is per volume, not per folder. Quota values are refreshed every few minutes.

Volume   Quota    Used  %Used
/home    10GB     5GB   50%
/scratch 100GB   76GB   76%

```