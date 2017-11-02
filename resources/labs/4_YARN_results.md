**YARN/RM Lab: Tuning for YARN**
## Running the first initial script
```
[root@stf-btc-20171030-1 ~]# sh YARNtest.sh
Testing loop started on Thu Nov 2 00:27:47 PDT 2017
Launching the teragen job to create a 10Gb File through MRv2

Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m30.202s
user	0m4.909s
sys	0m0.241s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 1 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	8m4.038s
user	0m6.914s
sys	0m0.389s
Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m37.985s
user	0m6.096s
sys	0m0.244s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 1 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	8m13.940s
user	0m8.446s
sys	0m0.473s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
Testing loop ended on Thu Nov 2 00:47:23 PDT 2017
```

## Running the new loop with the new properties values

```


```
