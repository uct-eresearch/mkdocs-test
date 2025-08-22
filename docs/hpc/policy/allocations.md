# Allocations

## Overview

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


## Specifying time limits
    
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


## Initial job node limitations

Parallel jobs using MPI can address cores on multiple nodes using the nodes= directive. However if your job is not capable of running in MPI mode reserving more than one node will not make your job run faster. As some researchers do not fully understand the distinction between nodes and cores we sometimes find non-MPI jobs reserving cores on nodes that are not used. In order to avoid this waste of resource we have set the number of nodes that can be reserved for a job to 1.  In order to increase this limit please contact us.

## Undergraduate and Honours work

The UCT HPC cluster is intended for postgraduate supervised work that will result in a MSc, PhD or peer reviewed paper published in an accredited journal. We do however grant undergrads limited access to the cluster as we believe that this is the best time to learn how to use Linux and HPC schedulers. Undergrads are limited to 80 simultaneous cores and 100 hour jobs and honours students are limited to 120 simultaneous cores 170 hour jobs.

 

