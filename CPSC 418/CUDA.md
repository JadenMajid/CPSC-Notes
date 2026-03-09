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

## Threads Grids and Blocks

- SM: Streaming multiprocessor
	- two dimensions of parallelism
		- Deep pipelining
			- EX1...EXN
				- Make pipeline simple, energy efficient and fast
				- no bypasses
		- SIMD
			- Multiple pipelines execute same instructions on the same data
	- Lots of threads
		- to keep a SM fully utilized, we need ~1 thread for each $|Pipeline Stages|\times |Pipelines|$
		- Compiler can reduce this a bit by exploiting instruction level parallelism
- Threads, Warps, Blocks
	- Threads are interleaved so that other threads dispatch while waiting for results
	- CUDA programs have thousands of threads
	- Warps are groups of threads on each pipeline of a SIMD core 
		- up to 1024 threads, but normally 32
	- Blocks are groups of threads(up to 1024), 32 warps of 32 threads each are in a "thread block"
	- a cuda kernel is an array of blocks called a grid


| Grouping | Description                                                                                                                                                                                           |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Thread   | Individual instruction pipeline                                                                                                                                                                       |
| Warp     | Group of threads that are run together(lock step). Max size determined by the hardware.                                                                                                               |
| Block    | Array of warps that are run together(not necessarily lock step). Must have all execution resources available before it is launched. Switching between threads within a block is done by the hardware. |
| Grid     | Array of blocks, up to $2^{31}$ in x dim, $2^{16}$ in y and z dims. Can be arranged in 1D, 2D, or 3D. Different blocks can be run on different machines(multiple GPUs)                                |
|          |                                                                                                                                                                                                       |
|          |                                                                                                                                                                                                       |
|          |                                                                                                                                                                                                       |
## Kernels
- Launching a Kernel
	- we can launch ```__global__ void kernel_fun(args)``` with:
		- `kernel_fun<<dimGrid, dimBlock>>>(actuals)`
			- dimGrid and dimBlock can be `dim1(X)`, `dim2(X,Y)`, `dim3(X,Y,Z)`
			- DimBlock needs to be $<1024$ total
			- Index of thread can be found with builtins
				- `gridDim.x`,`gridDim.y`,`gridDim.z`
				- `blockDim.x`,`blockDim.y`,`blockDim.z`
				- `blockIdx.x`,`blockIdx.y`,`blockIdx.z`,
				- `threadIdx.x`,`threadIdx.y`,`threadIdx.z`
				- indices are $0\le blockIdx.x < gridDim.x$
			- 
	- 