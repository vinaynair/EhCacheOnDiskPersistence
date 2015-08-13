PRE-REQUISTIES
==============
Maven for build

HOW TO RUN THE SAMPLE
======================
First time when you run the sample, there is no persisted data on the disk.
So we / cache will get NULL (for a given key hardcoded within the sample). 
But at the end of the sample, we will write to the cache.
``` 
$> mvn compile exec:exec
Reading from cache null
Writing to cache [ key = a, value=b, version=1, hitCount=1, CreationTime = 1439480214501, LastAccessTime = 1439480214505 ]
```

Now when we run the same program one more time, since we have cache data persisted on disk, 
we shall be able to read the value from the cache. 
```
$>mvn exec:exec
Reading from cache [ key = a, value=b, version=1, hitCount=2, CreationTime = 1439480215000, LastAccessTime = 1439480303001 ]
Writing to cache [ key = a, value=b, version=1, hitCount=1, CreationTime = 1439480303001, LastAccessTime = 1439480303006 ]
```