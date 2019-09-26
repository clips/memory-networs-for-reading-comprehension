# Memory networks for machine reading comprehension
This repository contains a pytorch implementation of end-to-end memory networks (MemNNs) for machine reading comprehension. The implementation is based on this [repository](https://github.com/uditsaxena/examples/tree/master/memory_network_n2n).

## Requirements
The code was run using Python 3.5, and [pytorch](http://pytorch.org/) v0.4.1.

## Usage
Train and evaluate a window-based model on the NE part of the CBT dataset: 
```
python3.5 main.py --mode win --train 1 --lr 0.001 --hops 1 --eval 1 --data-dir CBTest/data/ --ent-setup ent --cuda 1 --epochs 20 --log-epochs 1 --dataset cbt --memory-size 105 --embed-size 100 --win-size-kv 2 --dataset-part NE --exclude-unseen-ans 0
```

To train on CliCR, first [request](https://github.com/clips/clicr) the dataset, then:
```
python3.5 main.py --mode win --train 1 --lr 0.001 --hops 1 --eval 1 --data-dir clicr/ --ent-setup ent --cuda 1 --epochs 10 --log-epochs 1 --dataset clicr --memory-size 300 --embed-size 100 --win-size-kv 2 --exclude-unseen-ans 0 --anonymize
```

See `main.py` for the full list of options.
