# pytorch-cheatsheet


# Tips
* UserWarning: Creating a tensor from a list of numpy.ndarrays is extremely slow
  * Slow 
```
torch.tensor([1, 2, 3])
```
  
  * Better
```
torch.tensor(np.array([1, 2, 3]))
```
   


