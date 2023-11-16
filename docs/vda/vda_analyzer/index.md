# VDA Analyzer 软件操作手册

VDA Analyzer 为应用于 VDA 分析仪的软件，可实现在线/离线标定、在线/离线分析，并进行分析回放。VDA Analyzer 系列软件分为两个版本：全场应变 (VDA Strain Analyzer)、刚性体移 (VDA Rigid Analyzer)，分别适配 VDA 全场应变测量仪、VDA 刚性位移分析仪两款产品，用于不同类型的测量分析。

软件技术参数见下表。

<table>
    <tr>
        <th>软件</th><th align="center">VDA Strain Analyzer 专业版</th><th align="center">VDA Rigid Analyzer 专业版</th>
    </tr>
    <tr>
        <td>追踪技术</td><td colspan="2" align="center">DIC</td>
    </tr>
    <tr>
        <td>测量精度</td><td colspan="2" align="center">0.01 像素</td>
    </tr>
    <tr>
        <td>测量对象</td><td align="center">支持多区域测量</td><td align="center">支持多点测量</td>
    </tr>
    <tr>
        <td>分析速度</td><td align="center">3~10 Hz</td><td align="center">50~100 Hz</td>
    </tr>
    <tr>
        <td>测量值</td><td>位移 (u, v, w)、应变 (εx, εy)、主应变 (ε1, ε2)、剪应变 (εxy)</td><td>位移、速度、加速度、频谱、点应变、电压值</td>
    </tr>
    <tr>
        <td>输出结果</td><td>支持一键生成.csv 测量数据，包含图像坐标、空间坐标、位移、应变、主应变，选点全程位移、应变、主应变输出</td><td>支持一键生成.csv 测量数据，包含位移、世界坐标、图像坐标、速度、加速度、频谱、点应变、电压值</td>
    </tr>
    <tr>
        <td>快速标定</td><td colspan="2">自主研发核心标定算法，实现现场快速、简易、方便的高精度标定；标定时间约 1—5 分钟</td>
    </tr>
    <tr>
        <td>记录存档</td><td colspan="2" align="center">支持工程数据、图像实时存储</td>
    </tr>
    <tr>
        <td>离线处理</td><td colspan="2" align="center">将记录存档的数据进行离线标定、离线分析</td>
    </tr>
    <tr>
        <td>查阅模式</td><td colspan="2" align="center">支持数据离线标定、离线分析、数据回放</td>
    </tr>
    <tr>
        <td>测量模式</td><td>支持单区域、多区域测量，支持二维、三维测量</td><td>支持单点、多点测量，支持二维、三维测量</td>
    </tr>
</table>

---

下列章节介绍 VDA Analyzer 系列软件的安装方法、软件各区域功能。

- [**软件安装**](installation.md)

- [**界面介绍**](overview.md)

---

下列章节按 VDA 的常规使用步骤，详述使用 VDA Analyzer 系列软件进行标定与分析的方法。

- [**准备工作**](preparation.md)

- [**标定**](calibration.md)
  
- [**全场应变分析**](analysis_strain.md)

- [**刚性位移分析**](analysis_rigid.md)

---

下列章节给出 VDA Analyzer 系列软件常见使用问题处理方法，并附有版本更新说明。

- [**常见问题及处理**](faq.md)

- [**版本更新记录**](changelog.md)

---