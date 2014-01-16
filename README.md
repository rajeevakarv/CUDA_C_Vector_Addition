Instruction
Edit the code in the code tab to perform the following:

Allocate device memory

Copy host memory to device

Initialize thread block and kernel grid dimensions

Invoke CUDA kernel

Copy results from device to host

Free device memory

Write the CUDA kernel

Instructions about where to place each part of the code is demarcated by the //@@ comment lines.

Suggestions
The system’s autosave feature is not an excuse to not backup your code and answers to your questions regularly.

If you have not done so already, read the tutorial

Do not modify the template code provided – only insert code where the //@@ demarcation is placed

Develop your application incrementally

Do not wait until the last minute to attempt the lab.

If you get stuck with boundary conditions, grab a pen and paper. It is much easier to figure out the boundary conditions there.

Implement the serial CPU version first, this will give you an understanding of the loops

Get the first dataset working first. The datasets are ordered so the first one is the easiest to handle

Make sure that your algorithm handles non-regular dimensional inputs (not square or multiples of 2). The slides may present the algorithm with nice inputs, since it minimizes the conditions. The datasets reflect different sizes of input that you are expected to handle

Make sure that you test your program using all the datasets provided (the datasets can be selected using the dropdown next to the submission button)

Check for errors: here is an example function of a macro wbCheck that you can use to check for errors while programming CUDA:

#define wbCheck(stmt) do {                                                    \
        cudaError_t err = stmt;                                               \
        if (err != cudaSuccess) {                                             \
            wbLog(ERROR, "Failed to run stmt ", #stmt);                       \
            wbLog(ERROR, "Got CUDA error ...  ", cudaGetErrorString(err));    \
            return -1;                                                        \
        }                                                                     \
    } while(0)
An example usage is wbCheck(cudaMalloc(...))
