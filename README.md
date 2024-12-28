# Caption


Requirements:

```
pip install -r requirements.txt
```

- Python           3.9.13
- Pytorch
- Triton           3.0.0
- HuggingFace Hub
- Numpy            1.26.4
- Pillow



# Model Description


This Model uses pretrained EfficientNet5 for feature extraction and GPT-2 architecture (from scratch) is used as decoder.

Note: This is not a proper working model because it is trained on 16384 steps rather than 20k - 90k steps. "validation_output.txt" have results of training. Each line displays an output for each step.



Model Specification:

- Sequence Length = 128
- Token Dimension(dmodel) = 384
- Image size (after transformation) = 256 x 224
- Number of Decoder Layers = 3
- Num of Decoder Heads = 12
- Batch Size = 64
- Optimzer = AdamW


This model uses decay rate and grad clipping through normalization to reduce shock while learning.


Features used to speed up training:

- Distributed Data Parallel
- Gradient Clipping
- Torch Compile
- Fused Adam
- FP16

