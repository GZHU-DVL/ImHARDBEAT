## Prerequisite

The code is implemented and tested on PyTorch. It runs on Python 3.6.9.

### PyTorch Version

* PyTorch 1.7.0

## Usage

The main functions are located in `main.py` file.

To generate a patch trigger using HardBeat, please use the following command:

   ```bash
   python3 main.py
   ```

The default dataset and model are CIFAR-10 and ResNet18. You can generate triggers for different model structures on other datasets by passing the arguments `--dataset [dataset]` and `--network [model structure]`. We have included four datasets (CIFAR-10, STL-10, SVHN, and GTSRB) and varoius model structures (ResNet, VGG, DenseNet, MoibleNet, etc.). Please place the datasets in `./data` folder and the model checkpoints in `./ckpt` folder.

To generate a trigger for a different class pair, please run:

   ```bash
   python3 main.py --pair 1-2
   ```

The argument `1-2` means generating a trigger that can flip the prediction of samples from class 1 to class 2.

You can use `--patch_size` to change the trigger size and `--query_limit` to limit the number of queries. The default trigger size is 7x7 and the number of queries is 50k.

### Model Functionality

To test the accuracy of a model, simply run:

   ```bash
   python3 main.py --phase test --dataset [dataset] --network [model structure]
   ```


