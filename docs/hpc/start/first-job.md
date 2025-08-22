# Running Your First Job

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