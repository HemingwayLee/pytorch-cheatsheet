# pytorch-cheatsheet


# Tips
* UserWarning: Creating a tensor from a list of numpy.ndarrays is extremely slow
```python
# Slow 
torch.tensor([1, 2, 3])
# Better
torch.tensor(np.array([1, 2, 3]))
```
   
* Run with docker on GPU machine
```
docker run -it --rm --gpus all ...
```

* Size of `runtime` images < size of `devel` images
  * runtime: extends the base image by adding all the shared libraries from the CUDA toolkit. Use this image if you have a pre-built application using multiple CUDA libraries.
  * devel: extends the runtime image by adding the compiler toolchain, the debugging tools, the headers and the static libraries. Use this image to compile a CUDA application from sources.

* Check if run with GPU 
```
import torch
torch.cuda.is_available()
```

  * If it show `False`
    * run docker with `--gpus all` options
    * install driver by executing `sudo apt install nvidia-driver-410`
    * install cuda version of pytorch with `pip`
      * `pip3 install torch==1.10.0+cu113 torchvision==0.11.0+cu113 --extra-index-url https://download.pytorch.org/whl/cu113` 


* Check if installed pytroch cpu only
```
$> conda list
pytorch                   1.13.1          cpu_py310hd11e9c7_1    conda-forge
```