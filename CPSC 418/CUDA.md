## Data Parallelism
- When you see a for-loop:
	- Is the loop index used as an array?
	- are iterations independent?
	- if so: then the code is probably data-parallel code
- Misc
	- Runs well on GPUs because each element can be handled by a different thread
	- Good candidate for parallel techniques because available parallelism grows with problem size
	- Compared with task parallelism where the problem is divided into the same number of tasks

## GPU Architecture Features
- GPUs are SIMD machines
- lock step execution of pipelines
- deep pipelines, breaking instructions into small steps allows simple hardware to perform well
- each instruction must go all the way through the pipeline before another instruction can use the result
- typically 9-100+ SIMD processors where each processor has 32-128 pipelines

### Example: RTX 3090
- 5248 cuda cores
	- each can perform 4 FP or 3FP+1INT OPs per cycle
	- `__host__`

## Cuda Program Structure
- Host function
	- run on the CPU, in CUDA C these look like normal functions
- Global functions
	- Called by host CPU
	- executed on GPU
	- `__global__`
- 
- ![[Screenshot 2026-03-02 at 15.48.44.png]]