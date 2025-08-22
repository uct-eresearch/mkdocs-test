# Monitoring & Efficiency

## HPC Dashboard

The HPC Dashboard offers a real-time view of the system.

[:fontawesome-solid-square-check: Check cluster status](http://srvrochpc001.uct.ac.za/db){ .md-button .md-button--primary }

## File System Quota Check

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