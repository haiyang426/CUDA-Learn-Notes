# Dot Product

## 0x00 说明

包含以下内容：

- [X] dot_prod_f32_acc_with_f32_kernel
- [X] dot_prod_f32x4_acc_with_f32_kernel(float4向量化版本)
- [X] dot_prod_f16_acc_with_f32_kernel(fp16版本，使用fp32 acc)
- [X] dot_prod_f16x2_acc_with_f32_kernel(fp16向量化版本，使用fp32 acc)
- [X] PyTorch bindings

## 测试

```bash
# 只测试Ada架构 不指定默认编译所有架构 耗时较长
export TORCH_CUDA_ARCH_LIST=Ada 
python3 dot_product.py
```

输出:

```bash
--------------------------------------------------------------------------------
       out_f32f32: -88.81410217   , time:0.01135945ms
     out_f32x4f32: -88.81417847   , time:0.01171017ms
    out_f32f32_th: -88.81379700   , time:0.01147819ms
--------------------------------------------------------------------------------
       out_f16f32: -88.62890625   , time:0.01113868ms
     out_f16x2f32: -88.65764618   , time:0.01108241ms
    out_f16f16_th: -88.75000000   , time:0.01112628ms
--------------------------------------------------------------------------------
```