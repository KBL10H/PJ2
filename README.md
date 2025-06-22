<h3 id="3">Project 2. Train a Network on CIFAR-10</h3>

- This project aims to: 1. train neural network models on CIFAR-10 to optimize performance; 2. analyze how BN help optimization by conducting 3 experiments on VGG-A with and without BN.

- In part 1, to run the code, you may first determine the parameters and the model you want to train, and then copy the following code to the terminal.

```shell
# All models in './models' except FastResNet9, e.g.: LeNet
CUDA_VISIBLE_DEVICES=0,1,2,3 python main.py --model=LeNet --batch-size=128 --lr=0.1 --max-epoch=200

# FastResNet9
python main_fastresnet9.py --max-epoch=200
```

- The model with best performance is **GeResNeXt29_8x64d**, whose test accuracy reaches **96.88%**.

| Model                 | Nparams | Test Acc (200 epochs) | Time (s/epoch) |
| --------------------- | ------- | --------------------- | -------------- |
| LeNet                 | 0.06M   | 76.32%                | 2.76           |
| AlexNet               | 2.47M   | 77.82%                | 3.05           |
| ResNet18              | 11.17M  | 95.29%                | 21.96          |
| ResNet34              | 21.28M  | 95.58%                | 51.59          |
| ResNet50              | 23.52M  | 94.66%                | 79.24          |
| ResNeXt29_2x32d       | 2.30M   | 94.02%                | 40.15          |
| ResNeXt29_2x64d       | 9.13M   | 94.45%                | 85.47          |
| ResNeXt29_32x4d       | 4.77M   | 95.03%                | 78.08          |
| DenseNet100_bc        | 0.77M   | 95.20%                | 74.25          |
| DenseNet121           | 6.96M   | 95.35%                | 89.91          |
| WideResNet16x8        | 10.97M  | 95.18%                | 42.83          |
| WideResNet28x10       | 36.49M  | 96.63%                | 158.49         |
| **GeResNeXt29_8x64d** | 36.33M  | **96.88%**            | 439.67         |
