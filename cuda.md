### 1.model.cuda()和model.to(device)有什么区别
都可以将模型或数据移动到gpu上

#### 1.1 model = model.cuda()
`model = model.cuda()`: 将模型移动到当前默认的 GPU 设备（通常是 cuda:0）
不能是cpu，如果想指定其他 GPU，需要调用 `model.cuda(device_id)`，如` model.cuda(1)` 将模型移动到 cuda:1  

#### 1.2 model = model.to(device)
device 可以是 cuda:0, cuda:1, cpu 等，因此支持动态选择设备
```
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model = model.to(device)  # 根据设备动态移动模型
```
