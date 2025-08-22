# User Policy & Acceptable Use

By logging on to the ICTS HPC cluster you are agreeing to abide by UCT’s policy and rules on Internet and email use as well as the HPC Acceptable Use Policy terms and conditions outlined below;

## General HPC terms and conditions

- Computing resources including but not limited to CPUs, RAM, disk space, internet bandwidth and networking are to be used for research purposes only.
- User accounts may not be shared.
- No commercial work is permitted.
- No proxy work, you may not submit jobs on behalf of someone else.

## Revocation of access

Any infringement of the above terms, or if the following abuse is noted, may result in your user account being suspended and/or disciplinary action:

- Running jobs or any high load process on the head node.
- Viewing or editing extremely large files on the head node.
- Fraudulent requests for HPC resources.
- Causing a file system to run out of space.
- Allowing illegal access to the cluster.
- Downloading non-research related files or data.

## Abandoned accounts

- Accounts that have never been logged into will be deleted after 12 months.
- Accounts not accessed in over a year will be deleted in the event we are unable to contact the researcher to establish a continued need.

## Core, Memory and Time limits

By default, users will have access to a [set number of cores](allocations.md).  This can be boosted if the cluster is under-utilised or if the usage patterns of a researcher’s jobs can be anticipated. If jobs are queued and the cluster is severely under-used then these jobs will be allowed to run by discretion of the HPC system administrators. The limits will be altered over time as hardware and usage patterns change in order to achieve maximum efficiency and usage of the cluster.

If your jobs are known to have a low wall time and\or you make use of the wall time directive then depending on the current state of the cluster your core usage may be increased substantially at the discretion of the administrators.

The maximum wall and times are displayed on the dashboard under partition parameters. Additional partition attributes can be found under [resource allocation](allocations.md).

## Space usage

`/home`:   There is limited disk space on `/home` and this is shared with other researchers. You are limited to __10GB__ in `/home` for scripts or reference data. This volume is protected by ICTS’s backup system although there is a cost for restores.

`/scratch`:   The `/scratch` volume provides extremely high speed disk access for transient research data. You will be granted a __50GB quota__ by default. The `/scratch` volume is volatile and is not backed up. Users are expected to move data off this volume once computation is completed. Old files will automatically be deleted if the volume starts to run out of space. The 50GB quota can be increased on request.

`eresearchData`: Long term storage for research data.


| Quota | Lifespan (days) |
| ----- | --------------- |
| 50GB (default) | indefinite |
| 500GB | indefinite |
| 1TB | 12 months by agreement |
| 5TB  | Dependent on agreement |
| Over 5TB | Dependent on agreement |

!!! warning "Understanding your quota"

    Storage allocation is applied to a user on the `/scratch` file system. These are not directory quotas, they are user quotas applied to the entire file system.

!!! info "Checking your quota"

    You can check your quota and usage stats with the `myquota` command. [Click here](../work/monitoring.md) to learn more.

!!! danger "Please note"

    Using the `touch` command to modify files in the `/scratch` volume will result in your user account being revoked.


!!! tip "Long term storage"

    Users requiring reliable long term central storage should contact [eresearch@uct.ac.za](mailto:eresearch@uct.ac.za). This storage is separate to the HPC cluster. 

## End of project

When your account is deleted all files on `/home` and `/scratch` are deleted. It is your responsibility to move data off the HPC file systems when your research projects come to an end.


## Privacy

All user home directories are protected at the file system level. Researchers that request shared data areas must inform ICTS HPC staff as to which HPC users or groups may have access to these areas.

## Rogue processes

In order to maintain the stability of the HPC clusters, the ICTS HPC administrators reserve the right to terminate any running job or process that does not fall within the agreement of good usage, or that threatens the running of other researchers’ jobs.

## Data and disaster recovery

You are responsible for your data. Recovery costs due to data loss caused by user action or inaction will incur a cost. Only data that is stored on `/home` is backed up to tape. Data stored on these tapes will be kept for a __maximum period of one year__, thereafter the tapes will be recycled.

## Compilation of software

Compiling of software or installing libraries must not be done on the head node. This must be run as a job. If debugging or interaction is required then you must run an [interactive job](../work/interactive.md).

## Data transfer

You may transfer data via the head node, however it is preferred that large downloads of data are done via a worker node as part of a job.

## Citations

Researchers are required to notify us of any submissions, publications or presentations that contains work conducted using the HPC resources. The following form of acknowledgement must also be included in your published work:


!!! quote "Citation"

    _Computations were performed using facilities provided by the University of Cape Town’s ICTS High Performance Computing team: [hpc.uct.ac.za](https://ucthpc.uct.ac.za/)._

    _[doi.org/10.5281/zenodo.10021613](https://doi.org/10.5281/zenodo.10021613)._


## Off-Campus logins

If you need to access cluster from outside of UCT you will need to do so by making use of the VPN.