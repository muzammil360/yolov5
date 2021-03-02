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


# Getting custom layer output 
Simply pass list of intermediate layer indexes to the model. Afterwards, call `getIntermediateOutput` method.
You will get a list of all intermediate layers output. Those which do not exist in `save_idx`, will have `None` corresponding to them.
```
pred = model(img, augment=opt.augment, save_idx=[0, 10, 23])[0]
outlist = model.getIntermediateOutput()

# print the intermediate output
print("\n")
for out in outlist:
    if out is not None:
        print(out.shape)
```

