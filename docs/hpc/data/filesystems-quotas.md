# Filesystems & Quotas

## `/scratch` for Computing

`/scratch` is mounted on all worker nodes. The file system is intended to provide fast disk I/O. The `/scratch` file system is shared space and is intended for temporary processing, not long term storage. Should the `/scratch` file system run out of space all users are affected.

Users are granted a default quota of 100GB in `/scratch` and are requested to apply for additional storage by [e-mailing the HPC administrators](../help/support.md/#Contact-us). 

### What should you do on `/scratch`?

This is the preferred place to put any intermediate files required while a job is executing. 

We encourage users who have large datasets to upload them directly to `/scratch`, not `/home`.

The output of all computation should also be directed to `/scratch`.


!!! warning "`scratch` is not backed up"

    `/scratch` is purposely built as a computational work space and is __not intended for long term storage__.

    Any data which is lost from `/scratch` cannot be recovered.


### What should you __not__ do on `scratch?

`scratch` should not be used for long-term storage. Users are expected to move their data from `/scratch` to long term storage as part of their workflow. 

Scripts and other data that cannot easily be replicated should not be stored in `/scratch`.

Data that you wish to keep must be downloaded and removed from `/scratch`.


## `/home` for XYZ

Please note that you may only store 10GB of data on `/home`.