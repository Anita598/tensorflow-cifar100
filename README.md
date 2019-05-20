# tensorflow-cifar100

Tensorflow implementation on cifar100.

All models have achieved high accuracy (> 0.7).


### Usage

Requirements:

1. tensorflow-gpu=1.11.1
2. tensorlayer=1.11.0

download dataset:

[Download Website](https://www.cs.toronto.edu/~kriz/cifar.html )

download repo:

```
$ git clone https://github.com/Ecohnoch/tensorflow-cifar100
```

train:

```
$ python3 -u train.py train --batch_size 64 --epoch 200 --network resnet50 --opt momentum --train_path /data/ChuyuanXiong/up/cifar-100-python/train --test_path /data/ChuyuanXiong/up/cifar-100-python/test
```

params:

* batch_size: 64 default
* epoch: 200 is best
* network: resnet18/resnet50/resnet110/resnet152/seresnet50/seresnet110/seresnet152/densenet121/densenet169/densenet161/densenet201
* opt: adam/momentum/nesterov
* train_path:  your train path
* test_path: your test path

Have Done
```
resnet18
resnet34
resnet50
resnet110
resnet152
seresnet50
seresnet110
seresnet152
densenet121
densenet169
densenet201

# TODO
preresnet
resnext
mobilenet
```


test:

```
python3 -u train.py test --network resnet18 --test_path '/data/ChuyuanXiong/up/cifar-100-python/test' --ckpt 'params/resnet18/Speaker_vox_iter_58000.ckpt'
```

params:

* network: resnet18/resnet50
* test_path: your test path
* ckpt:  your pre-trained model. You can try the [\$THIS_REPO/params/resnet18/Speaker_vox_iter_58000.ckpt]




### Results

dataset | network | top1 acc | epoch (lr=0.1) | epoch (lr=0.02) |  batch_size | initializer |  warmup |   weight decay|
--------|---------|---------|-----------------|----------------|--------------|-------------|---------|--------------|
cifar100| resnet18   | 0.740  |   60          | > 60           |    128       | msra       |     0    |        0
cifar100| densenet169| 0.743 |  60            | > 60           |    64        | orth       |     1    |      5e-4     


// TODO

* resnext50
* resnext101
* resnext152
* preresnet18
* ...



### References

1. [pytorch-cifar100](https://github.com/weiaicunzai/pytorch-cifar100)