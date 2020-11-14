# Quick Start
1. Install the prerequisites
```
cuda 9.0
sudo apt-get install libboost-all-dev
```

```bash
conda create -n vidvrd python=2.7 
conda install cmake tensorflow-gpu=1.8.0 keras=2.1.6 tqdm ffmpeg=3.4 py-opencv
pip install dlib==19.3.1 --isolated
``` 

2. Download precomputed features, model and detected relations from [here](https://zdtnag7mmr.larksuite.com/file/boxusS8Z0kwEizoPPh5h7vx7Usf), and decompress the zipfile under the same folder as this repository.

3. Run `python evaluate.py vidvrd test relation ../vidvrd-baseline-output/models/baseline_relation_prediction.json` to evaluate the precomputed detected relations. Since a few wrong labels in the dataset were corrected after paper submission, the result is slightly different from the one reported in the paper. Some qualitative results can be found [here](http://mm.zl.io).


4. Run `python baseline.py --detect` to detect video visual relations using the precomputed model.

5. Run `python baseline.py --train` to train a new model by adjusting the hyperparameters in the script, based on the precomputed features.
