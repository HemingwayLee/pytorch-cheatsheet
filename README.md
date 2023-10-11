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
