# Learning-based schemes
These schemes are implemented using Tensorflow. We support QAM4, QAM16 and QAM64 modulations. Number of transmit and receive anttenas can be set using ``--x-size`` and ``--y-size``, respectively. The range of training and test signal-to-noise ratio (SNR) is set with ``--snr-min`` and ``--snr-max`` arguments. Please use ``--data`` flag in order to specify using specific channels dataset. Not feeding this flag is interpreted for independent and identically distributed Gaussian channels.

## Offline training
For training MMNet-iid you can use:
```
python offlineTraining.py  --x-size 16 --y-size 64 --snr-min 2 --snr-max 7 --layers 10 -lr 1e-3 --batch-size 500 --train-iterations 10000 --mod QAM_4  --test-batch-size 5000 --linear MMNet_iid --denoiser MMNet --test-every 100
```

## Online training
For online training algorithm run:
```
python onlineTraining.py  --x-size 32 --y-size 64 --snr-min 10 --snr-max 15 --layers 10 -lr 1e-3 --batch-size 500 --train-iterations 1000 --mod QAM_4  --test-batch-size 5000 --linear MMNet  --denoiser MMNet --data --channels-dir path/to/channels --output-dir path/to/save/results
```
