Go is unusual in that it can increase the size of a stack while the program is running. This is because each goroutine has its own stack and goroutines are managed by the Go runtime, not by the underlying operating system. This has advantages (Go stacks start small and use less memory) and disadvantages (when the stack needs to grow, all data on the stack needs to be copied, which is slow). It's also possible to write worst-case-scenario code that causes that stack to grow and shrink over and over.