![Logo](./images/ZazuML.jpeg)
<br/><br/>   

This is an open-source AutoML project for instance detection. Currently this project contains a model finder, hyper-parameter tuner, 
and trial manager all wrapped up in one synchronous end to end program. The input to this program is a dataset, the output is a trained 
model with auto-optimized hyper parameters, ready to run inference, simple as that.

**NOTE**: This project is still under development, clone and play, we appreciate and encourage
pull requests and feedback from the community. Help us make this tool awesome.

## *Why ZazuML?*
You might be building an ML pipeline to avoid model performance degeneration, or maybe you're just too lazy to download, 
debug, and tune your own model. Either way, you shouldn't be focusing your efforts on simple things like detection. There's
a whole world out there for you to explore, give your hand at trajectory prediction or action recognition and let *ZazuML*
free you up from the boring stuff.

To learn more, take a look [Under The Hood of ZazuML](./UNDERTHEHOOD.md)

## Getting started

First thing to do is . . .  

### *pull & run the Docker Image*
```
docker run --rm -it --init  --runtime=nvidia  --ipc=host  -e NVIDIA_VISIBLE_DEVICES=0 buffalonoam/zazu-image:0.2 bash
```
Be sure to update the nvidia-devices flag!

### *clone the repo*
```
git clone https://github.com/dataloop-ai/ZazuML.git
cd ZazuML
git clone https://github.com/dataloop-ai/zoo.git
```

### *download tiny coco dataset*
```
mkdir ../data
cd ../data
git clone https://github.com/dataloop-ai/tiny_coco.git
```

### *Begin model & hyper-parameter search*
```
python zazu.py --search
```
### *Begin training*
```
python zazu.py --train
```
### *predict*
```
python zazu.py --predict
```

### *Launch search on Kubernetes via our Dataloop engine* (this feature is not ready yet)
```
python zazu.py --search --remote
```

Now that you've got the gist of it, feel free to read up on [Configuring ZazuML](./CONFIGURINGZAZU.md)

## TO DO

- Implement HyperBand instead of random search
- Improve search space
- NAS to replace some of the HP search
- Intelligent Losses to replace some of the HP search

## Contact

If you're interested in becoming a collaborator or just have some questions, feel free to contact me at:

WeChat: BuffaloNoam   
Line: buffalonoam   
WhatsApp: +972524226459   

## Refrences

Some of the code was influenced by [keras-tuner](https://github.com/keras-team/keras-tuner)