# 参数设置

在相机采集之前，可设置拍摄参数。以单目模式为例，首先需构建 X1 拍摄参数对象。

```cs
X1.CaptureOptions options = CreateOptionX1(device, x1);
```

将修改后的参数保存为本地配置文件。以配置文件存储位置为 D 盘、名称为 test.json 为例，执行下面代码。

```cs
x1.SaveSettingToFile("d://test.json");
```

设置是否计算法向量、法向量计算半径。是否计算法向量可选 true（是）或 false（否），默认值为 false。法向量计算半径默认值为 5。

```cs
options.calc_normal = false;
options.calc_normal_radius = 5;
```

设置坐标系。可选 true（相机坐标系）或 false（标定板坐标系），默认值为 false。

```cs
options.transform_to_camera = false;
```

设置聚类去噪距离阈值（单位：mm）与聚类去噪有效点数。聚类去噪距离阈值的取值范围为 [0, 10] 之间的浮点值，默认值为 0.5；聚类去噪有效点数的取值范围为 [0, 100] 之间的整数，默认值为 40。

```cs
options.noise_removal_distance = 0;
options.noise_removal_point_number = 40;
```

设置光强对比度阈值。取值范围为 [0, 10] 之间的整数，默认值为 0。

```cs
options.light_contrast_threshold = 3;
```

设置 2D 曝光时间、3D 曝光时间（单位：ms）。2D、3D 曝光时间的取值范围与默认值均与相机配置有关，通常 P/I/X 系列灰度相机为 [3, 100]，彩色相机为 [11, 100]，G 系列激光相机为 [20, 100]，可通过 GetExposureTimeRange() 函数查询。

```cs
options.exposure_time_2d = 11;
options.exposure_time_3d = 11;
```

设置投影亮度等级。取值范围为 [1, 240] 之间的整数，默认值为 240。

```cs
options.projector_brightness = 240;
```

设置 2D 增益、3D 增益（单位：dB）。2D、3D 增益的取值范围与相机配置有关，可通过 GetGainRange() 函数查询。2D 增益、3D 增益的默认值均为 0。

```cs
options.gain_2d = 0.0f;
options.gain_3d = 0.0f;
```

设置 HDR 曝光次数及每次曝光时间（单位：ms）。HDR 曝光次数可选为 0（不使用 HDR）、2（2 次曝光）、3（3 次曝光）。

```cs
options.hdr_exposure_times = 0;
options.hdr_exposuretime_content = new int[3];
options.hdr_exposuretime_content[0] = 11;
options.hdr_exposuretime_content[1] = 20;
options.hdr_exposuretime_content[2] = 50;
options.hdr_gain_3d[0] = 0.0f;
options.hdr_gain_3d[1] = 0.0f;
options.hdr_gain_3d[2] = 0.0f;
options.hdr_scan_times[0] = 2;
options.hdr_scan_times[1] = 2;
options.hdr_scan_times[2] = 2;
options.hdr_projector_brightness[0] = 240;
options.hdr_projector_brightness[1] = 240;
options.hdr_projector_brightness[2] = 240;
```

设置 2D Gamma、3D Gamma。2D、3D Gamma 的取值范围与相机配置有关，可通过 GetGammaRange() 函数查询。2D Gamma、3D Gamma 的默认值均为 1。

```cs
options.gamma_2d = 1.0f;
options.gamma_3d = 1.0f;
```

设置拍摄时 2D 相机是否使用光机。可选 true（是）或 false（否），默认值为 true。

```cs
options.use_projector_capturing_2d_image = true;
```

设置平滑等级。可选：SmoothnessLevel_Off（关）、SmoothnessLevel_Weak（低）、SmoothnessLevel_Normal（中） 、 SmoothnessLevel_Strong（强） ， 默认值为 SmoothnessLevel_Off。

```cs
options.smoothness = SmoothnessLevel.SmoothnessLevel_Off;
```

设置下采样距离（单位：m）。默认值为-1。

```cs
options.downsample_distance = -1;
```

设置相机拍摄模式。 P/I/X 系列相机可选 ： CaptureMode_Fast（快速模式）、CaptureMode_Normal（标准模式），默认为标准模式；G 系列激光相机可选：CaptureMode_Ultra（高精度模式）、CaptureMode_Robust（抗干扰模式）。

```cs
options.capture_mode = CaptureMode.CaptureMode_Normal;
```

设置置信度去噪阈值。取值范围为 [0, 1] 之间的浮点值，默认值为 0.6。

```cs
options.confidence_threshold = 0;
```

设置扫描次数。此参数仅激光相机抗干扰模式下可用，取值范围为 [2, 8]。

```cs
options.scan_times = 2;
```

设置 Z 向截断最小值与最大值。

```cs
options.truncate_z_min = 100;
options.truncate_z_max = 200;
```

设置双边滤波窗口大小、深度分布、空间分布参数。

```cs
options.bilateral_filter_kernal_size = 5;
options.bilateral_filter_depth_sigma = 100;
options.bilateral_filter_space_sigma = 100;
```

设置 ROI 范围。设置 ROI 范围。使用前，应根据应用场景，检查并自行修改 ROI 参数。4 个参数依次代表区域的起始 x 坐标、起始 y 坐标、区域宽度、区域高度，取值范围与相机拍摄区域大小有关。默认值为 (10, 10, 200, 200)。

```cs
options.roi = new ROI(0, 0, 0, 0);
```

设置边缘去噪等级。取值范围为 [0, 10] 之间的整数，默认值为 2。

```cs
X2.CaptureOptions options = CreateOptionX2(device, x2);
options.edge_noise_reduction_threshold = 2;
```

!!! attention "注意"
    以下拍摄参数仅适用于双目模式，需构建 X2 拍摄参数对象。

设置光机投影颜色。可选：ProjectorColor_Red（红色）、ProjectorColor_Green（绿色）、ProjectorColor_Blue（蓝色）、ProjectorColor_White（白色） ， 默认值为ProjectorColor_Blue。非 RGB 光机不可以调整投影颜色。

```cs
options.projector_color = ProjectorColor.ProjectorColor_Blue;
```

设置坐标系。可选：CameraID_Left（左相机坐标系）、CameraID_Right（右相机坐标系）、CameraID_NONE（标定板坐标系），默认值为 CameraID_NONE。

```cs
options.transform_to_camera = CameraID.CameraID_NONE;
```
