## installation for windows

[pip_install](https://www.tensorflow.org/install/pip)

1- install [anaconda](https://docs.anaconda.com/anaconda/install/windows/) 

2- open CMD or conda prompt, use conda's prompt as it directly  points towards the base environment of conda 

3- create your own Environment run the following command

```bash
conda create --name tfgpu python=3.10
conda activate tfgpu 
```
4- installing cudatoolkit package


```bash
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
```
you can install another version of CUDA but it has to be compatible with CUDNN

5- install tensorflow 

```bash 
python -m pip install tensorflow
```

6- make sure it's running 
```bash 
python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
```
if it worked properly you should see something like this 
```bash 
[PhysicalDevice(name='/physical_device:GPU:0', device_type='GPU')]
```
if it installed CPU version of tensorflow you should see something like this 
```bash 
[]
```

7- install all the packages needed inside tools.yml 
 > you can edit the file at your own prefrence
move tools.yml to the root directory of your conda environment 
for example 
> C:\Users\DELL>
```bash 
conda activate tfgpu
conda env update --file tools.yml
```

## Set up the environment 
for VSCODE 
- change kernel to environment kernel [tfgpu python3.10.8] 
- ![](img2.png)
- it will ask for ipython and other dependencies, just allow all their installation and you're ready to go 
- in case if you want to to install other libraraies
  
```bash
conda activate tfgpu
pip install <package>

```

for jupyter 
- install jupyter from Anaconda Navigator 
- ![](img1.png)
- load ipython kernel and you're ready to go 
- to install package just do it normally in a cell while tfpgu kernel is running
```bash
pip install <package>
```
