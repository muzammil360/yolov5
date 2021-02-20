# Installation
```
git clone https://github.com/muzammil360/yolov5.git  # clone repo
cd yolov5
python3 -m pip install -r requirements.txt  # install dependencies
python3 -m pip install wandb  

wandb login  # use 'wandb disabled' or 'wandb enabled' to disable or enable
```
When asked for the API key, enter: `87a1027c5e7f78b4ea3abfb0cb3429fd969eb4aa`. 

# Training

```
python3 train.py --data coco.yaml --cfg yolov5s.yaml --weights '' --batch-size 32
```

**NOTE**: If `--batch-size` throws OOM (Out of Memory) error, then reduce it by half.




