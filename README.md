# CS6910_Assignment_2

Instruction to run the code:
Every colab files need to be run cell by cell...!

Question 2A:Below sweep config is used to train the model using wandb
Grid search is used in this sweep:
sweep_config1 = {
  'name': 'sweep1',  
  'method': 'grid',
  'parameters': {
        
        'filters': {
            'values': ['inc_dec','dec_inc','all_64','all_32','inc','dec']
        },
        'fc_size':{
            'values':[128]
        },
        'batchnorm':{
            'values':['yes']
        },
        'augmentation':{
            'values':['yes','No']   
        },
        'droprate':{
            'values':[0.4,0.5]
        }
           
    }

}

Random search is used in this sweep:
sweep_config2 = {
  'name': 'sweep2',  
  'method': 'random',
  'parameters': {
        
        'filters': {
            'values': ['inc_dec','dec_inc','all_64','all_32','inc','dec']
        },
        'fc_size':{
            'values':[128]
        },
        'batchnorm':{
            'values':['yes']
        },
        'augmentation':{
            'values':['yes','No']   
        },
        'droprate':{
            'values':[0.4,0.5]
        }
           
    }

}

Best model config is as below. The hyperparameter can be changed according to requirements:
config_defaults={
    'filters':'inc',
    'fc_size':256,
    'batchnorm':'yes',
    'augmentation':'no',
    'droprate':0.3
}

Question 2B: Below sweep config is used to train the model using wandb
sweep_config = {
  'name': 'sweep2B5b',  
  'method': 'grid',
  'parameters': {
        
        
        'fc_size':{
            'values':[32,64,128]
        },
        'batchnorm':{
            'values':['yes','no']
        },
        'augmentation':{
            'values':['yes','no']   
        },
        'droprate':{
            'values':[0.3,0.4,0.5]
        },
        'pre_train':{
            'values':['inceptionv3','inceptionresnetv2','Xception','resnet50']
        }

           
    }

}

***This sweep config is used for best model. you can change the hyperparameters using this xml.***

#this config gives best val accuracy
config_defaults={
    'fc_size':32,
    'batchnorm':'yes',
    'augmentation':'yes',
    'droprate':0.3,
    'pre_train':'inceptionv3'
}
****Need to uncomment the below code and change the entity name corresponding to your wandb userid ***** 
#Ignore this and proceed
#sweep_id=wandb.sweep(sweep_config,entity='rashmipathak',project='assignment_2B')
#wandb.agent(sweep_id, PreTrain)

Question2C. step1. Please download coco.names ,yolov3.cfg and yolov3.weights from below drive:
https://drive.google.com/drive/folders/1JOprKM7oQvzoaYeqeV8o6YdjTPRUR_5m?usp=sharing

2. place above files in your folder of google drive and give those path in the YOLO1.ipynb file to the corresponding arguments and again you can download  paris.mp4 video from the given drive or can use any other video for object detection...! 
