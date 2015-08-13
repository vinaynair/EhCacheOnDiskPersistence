PRE-REQUISTIES
==============
Maven for build

HOW TO RUN THE SAMPLE
======================
First time when you run the same, there is no persisted on the disk by the cache 
So we see we read NULL but we will write to the cache.
``` 
$> mvn compile exec:exec
Reading from cache null
Writing to cache [ key = a, value=b, version=1, hitCount=1, CreationTime = 1439480214501, LastAccessTime = 1439480214505 ]
```

Therefore when we run the same program next time, the cache will be backed by the persistent disk store,
and we shall be able to read the value from the cache
```
$>mvn exec:exec
Reading from cache [ key = a, value=b, version=1, hitCount=2, CreationTime = 1439480215000, LastAccessTime = 1439480303001 ]
Writing to cache [ key = a, value=b, version=1, hitCount=1, CreationTime = 1439480303001, LastAccessTime = 1439480303006 ]
```