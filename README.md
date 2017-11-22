# SCA
This is a testing
# Enter your network definition here.
# Use Shift+Enter to update the visualization.
name: "scrlnet"
input: "data"
input_dim: 1
input_dim: 3
input_dim: 256
input_dim: 256
############# load from VGG-16 ################
layer {
  name: "conv1_1"
  type: "Convolution"
  bottom: "data"
  top: "conv1_1"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv1_1/bn"
  type: "BatchNorm"
  bottom: "conv1_1"
  top: "conv1_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu1_1"
  type: "ReLU"
  bottom: "conv1_1"
  top: "conv1_1"
}
layer {
  name: "conv1_2"
  type: "Convolution"
  bottom: "conv1_1"
  top: "conv1_2"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv1_2/bn"
  type: "BatchNorm"
  bottom: "conv1_2"
  top: "conv1_2"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu1_2"
  type: "ReLU"
  bottom: "conv1_2"
  top: "conv1_2"
}
layer {
  name: "pool1"
  type: "Pooling"
  bottom: "conv1_2"
  top: "pool1"
  pooling_param {
    pool: MAX
    kernel_size: 2
    stride: 2
  }
}
layer {
  name: "conv2_1"
  type: "Convolution"
  bottom: "pool1"
  top: "conv2_1"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 128
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv2_1/bn"
  type: "BatchNorm"
  bottom: "conv2_1"
  top: "conv2_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu2_1"
  type: "ReLU"
  bottom: "conv2_1"
  top: "conv2_1"
}
layer {
  name: "conv2_2"
  type: "Convolution"
  bottom: "conv2_1"
  top: "conv2_2"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 128
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv2_2/bn"
  type: "BatchNorm"
  bottom: "conv2_2"
  top: "conv2_2"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu2_2"
  type: "ReLU"
  bottom: "conv2_2"
  top: "conv2_2"
}
layer {
  name: "pool2"
  type: "Pooling"
  bottom: "conv2_2"
  top: "pool2"
  pooling_param {
    pool: MAX
    kernel_size: 2
    stride: 2
  }
}
layer {
  name: "conv3_1"
  type: "Convolution"
  bottom: "pool2"
  top: "conv3_1"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 256
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_1/bn"
  type: "BatchNorm"
  bottom: "conv3_1"
  top: "conv3_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_1"
  type: "ReLU"
  bottom: "conv3_1"
  top: "conv3_1"
}
layer {
  name: "conv3_2"
  type: "Convolution"
  bottom: "conv3_1"
  top: "conv3_2"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 256
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_2/bn"
  type: "BatchNorm"
  bottom: "conv3_2"
  top: "conv3_2"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_2"
  type: "ReLU"
  bottom: "conv3_2"
  top: "conv3_2"
}
layer {
  name: "conv3_3"
  type: "Convolution"
  bottom: "conv3_2"
  top: "conv3_3"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 256
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_3/bn"
  type: "BatchNorm"
  bottom: "conv3_3"
  top: "conv3_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_3"
  type: "ReLU"
  bottom: "conv3_3"
  top: "conv3_3"
}
layer {
  name: "pool3"
  type: "Pooling"
  bottom: "conv3_3"
  top: "pool3"
  pooling_param {
    pool: MAX
    kernel_size: 2
    stride: 2
  }
}
layer {
  name: "conv4_1"
  type: "Convolution"
  bottom: "pool3"
  top: "conv4_1"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_1/bn"
  type: "BatchNorm"
  bottom: "conv4_1"
  top: "conv4_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_1"
  type: "ReLU"
  bottom: "conv4_1"
  top: "conv4_1"
}
layer {
  name: "conv4_2"
  type: "Convolution"
  bottom: "conv4_1"
  top: "conv4_2"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_2/bn"
  type: "BatchNorm"
  bottom: "conv4_2"
  top: "conv4_2"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_2"
  type: "ReLU"
  bottom: "conv4_2"
  top: "conv4_2"
}
layer {
  name: "conv4_3"
  type: "Convolution"
  bottom: "conv4_2"
  top: "conv4_3"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_3/bn"
  type: "BatchNorm"
  bottom: "conv4_3"
  top: "conv4_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_3"
  type: "ReLU"
  bottom: "conv4_3"
  top: "conv4_3"
}
layer {
  name: "pool4"
  type: "Pooling"
  bottom: "conv4_3"
  top: "pool4"
  pooling_param {
    pool: MAX
    kernel_size: 2
    stride: 2
  }
}
layer {
  name: "conv5_1"
  type: "Convolution"
  bottom: "pool4"
  top: "conv5_1"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_1/bn"
  type: "BatchNorm"
  bottom: "conv5_1"
  top: "conv5_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_1"
  type: "ReLU"
  bottom: "conv5_1"
  top: "conv5_1"
}
layer {
  name: "conv5_2"
  type: "Convolution"
  bottom: "conv5_1"
  top: "conv5_2"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_2/bn"
  type: "BatchNorm"
  bottom: "conv5_2"
  top: "conv5_2"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_2"
  type: "ReLU"
  bottom: "conv5_2"
  top: "conv5_2"
}
layer {
  name: "conv5_3"
  type: "Convolution"
  bottom: "conv5_2"
  top: "conv5_3"
  param {
    lr_mult: 1
    decay_mult: 1
  }
  param {
    lr_mult: 2
    decay_mult: 0
  }
  convolution_param {
    num_output: 512
    pad: 1
    kernel_size: 3
    stride: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_3/bn"
  type: "BatchNorm"
  bottom: "conv5_3"
  top: "conv5_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_3"
  type: "ReLU"
  bottom: "conv5_3"
  top: "conv5_3"
}
########### The Side-out ASPP #########
#conv5_3
layer {
  name: "conv5_3_1"
  type: "Convolution"
  bottom: "conv5_3"
  top: "conv5_3_1"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_3_1/bn"
  type: "BatchNorm"
  bottom: "conv5_3_1"
  top: "conv5_3_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_3_1"
  type: "ReLU"
  bottom: "conv5_3_1"
  top: "conv5_3_1"
}
layer {
  name: "conv5_3_3"
  type: "Convolution"
  bottom: "conv5_3"
  top: "conv5_3_3"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_3_3/bn"
  type: "BatchNorm"
  bottom: "conv5_3_3"
  top: "conv5_3_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_3_3"
  type: "ReLU"
  bottom: "conv5_3_3"
  top: "conv5_3_3"
}
layer {
  name: "concat5_3"
  type: "Concat"
  bottom: "conv5_3_1"
  bottom: "conv5_3_3"
  top: "concat5_3"
}
layer {
  name: "conv5_3_re"
  type: "Convolution"
  bottom: "concat5_3"
  top: "conv5_3_re"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv5_3_re/bn"
  type: "BatchNorm"
  bottom: "conv5_3_re"
  top: "conv5_3_re"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu5_3_re"
  type: "ReLU"
  bottom: "conv5_3_re"
  top: "conv5_3_re"
}
layer {
  name: "conv5_3_de"
  type: "Deconvolution"
  bottom: "conv5_3_re"
  top: "conv5_3_de"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 16
    stride: 16
    group: 66
    weight_filler {
      type: "bilinear"
    }
    bias_term: false
  }  
}
layer {
  name: "conv5_3_pre"
  type: "Convolution"
  bottom: "conv5_3_de"
  top: "conv5_3_pre"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "loss5"
  type: "SoftmaxWithLoss"
  bottom: "conv5_3_pre"
  bottom: "label"
  top: "loss5"
  loss_param {
    normalize: false
  }
}
#conv4_3
layer {
  name: "conv4_3_1"
  type: "Convolution"
  bottom: "conv4_3"
  top: "conv4_3_1"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_3_1/bn"
  type: "BatchNorm"
  bottom: "conv4_3_1"
  top: "conv4_3_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_3_1"
  type: "ReLU"
  bottom: "conv4_3_1"
  top: "conv4_3_1"
}
layer {
  name: "conv4_3_3"
  type: "Convolution"
  bottom: "conv4_3"
  top: "conv4_3_3"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_3_3/bn"
  type: "BatchNorm"
  bottom: "conv4_3_3"
  top: "conv4_3_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_3_3"
  type: "ReLU"
  bottom: "conv4_3_3"
  top: "conv4_3_3"
}
layer {
  name: "concat4_3"
  type: "Concat"
  bottom: "conv4_3_1"
  bottom: "conv4_3_3"
  top: "concat4_3"
}
layer {
  name: "conv4_3_re"
  type: "Convolution"
  bottom: "concat4_3"
  top: "conv4_3_re"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv4_3_re/bn"
  type: "BatchNorm"
  bottom: "conv4_3_re"
  top: "conv4_3_re"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu4_3_re"
  type: "ReLU"
  bottom: "conv4_3_re"
  top: "conv4_3_re"
}
layer {
  name: "conv4_3_de"
  type: "Deconvolution"
  bottom: "conv4_3_re"
  top: "conv4_3_de"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 8
    stride: 8
    group: 66
    weight_filler {
      type: "bilinear"
    }
    bias_term: false
  } 
}
layer {
  name: "sum4_de"
  type: "Eltwise"
  bottom: "conv4_3_de"
  bottom: "conv5_3_pre"
  top: "sum4_de"
}
layer {
  name: "conv4_3_pre"
  type: "Convolution"
  bottom: "sum4_de"
  top: "conv4_3_pre"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "loss4"
  type: "SoftmaxWithLoss"
  bottom: "conv4_3_pre"
  bottom: "label"
  top: "loss4"
  loss_param {
    normalize: false
  }
}
#conv3_3
layer {
  name: "conv3_3_1"
  type: "Convolution"
  bottom: "conv3_3"
  top: "conv3_3_1"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_3_1/bn"
  type: "BatchNorm"
  bottom: "conv3_3_1"
  top: "conv3_3_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_3_1"
  type: "ReLU"
  bottom: "conv3_3_1"
  top: "conv3_3_1"
}
layer {
  name: "conv3_3_3"
  type: "Convolution"
  bottom: "conv3_3"
  top: "conv3_3_3"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_3_3/bn"
  type: "BatchNorm"
  bottom: "conv3_3_3"
  top: "conv3_3_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_3_3"
  type: "ReLU"
  bottom: "conv3_3_3"
  top: "conv3_3_3"
}
layer {
  name: "concat3_3"
  type: "Concat"
  bottom: "conv3_3_1"
  bottom: "conv3_3_3"
  top: "concat3_3"
}
layer {
  name: "conv3_3_re"
  type: "Convolution"
  bottom: "concat3_3"
  top: "conv3_3_re"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv3_3_re/bn"
  type: "BatchNorm"
  bottom: "conv3_3_re"
  top: "conv3_3_re"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu3_3_re"
  type: "ReLU"
  bottom: "conv3_3_re"
  top: "conv3_3_re"
}
layer {
  name: "conv3_3_de"
  type: "Deconvolution"
  bottom: "conv3_3_re"
  top: "conv3_3_de"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 4
    stride: 4
    group: 66
    weight_filler {
      type: "bilinear"
    }
    bias_term: false
  } 
}
layer {
  name: "sum3_de"
  type: "Eltwise"
  bottom: "conv3_3_de"
  bottom: "conv4_3_pre"
  top: "sum3_de"
}
layer {
  name: "conv3_3_pre"
  type: "Convolution"
  bottom: "sum3_de"
  top: "conv3_3_pre"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "loss3"
  type: "SoftmaxWithLoss"
  bottom: "conv3_3_pre"
  bottom: "label"
  top: "loss3"
  loss_param {
    normalize: false
  }
}
#conv2_2
layer {
  name: "conv2_2_1"
  type: "Convolution"
  bottom: "conv2_2"
  top: "conv2_2_1"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv2_2_1/bn"
  type: "BatchNorm"
  bottom: "conv2_2_1"
  top: "conv2_2_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu2_2_1"
  type: "ReLU"
  bottom: "conv2_2_1"
  top: "conv2_2_1"
}
layer {
  name: "conv2_2_3"
  type: "Convolution"
  bottom: "conv2_2"
  top: "conv2_2_3"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 1
    kernel_size: 3
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv2_2_3/bn"
  type: "BatchNorm"
  bottom: "conv2_2_3"
  top: "conv2_2_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu2_2_3"
  type: "ReLU"
  bottom: "conv2_2_3"
  top: "conv2_2_3"
}
layer {
  name: "concat2_2"
  type: "Concat"
  bottom: "conv2_2_1"
  bottom: "conv2_2_3"
  top: "concat2_2"
}
layer {
  name: "conv2_2_re"
  type: "Convolution"
  bottom: "concat2_2"
  top: "conv2_2_re"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv2_2_re/bn"
  type: "BatchNorm"
  bottom: "conv2_2_re"
  top: "conv2_2_re"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu2_2_re"
  type: "ReLU"
  bottom: "conv2_2_re"
  top: "conv2_2_re"
}
layer {
  name: "conv2_2_de"
  type: "Deconvolution"
  bottom: "conv2_2_re"
  top: "conv2_2_de"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 2
    stride: 2
    group: 66
    weight_filler {
      type: "bilinear"
    }
    bias_term: false
  } 
}
layer {
  name: "sum2_de"
  type: "Eltwise"
  bottom: "conv2_2_de"
  bottom: "conv3_3_pre"
  top: "sum2_de"
}
layer {
  name: "conv2_2_pre"
  type: "Convolution"
  bottom: "sum2_de"
  top: "conv2_2_pre"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "loss2"
  type: "SoftmaxWithLoss"
  bottom: "conv2_2_pre"
  bottom: "label"
  top: "loss2"
  loss_param {
    normalize: false
  }
}
#conv1_2
layer {
  name: "conv1_2_1"
  type: "Convolution"
  bottom: "conv1_2"
  top: "conv1_2_1"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 64
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv1_2_1/bn"
  type: "BatchNorm"
  bottom: "conv1_2_1"
  top: "conv1_2_1"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu1_2_1"
  type: "ReLU"
  bottom: "conv1_2_1"
  top: "conv1_2_1"
}
layer {
  name: "conv1_2_3"
  type: "Convolution"
  bottom: "conv1_2"
  top: "conv1_2_3"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 32
    pad: 1
    kernel_size: 3
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv1_2_3/bn"
  type: "BatchNorm"
  bottom: "conv1_2_3"
  top: "conv1_2_3"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu1_2_3"
  type: "ReLU"
  bottom: "conv1_2_3"
  top: "conv1_2_3"
}
layer {
  name: "concat1_2"
  type: "Concat"
  bottom: "conv1_2_1"
  bottom: "conv1_2_3"
  top: "concat1_2"
}
layer {
  name: "conv1_2_re"
  type: "Convolution"
  bottom: "concat1_2"
  top: "conv1_2_re"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "conv1_2_re/bn"
  type: "BatchNorm"
  bottom: "conv1_2_re"
  top: "conv1_2_re"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  param {
    lr_mult: 0
    decay_mult: 0
  }
  batch_norm_param {
    use_global_stats: false
  }
}
layer {
  name: "relu1_2_re"
  type: "ReLU"
  bottom: "conv1_2_re"
  top: "conv1_2_re"
}
layer {
  name: "conv1_2_de"
  type: "Deconvolution"
  bottom: "conv1_2_re"
  top: "conv1_2_de"
  param {
    lr_mult: 0
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    stride: 1
    group: 66
    weight_filler {
      type: "bilinear"
    }
    bias_term: false
  } 
}
layer {
  name: "sum1_de"
  type: "Eltwise"
  bottom: "conv1_2_de"
  bottom: "conv2_2_pre"
  top: "sum1_de"
}
layer {
  name: "conv1_2_pre"
  type: "Convolution"
  bottom: "sum1_de"
  top: "conv1_2_pre"
  param {
    lr_mult: 10
    decay_mult: 1
  }
  param {
    lr_mult: 20
    decay_mult: 0
  }
  convolution_param {
    num_output: 66
    pad: 0
    kernel_size: 1
    weight_filler {
      type: "xavier"
      std: 0.1
    }
    bias_filler {
      type: "constant"
      value: 0.1
    }
  }
}
layer {
  name: "loss1"
  type: "SoftmaxWithLoss"
  bottom: "conv1_2_pre"
  bottom: "label"
  top: "loss1"
  loss_param {
    normalize: false
  }
}
