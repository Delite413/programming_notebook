
|  | Unbuffered, Open | Unbuffered, Closed | Buffered, Open | Buffered, Closed | Nil |
| ---- | ---- | ---- | ---- | ---- | ---- |
| Read | Pause until somthing is written | Return zero value (use comma ok to see if closed) | Pause if buffer is empty | Return a remaning value in the buffer; if the buffer is empty, return zero value (use comma ok to see if closed) | Hang forever |
| Write | Pause until something is read | PANIC | Pause if buffer is full | PANIC | Hang forever |
| Close | Works | PANIC | Works, remaining values still there PANIC | PANIC | PANIC |





