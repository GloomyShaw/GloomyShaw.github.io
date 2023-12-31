# 异常排查

### 1. 加密狗提示找不到或者失效。

(1) 检查加密狗是否是亮灯状态。

(2) 确定使用中的加密狗是否是有效期。对出货用户，加密狗有效期为永久；对试用用户，加密狗有效期为两个月内。

### 2. 相机无法识别，或者只识别出一台相机。

- USB 相机：检查连接电脑/工控机的接口是否为 USB3.0。

- 千兆网相机：检查网口是否支持 POE 供电。

- 万兆网相机：需要配合万兆网卡使用，检查是否保证相机电源独立供电（万兆网相机不支持 POE 供电）。

### 3. 标定时，无法识别圆环。

(1) 检查标定板是否处于相机视野范围内。保证标定板的宽度至少占视野宽度的 1/4，且尽可能在视野内居中。

(2) 检查标定板亮度是否合适，应使其在视野范围内清晰可见。

(3) 检查标定板内所有图形是否对焦清晰。如果图像模糊，需要进行调焦。

(4) 检查标定板内图形是否存在遮挡、脏污、缺失。

(5) 检查视野内是否有其他圆环干扰。可在“相机控制”中裁剪画面范围，排除干扰。

(6) 检查高精度标定文件是否正确。

(7) 可适当修改标定参数。

如果完成以上步骤后仍无法识别，请联系技术支持。

### 4. 调节相机曝光值亮度无变化。

(1) 检查环境光照度是否合适。

(2) 检查镜头光圈是否误调到光圈值最大位置（最小光圈）。

(3) 检查自动曝光功能是否开启，AOI 区域是否在目标上。若不在目标上，需要修改 AOI 区域。  
(4) 可关闭自动曝光，改为手动曝光，并检查软件中曝光值设置是否正确合理。

### 5. 标定结果相机基线与实际不符。

(1) 检查选择的高精度标定文件是否跟镜头相符。

(2) 检查标定参数输入是否正确。

### 6. 全场分析时，分析过程中云图不显示，或云图乱飞。

(1) 检查分析参数设置，确保子集大小应包含至少 3 个散斑图形。

(2) 检查分析过程中目标是否出现较大变形。

(3) 检查分析参数设置，适当调整子集宽度、子集高度、最大相关系数。

### 7. 位移分析时，当被测点移动量大会匹配失败。

(1) 将分析模式设置为大位移，增加水平、垂直搜索范围值。

(2) 将分析模式设置为大位移，开启增量分析功能。 

(3) 检查分析参数设置，确保子集大小应包含至少 3 个散斑图形。

(4) 检查分析参数设置，适当调整子集宽度、子集高度、最大相关系数。

### 8. 位移某一个方向时，其他方向分量比较大。

(1) 检查被测物本身是否不稳定。

(2) 检查标定板是否紧贴被测目标平面。

(3) 标定完成后，建议对目标平面做标定坐标调整，将坐标系进一步调整到目标平面或运动方向。