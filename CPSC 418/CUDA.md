## Data Parallelism
- When you see a forloop:
	- Is the loop index used as an array?
	- are iterations independent?
	- if so: then the code is probably data-parallel code
- Misc
	- Runs well on GPUs because each element can be handled by a different thread
	- good candidate for parallel techniques because available parallelism grows with problem size
	- compared with task parallelism where the problem is divided into the same number of tasks