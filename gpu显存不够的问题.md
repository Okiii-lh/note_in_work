### 问题描述

E tensorflow/stream_executor/cuda/cuda_dnn.cc:352] Could not create cudnn handle: CUDNN_STATUS_INTERNAL_ERROR

### 解决办法

使用如下代码控制使用的显存数量

```python
config = tf.ConfigProto(allow_soft_placement=True)
config.gpu_options.pre_process_gpu_memory_fraction=0.4
config.gpu_options.allow_growth=True
```

