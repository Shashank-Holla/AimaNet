# AimaNet

To run the model on Carbonate machine.

1. Clone repo

```
git clone https://github.iu.edu/sholla/AimaNet.git
```

2. Move into AimaNet folder. Copy input and output file. File should be named as input_numpy.npy and output_numpy.npy

3. On terminal, run the following commands to load deep learning libraries.

```
module load deeplearning/2.10.0

```

4. To get terminal to run our model training , execute below command. This creates interactive job

```
srun -p gpu -A c00041 --gpus-per-node v100:1 --pty bash
```

5. Run below command to start training.

```
python3 main.py --epochs 2 --batch_size 3 --train_split_index 132720
```

5. a) Run training on seperate 78 files

```
python3 mainSeperate78.py --data_path ./UBFC-wb-separate --epochs 24 --batch_size 6
```

6. To submit job

```
sbatch run.sh
```
