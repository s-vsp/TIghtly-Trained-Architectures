# Tightly Trained Architectures
Methodologies overview, used datasets and neural networks architectures.

## SmallNORB
* **Dataset Details**
    - Number of classes = 5
    - Train Size = 19,440
    - Validation Size = 4,860
    - Test Size = 24,300

### VGG16
- Augmentations
    - Train Augmentations
        - RandomResizedCrop(size=(224,224), scale=(0.8, 1.0))
        - RandomRotation(degrees=30)
        - RandomHorizontalFlip()
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)

- Training Details
    - Total parameters: 135,309,509
    - Trainable parameters: 1,050,757
    - Batch Size = 16
    - Epochs = 35
    - Initial Learning Rate = 1e-2
    - Momentum = 0.9
    - Weight Decay = 5e-4
    - Optimizer: SGD
    - Learning Rate Scheduler: ReduceLROnPlateau
    - Loss: Negative Log-Likelihood

- **Test Accuracy = 91.23%**

### Improved ResNet50
- Augmentations
    - Train Augmentations
        - RandomResizedCrop(size=(224,224), scale=(0.8, 1.0))
        - RandomRotation(degrees=30)
        - RandomHorizontalFlip()
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)

- Training Details
    - Total parameters: 24,027,589
    - Trainable parameters: 528,965
    - Batch Size = 16
    - Epochs = 100 (61 completed)
    - Initial Learning Rate = 5e-3
    - Momentum = 0.9
    - Weight Decay = 1e-2
    - Optimizer: SGD
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Negative Log-Likelihood

- **Test Accuracy = 89.1975%**

### SwinTransformer
- Augmentations
    - Train Augmentations
        - Resize(size=(224, 224))
        - RandAugment(num_ops=2, magnitude=9)
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
        - RandomErasing(p=0.25)
        - CutMix / MixUp
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)

- Training Details
    - Total parameters: 87,002,813
    - Trainable parameters: 265,861
    - Batch Size = 16
    - Epochs = 80 (7 completed)
    - Initial Learning Rate = 5e-3
    - Weight Decay = 5e-2
    - Optimizer: SGD
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Negative Log-Likelihood

- **Test Accuracy = 91.7407%**

### ConvNeXt
- Augmentations
    - Train Augmentations
        - Resize(size=(224, 224))
        - RandAugment(num_ops=2, magnitude=9)
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
        - RandomErasing(p=0.25)
        - CutMix / MixUp
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)

- Training Details
    - Total parameters: 87,826,053
    - Trainable parameters: 265,861
    - Batch Size = 16
    - Epochs = 30
    - Initial Learning Rate = 5e-5
    - Weight Decay = 1e-8
    - Optimizer: AdamW
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Cross Entropy (label-smoothing=0.1)

- **Test Accuracy = 92.50%**

### ConvNeXt V2
- Augmentations
    - Train Augmentations
        - Resize(size=(224, 224))
        - RandAugment(num_ops=2, magnitude=9)
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
        - RandomErasing(p=0.25)
        - CutMix / MixUp(p=0.8)
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=0.485, std=0.229)

- Training Details
    - Total parameters: 87,952,389
    - Trainable parameters: 265,861
    - Batch Size = 16
    - Epochs = 50
    - Initial Learning Rate = 6.25e-3
    - Weight Decay = 0.05
    - Optimizer: AdamW
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Cross Entropy (label-smoothing=0.1)

- **Test Accuracy = 92.53 %**

## StreetsAndHouses

### VGG16

### Improved ResNet50
- Augmentations
    - Train Augmentations
        - RandomResizedCrop(size=(224,224), scale=(0.8, 1.0))
        - RandomRotation(degrees=30)
        - RandomHorizontalFlip()
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])

- Training Details
    - Total parameters: 24,035,917 
    - Trainable parameters: 527,885 
    - Batch Size = 16
    - Epochs = 100
    - Initial Learning Rate = 5e-3
    - Momentum = 0.9
    - Weight Decay = 1e-2
    - Optimizer: SGD
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Negative Log-Likelihood

- **Test Accuracy = 49.5595%**

### SwinTransformer
- Augmentations
    - Train Augmentations
        - Resize(size=(224, 224))
        - RandAugment(num_ops=2, magnitude=9)
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
        - RandomErasing(p=0.25)
        - CutMix / MixUp
    - Validation Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
    - Test Augmentations:
        - Resize(size=(224, 224))
        - ToTensor()
        - Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])

- Training Details
    - Total parameters: 87,008,965
    - Trainable parameters: 265,741
    - Batch Size = 16
    - Epochs = 80
    - Initial Learning Rate = 5e-3
    - Weight Decay = 5e-2
    - Optimizer: SGD
    - Learning Rate Scheduler: CosineAnnealingLR
    - Loss: Negative Log-Likelihood

- **Test Accuracy = 62.6872%**

### ConvNeXt

### ConvNeXt V2
