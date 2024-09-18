# Parallel Robocopy

This Powershell script spawns multiple copies of robocopy as a process which each process will use mutiple threads.

This increases the maximum number of outstanding I/Os and reduces the copy time faster than just using the -mt flag.

Instructions are in the Powershell script

Reference to my original writeup:

https://support.zadarastorage.com/hc/en-us/articles/213024806-How-to-Run-Robocopy-in-Parallel


## Best Practices

* **Parallel Robocopy Jobs**: Running multiple Robocopy jobs in parallel can significantly speed up copy times, potentially reducing backup speed by a factor of 61.

* **Strategy**: Maximize the number of independent folders processed by Robocopy. For example, creating backup jobs for each user home directory.

* **Script Details**: The provided script iterates through user directories, dispatching backup jobs while limiting the number of concurrent jobs to avoid performance degradation.

* **Optimization Tips**: For maximum SMB throughput, do not exceed 8 concurrent Robocopy jobs with 20 threads5. Lower the number of threads if volumes are encrypted.