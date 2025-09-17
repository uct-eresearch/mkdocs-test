## ACCEPTABLE USE POLICY

By logging on to the ICTS HPC cluster you are agreeing to abide by UCT’s policy and rules on Internet and email use as well as the HPC Acceptable Use Policy terms and conditions outlined below;

__1. General HPC terms and conditions__

- Computing resources including but not limited to CPUs, RAM, disk space, internet bandwidth and networking are to be used for research purposes only.
- User accounts may not be shared.
- No commercial work is permitted.
- No proxy work, you may not submit jobs on behalf of someone else.

__2. Revocation of access__

Any infringement of the above terms, or if the following abuse is noted, may result in your user account being suspended and/or disciplinary action:

- Running jobs or any high load process on the head node.
- Viewing or editing extremely large files on the head node.
- Fraudulent requests for HPC resources.
- Causing a file system to run out of space.
- Allowing illegal access to the cluster.
- Downloading non-research related files or data.

__3. Abandoned accounts__

- Accounts that have never been logged into will be deleted after 12 months.
- Accounts not accessed in over a year will be deleted in the event we are unable to contact the researcher to establish a continued need.

__4. Core, Memory and Time limits__

By default, users will have access to a [set number of cores](allocations.md).  This can be boosted if the cluster is under-utilised or if the usage patterns of a researcher’s jobs can be anticipated. If jobs are queued and the cluster is severely under-used then these jobs will be allowed to run by discretion of the HPC system administrators. The limits will be altered over time as hardware and usage patterns change in order to achieve maximum efficiency and usage of the cluster.

If your jobs are known to have a low wall time and\or you make use of the wall time directive then depending on the current state of the cluster your core usage may be increased substantially at the discretion of the administrators.

The maximum wall and times are displayed on the dashboard under partition parameters. Additional partition attributes can be found under [resource allocation](allocations.md).

__5. Space usage__

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

__6. End of project__

When your account is deleted all files on `/home` and `/scratch` are deleted. It is your responsibility to move data off the HPC file systems when your research projects come to an end.


__7. Privacy__

All user home directories are protected at the file system level. Researchers that request shared data areas must inform ICTS HPC staff as to which HPC users or groups may have access to these areas.

__8. Rogue processes__

In order to maintain the stability of the HPC clusters, the ICTS HPC administrators reserve the right to terminate any running job or process that does not fall within the agreement of good usage, or that threatens the running of other researchers’ jobs.

__9. Data and disaster recovery__

You are responsible for your data. Recovery costs due to data loss caused by user action or inaction will incur a cost. Only data that is stored on `/home` is backed up to tape. Data stored on these tapes will be kept for a __maximum period of one year__, thereafter the tapes will be recycled.

__10. Compilation of software__

Compiling of software or installing libraries must not be done on the head node. This must be run as a job. If debugging or interaction is required then you must run an [interactive job](../work/interactive.md).

__11. Data transfer__

You may transfer data via the head node, however it is preferred that large downloads of data are done via a worker node as part of a job.

__12. Citations__

Researchers are required to notify us of any submissions, publications or presentations that contains work conducted using the HPC resources. The following form of acknowledgement must also be included in your published work:

!!! quote "Citation"

    _Computations were performed using facilities provided by the University of Cape Town’s ICTS High Performance Computing team: [hpc.uct.ac.za](https://ucthpc.uct.ac.za/)._

    _[doi.org/10.5281/zenodo.10021613](https://doi.org/10.5281/zenodo.10021613)._



__13. Off-Campus logins__

If you need to access cluster from outside of UCT you will need to do so by making use of the VPN.

---

## ALLOCATIONS

### Overview

Resources are assigned to partitions which can be thought of as queues.


| Partition	| Description |	Nodes |	Cores / node | Max cores / user | Time limit |
| --------- | ----------- | ----- | ------------ | ---------------- | ---------- |
| ada : 100 series | Fast cores, less RAM | 100-115 | 48 | 200 | 250 hours |
| ada : 200 series | Slower cores, more RAM | 200-226 | 40 | 200 | 250 hours|
| curie | Alternate partition | 600-607 | 64 | 64 | 100 hours|
| l40s | GPU partition | 012-015 | 48 (4 GPU cards) | 96 (8 GPU cards) | 48 hours|
| gpumk | Compsci GPU partition | 005-008 | 32 (4 GPU cards) | varies | Private |
| a100 | GPU partition | 009-011 | 56 (4 GPU cards) | varies | varies |
| sadacc | Private | 128-135 | 44 (4 GPU cards) | 176 | 1 hour |

!!! note "Understanding your allocations"

    Researchers are assigned to an account which is analogous to a group, normally their department or research group, for instance maths, compsci etc. A researcher may also be assigned to additional accounts. Accounts may also be limited to specific partitions, hence a researcher may submit to the ada partition using their maths account, but may only submit to the GPU partition using their mathsgpu account for example.


### Specifying time limits
    
If you do not specify a time limit then your job will inherit the default maximum partition time. You may however not want this, as the shorter the wall time specified, the more likely a queued (waiting) job is to be selected by the backfill scheduler to jump the queue. The scheduler can only do this if the job guarantees it will finish in a specified, short period of time.

!!! note "Time format in SLURM"

    Before starting it is important to understand the format of the time parameter to avoid ambiguity and confusion. Acceptable time formats include “minutes”, “minutes:seconds”, “hours:minutes:seconds”, “days-hours”, “days-hours:minutes” and “days-hours:minutes:seconds”.  This option applies to job and step allocations. If you do not specify a wall time then the partition’s default wall time will be applied to your job. This will potentially disadvantage you in terms of job priority, so if you know that your job will finish in a certain time then specify that wall time in your sbatch script. When you do this the scheduler can more easily backfill your job, in other words allow it to jump the queue and start sooner.

    __Some examples:__
    
    - 50 = 50 minutes
    - 50:00 = 50 minutes
    - 50:00:00 = 50 hours
    - 2-2 = 50 hours (2 days and 2 hours)
    - 2-2:00 = 50 hours (2 days and 2 hours)
    - 2-2:00:00 = 50 hours (2 days and 2 hours)


### Initial job node limitations

Parallel jobs using MPI can address cores on multiple nodes using the nodes= directive. However if your job is not capable of running in MPI mode reserving more than one node will not make your job run faster. As some researchers do not fully understand the distinction between nodes and cores we sometimes find non-MPI jobs reserving cores on nodes that are not used. In order to avoid this waste of resource we have set the number of nodes that can be reserved for a job to 1.  In order to increase this limit please contact us.

### Undergraduate and Honours work

The UCT HPC cluster is intended for postgraduate supervised work that will result in a MSc, PhD or peer reviewed paper published in an accredited journal. We do however grant undergrads limited access to the cluster as we believe that this is the best time to learn how to use Linux and HPC schedulers. Undergrads are limited to 80 simultaneous cores and 100 hour jobs and honours students are limited to 120 simultaneous cores 170 hour jobs.

--- 

## MAINTENANCE

ICTS has several data centers across campus and has a maintenance policy for each center. Additionally the HPC team has maintenance tasks that need to be carried out on the firmware, operating system and application software of the HPC nodes.

Most maintenance slots do not require a full shut down of the data centers and your submitted jobs should continue running, however access to the cluster may be limited. If we are aware of a full data center shutdown it will be highlighted on this page, our blog and the dashboards. We will also attempt to contact our users well in advance.

[:fontawesome-solid-calendar-days: Maintenance dates for ICTS data centers](https://icts.uct.ac.za/about-icts/scheduled-icts-maintenance-slots){ .md-button .md-button--primary }

---

## SECURITY

Key management, MFA, secrets handling, and incident reporting.

---

## INVESTMENT OPTIONS

Buy‑in and co‑investment programs for priority access or hardware.
