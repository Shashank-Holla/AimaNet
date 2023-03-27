# AimaNet

To run the model on Carbonate machine.

1. Clone repo

```
git clone https://github.iu.edu/sholla/AimaNet.git
```

2. Move into AimaNet folder. Copy input and output file. File should be named as input_numpy.npy and output_numpy.npy


3. Run below command to start training.

```
python3 main.py --epochs 2 --batch_size 3 --train_split_index 132720
```

4. a) Run training on seperate 78 files

```
python3 mainSeperate78.py --data_path ./UBFC-wb-separate --epochs 24 --batch_size 6
```


