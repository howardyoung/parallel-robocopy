# Parallel Robocopy

This Powershell script spawns multiple copies of robocopy as a process which each process will use mutiple threads.

This increases the maximum number of outstanding I/Os and reduces the copy time faster than just using the -mt flag.

Instructions are in the Powershell script

Ref my original writeup:

https://support.zadarastorage.com/hc/en-us/articles/213024806-How-to-Run-Robocopy-in-Parallel
