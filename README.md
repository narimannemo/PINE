# PINE: Parallel Interpreter Network

## Introduction
**PINE** (**P**arallel **I**nterpreter **NE**twork) is a novel interpretability framework which provides decent interpretations of DNNs in order to make the reasoning behind decisions of a black-box model become transparent to users.

## How PINE works?
PINE's structure consists of two paralell networks. The Main Model, which is the primary model we want to get interpreted, and the Interperter, which is an autoencoder network trains parallel to the main model and eventualy learns how the main model predicts. 
![image](https://user-images.githubusercontent.com/19486359/107159400-a3878080-6987-11eb-9075-bef8251559a4.png)

Due to the loss functions inside PINE, after each propagation through the training process, the interpreter learns more on how to generate an accurate interpretation based on Main Model's input.  

<table>
    <thead>
        <tr>       
            <th align="left"><img src="https://user-images.githubusercontent.com/19486359/107769671-3e89ad00-6d30-11eb-801e-3b606cea920b.png"></th>
            <th align= "center"> &rarr; PINE &rarr; </th>
            <th align="right"><img src="https://raw.githubusercontent.com/narimannemo/pine/main/mnist_pine.gif">
            </th>
        </tr>
    </thead>
</table>


## Getting Startd
### Console
**1.** Donwnload PINE repository and redirect to its folder using the code below in your terminal:
```bash
git clone https://github.com/narimannemo/pine.git
cd pine
```
**2.** Run main.py by filling the required arguments:

Arguments | main_model | interpreter | dataset 
--- | --- | --- | --- 
Options | mnist_model_no1, cifar10_model_no1| mnist_interpreter_no1, cifar10_interpreter_no1 | mnist, cifar10

**For example:**
```bash
python main.py --main_model mnist_model_no1  --interpreter mnist_interpreter_no1 --dataset mnist --epoch 10 --batch_size 64
```
**Note:** In the code above, the required fields are filled with examples. There are two required arguments to fill out: The `--main_model` in which you should select the main model you want get interpreted, from the options provided in the main_models.py. And the `--interpreter` in which you should select the interpreter you want to interpret the main model from the options provided in the `interpreters.py`.

**3.** Find the results in the `results` folder.

### Jupyter Notebook
You can also run PINE using the provided Jupyter Notebooks in notebooks folder. There are two folders of `PINE (TF 1x Compatible)` for those who are more
convenient with TensorFlow 1 and `PINE (TF 2x)` for those prefer TensorFlow 2. However, we recommend you to go with PINE (TF 1x Compatible). We will give you an award if you figure out why! ;) 

### Costumizing the Main Model and the Interpreter
You can easily add your costumized Main Models and Interpreters in the `main_models.py` and `interpreters.py` files.
## Experiments
### MNIST
After experimenting PINE on an MNIST model, the results below have achieved: (The pictures in the even columns are the interpretations of the pictures in the odd columns.)

![image](https://user-images.githubusercontent.com/19486359/107133665-a11f1b00-68e2-11eb-99ed-33839a32c844.png)
### CIFAR-10
<table>
    <thead>
        <tr>       
            <th align="left"><img src="https://user-images.githubusercontent.com/19486359/108003990-6442da80-6fec-11eb-89b3-55e94b16b561.png"></th>
            <th align= "center"> &rarr; PINE &rarr; </th>          
            <th align="right"><img src="https://raw.githubusercontent.com/narimannemo/pine/main/cifar10_mask.gif"></th>          
        </tr>
    </thead>
</table>

## TODO
- [x] Add PINE results on CIFAR-10 
- [ ] Add PINE visualizations
- [ ] Add comparison with other Interpretability Methods

## Contributing
If you like to contribute or add your experiments please go ahead and open an issue or submit a pull request.
