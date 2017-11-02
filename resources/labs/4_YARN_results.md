## YARN/RM Lab: Tuning for YARN
**Running the first initial script**
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

**Running the new loop with the new properties values**

```
[root@stf-btc-20171030-1 ~]# sh YARNtest.sh
Testing loop started on Thu Nov 2 00:59:04 PDT 2017
Launching the teragen job to create a 10Gb File through MRv2

Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m32.902s
user	0m4.583s
sys	0m0.251s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 8 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m0.506s
user	0m7.478s
sys	0m0.405s
Deleted /results/tg-10GB-8-8-512
Deleted /results/ts-10GB-8-8-512
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m31.165s
user	0m5.959s
sys	0m0.229s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 8 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m28.557s
user	0m7.012s
sys	0m0.370s
Deleted /results/tg-10GB-8-8-1024
Deleted /results/ts-10GB-8-8-1024
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m29.092s
user	0m5.814s
sys	0m0.269s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 10 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m7.961s
user	0m7.807s
sys	0m0.374s
Deleted /results/tg-10GB-8-10-512
Deleted /results/ts-10GB-8-10-512
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m29.909s
user	0m5.975s
sys	0m0.215s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 10 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m52.478s
user	0m7.883s
sys	0m0.428s
Deleted /results/tg-10GB-8-10-1024
Deleted /results/ts-10GB-8-10-1024
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m31.006s
user	0m5.931s
sys	0m0.223s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 20 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m26.695s
user	0m8.360s
sys	0m0.427s
Deleted /results/tg-10GB-8-20-512
Deleted /results/ts-10GB-8-20-512
Running the Teragen job with the following properties:

_____________________________

> 8 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m35.757s
user	0m6.242s
sys	0m0.250s
Running the Terasort job with the following properties:

_____________________________

> 8 mappers

> 20 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	7m1.475s
user	0m7.576s
sys	0m0.408s
Deleted /results/tg-10GB-8-20-1024
Deleted /results/ts-10GB-8-20-1024
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m37.222s
user	0m6.330s
sys	0m0.266s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 8 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m0.651s
user	0m8.666s
sys	0m0.489s
Deleted /results/tg-10GB-10-8-512
Deleted /results/ts-10GB-10-8-512
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m36.930s
user	0m5.936s
sys	0m0.196s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 8 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m38.558s
user	0m7.250s
sys	0m0.431s
Deleted /results/tg-10GB-10-8-1024
Deleted /results/ts-10GB-10-8-1024
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m35.179s
user	0m5.847s
sys	0m0.260s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 10 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m7.704s
user	0m7.952s
sys	0m0.385s
Deleted /results/tg-10GB-10-10-512
Deleted /results/ts-10GB-10-10-512
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m39.723s
user	0m5.862s
sys	0m0.230s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 10 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m35.701s
user	0m7.183s
sys	0m0.386s
Deleted /results/tg-10GB-10-10-1024
Deleted /results/ts-10GB-10-10-1024
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m37.977s
user	0m5.634s
sys	0m0.234s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 20 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m30.313s
user	0m7.434s
sys	0m0.426s
Deleted /results/tg-10GB-10-20-512
Deleted /results/ts-10GB-10-20-512
Running the Teragen job with the following properties:

_____________________________

> 10 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m38.243s
user	0m5.935s
sys	0m0.223s
Running the Terasort job with the following properties:

_____________________________

> 10 mappers

> 20 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	7m14.231s
user	0m7.845s
sys	0m0.431s
Deleted /results/tg-10GB-10-20-1024
Deleted /results/ts-10GB-10-20-1024
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m51.033s
user	0m6.179s
sys	0m0.234s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 8 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m2.203s
user	0m7.669s
sys	0m0.403s
Deleted /results/tg-10GB-20-8-512
Deleted /results/ts-10GB-20-8-512
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m52.830s
user	0m5.961s
sys	0m0.226s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 8 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m36.759s
user	0m7.388s
sys	0m0.335s
Deleted /results/tg-10GB-20-8-1024
Deleted /results/ts-10GB-20-8-1024
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m50.165s
user	0m5.993s
sys	0m0.226s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 10 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m5.707s
user	0m7.805s
sys	0m0.366s
Deleted /results/tg-10GB-20-10-512
Deleted /results/ts-10GB-20-10-512
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m52.072s
user	0m6.164s
sys	0m0.223s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 10 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m41.772s
user	0m7.734s
sys	0m0.332s
Deleted /results/tg-10GB-20-10-1024
Deleted /results/ts-10GB-20-10-1024
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 512 reducers

> 409 MB  map_heap_size

_____________________________



real	1m50.936s
user	0m5.891s
sys	0m0.245s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 20 reducers

> 512 MB per_reducers

> 409 MB map_heap_size

> 409 MB reduce_heapsize

_____________________________


real	7m16.958s
user	0m7.521s
sys	0m0.418s
Deleted /results/tg-10GB-20-20-512
Deleted /results/ts-10GB-20-20-512
Running the Teragen job with the following properties:

_____________________________

> 20 mappers

> 1024 reducers

> 819 MB  map_heap_size

_____________________________



real	1m52.194s
user	0m6.249s
sys	0m0.261s
Running the Terasort job with the following properties:

_____________________________

> 20 mappers

> 20 reducers

> 1024 MB per_reducers

> 819 MB map_heap_size

> 819 MB reduce_heapsize

_____________________________


real	6m56.911s
user	0m8.142s
sys	0m0.439s
Deleted /results/tg-10GB-20-20-1024
Deleted /results/ts-10GB-20-20-1024
Testing loop ended on Thu Nov 2 03:36:27 PDT 2017

```
