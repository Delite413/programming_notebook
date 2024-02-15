The garbage collector looks at the heap size at the end of a garbag-collection cycle and uses the formula

```go
CURRENT_HEAP_SIZE + CURRENT_HEAP_SIZE*GOGC/100
```

to calculate the heapsize that needs to be reached to trigger the next garbage-collection cycle.

>[!note]
>The GOGC heap size calculation is a little more complicated than just described. It takes into account not just the heapsize, but the sizes of all stacks of all the goroutines and the memory set aside to hold package-level variables. Most of the time, the heap size is far bigger than the size of these other memory areas, but in some situations they do have an effect.

By default, GOGC is set to 100, which means that the heap size that triggers the next collection is roughly double the heap size at the end of the current collection.