The rule as of Go 1.18 is to double the capacity of a slice the the current capacity is less than 256. A bigger slice increases by (current_capacity + 768) / 4. This slowly converges at 25% growth (a slice with a capacity of 512 will grow by 63%, but a slice with capacity of 4096 will grow by only 30%).