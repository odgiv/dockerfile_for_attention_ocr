This is a repository for building and running Attention-OCR on docker container. 

The original project repository is here: https://github.com/da03/Attention-OCR

In the data directory volume, we store data for training, testing and pretrained model. Those files include:

Test data:
```
wget http://www.cs.cmu.edu/~yuntiand/evaluation_data.tgz
tar zxf evaluation_data.tgz
```

Pretrained model:
```
wget http://www.cs.cmu.edu/~yuntiand/model.tgz
tar zxf model.tgz
```

Sample data for training:
```
wget http://www.cs.cmu.edu/~yuntiand/sample.tgz
tar zxf sample.tgz
```
The port 8887 should be open on host machine for jupyter notebook.

### Training and Testing commands:
Assuming you're in Attention-OCR directory.
```
python src/launcher.py --phase=test --visualize --data-path=/home/sg/data/evaluation_data/svt/test.txt --data-base-dir=/home/sg/data/evaluation_data/svt --log-path=log.txt --load-model --model-dir=/home/sg/data/model --output-dir=/home/sg/data/results

python src/launcher.py --phase=test --visualize --data-path=evaluation_data/evaluation_data.txt --data-base-dir=evaluation_data --log-path=log.txt --load-model --model-dir=model --output-dir=results
```
