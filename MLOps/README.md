# Overview

## Installing
Go to directory containing setup.py
pip install -e .
If want to create a wheel build and .tar that you can share with someone do,
python setup.py sdist bdist_wheel


## Unit Testing
Run all commands from `Production` directory
e.g. `python -m pytest -s ./test/`  
     `python ./src/train.py`  
	 `python ./test/test_train.py`
			
## Training
python ./src/train.py --hiddenDim 128 --numLayers 2 --decNumLayers 4 --numHeads 4 --batchSize 24 \
--numEpochs 100 --lr 1e-3 --dropout 0.0 --savedModelBaseName 'MODEL7' --modelType 'Seq2SeqwithXfmrMemEfficient' \ 
--loadBestModel False --beamSize 0 --configPath './config.yaml'


## Inference
python ./src/inference.py --hiddenDim 128 --numLayers 2 --decNumLayers 4 --numHeads 4 \
--dropout 0.0 --inputTextFile 'inferenceData.json' --modelType 'Seq2SeqwithXfmrMemEfficient' \
--loadModelName 'MODEL7_step_20500.pth.tar' --beamSize 0 --configPath './config.yaml'