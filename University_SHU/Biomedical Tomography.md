# 医学成像
## 思考题汇总
+ **基本的医学成像技术由哪些？各自成像机理有何特点？各成什么样的图像？**
  + X射线
    + 三维器官投影至二维平面
    + 优点：解剖结构成像
    + 缺点：不能显示软组织图像
  + X-CT
    + 从多个角度的投影图像重建物体内部结构信息
    + 1917 Radon提出数学理论
    + 1963 Cormack建立投影重建准确数学方法
    + 1967 Hounsfield制成第一台XCT原型机
    + Housfield和Cormack被授予诺贝尔医学金
  + 核医学
    + 基于原子物理学，放射性元素放置于体内，体外接收射线
    + 物理基础：射线于物质的相互作用
    + 成像模式：核素测量，示踪和放射性药物成像
    + 优点：可观察生物体新陈代谢过程
    + 缺点：分辨率低
    + PET成像
  + 超声
    + 基于组织的声学特性（边界反射特性）
    + 物理原理：压电效应
    + 优点：实时、动态观测，仪器操作方便，安全，便宜
    + 缺点：分辨率低，不适用胸腔
  + 磁共振成像
    + 优点：可结构与功能成像，分辨率高
    + 缺点：贵
  + 光学分子成像
    + 外加梯度磁场检测发出的电磁波
    + 优点：结构与功能成像，成本低
    + 缺点：成像深度浅，随深度增加空间分辨率降低
+ **医学成像技术的主要应用领域有哪些？**
  + 三维数字渲染
    + 电子解剖
    + 虚拟人
  + 手术机器人
  + 计算机辅助手术计划
    + 虚拟内窥镜
    + DDH手术计划
  + PACS影像归档和通信系统 & HIS医院信息系统
+ **常见的功能与结构成像系统各有哪些？其主要的联系与区别？**
  + 解剖结构成像：能量传递到人体再传递到接收器
    + 投影X射线成像
    + X-CT成像
    + 超声成像
    + MRI成像
  + 功能成像
    + PET
    + SPECT
    + fMRI
    + Optical Imaging
+ 医学成像技术于医学图像处理的联系与区别
  + 医学成像技术：研究图像形成的过程
  + 医学图像处理：对获取图像进行进一步处理
+ 空间分辨率以及灰度分辨率的定义及影响因素
  + 空间分辨率：对于图像细节部分的最小识别能力。
    + 采样像素量越少，空间分辨率越低
  + 灰度分辨率：对于图像灰度水平的最小识别能力。
    + AD转换量化级数越多，灰度分辨率越高
+ 描述图像的数字化过程
  + 采样：在模拟图像上按一定规律采集一定数量的点数据
  + 量化：将连续变化的灰度值转为离散整数灰度值（**灰度级**）
## 概论
+ 医学成像技术定义：
  + **借助某种介质**（X射线、电磁场、超声、放射性核素）与人体相互作用
  + **把人体内部组织器官的结构、功能等消息**传递给**数据接收设备**
  + **以影像的方式表现出来，提供给诊断医生**
+ 意义：看不见->看见
+ 技术分类：
  + X射线
  + 核医学成像
  + 核磁共振成像
  + 超声成像
+ 医学成像技术的分类
  + 结构/功能成像
    + 解剖结构成像：
      + 投影X射线成像
      + X-CT成像
      + 超声成像
      + MRI成像
    + 功能成像
      + PET
      + SPECT
      + fMRI
      + Optical Imaging
  + 电离/非电离成像
    + 图像都是由**能量和人体组织（物质）的相互作用形成的**
    + 两个条件：
      + 能量必须穿透人体
      + 能量必须与体内结构相互作用
    + 辐射分类：
      + 电离辐射：波长效于100nm
        + $\gamma$
          + $\gamma$相机
          + 核素断层PET/SPECT
        + X-ray
          + X射线投影
          + X-CT
      + 非电离辐射：能量较低
        + 声波
          + 超声波
            + 超声成像
          + 电磁波
            + 射频
              + 磁共振
            + 可见光
              + 内镜
              + 显微镜
            + 红外
              + 热成像
            + 微波
              + 微波断层
          + 电场
            + 阻抗成像
+ 医学成像系统的评价
  + X射线
    + 优点：解剖结构成像
    + 缺点：不能显示软组织图像
  + 核医学
    + 优点：可观察生物体新陈代谢过程
    + 缺点：分辨率低
  + 超声
    + 优点：实时、动态观测，仪器操作方便，安全，便宜
    + 缺点：分辨率低，不适用胸腔
  + 磁共振成像
    + 优点：可结构与功能成像，分辨率高
    + 缺点：贵
  + 光学分子成像
    + 优点：结构与功能成像，成本低
    + 缺点：成像深度浅，随深度增加空间分辨率降低
+ **应用领域**
  + 三维数字渲染
    + 电子解剖
    + 虚拟人
  + 手术机器人
  + 计算机辅助手术计划
    + 虚拟内窥镜
    + DDH手术计划
  + PACS影像归档和通信系统 & HIS医院信息系统

## 投影X射线成像系统
+ X-ray
  + 基本条件
    + 高速运动粒子流
    + 阻止粒子流运动的障碍（靶材）
  + X-ray tube
    + 结构
      + 阴极：电子源
        + 灯丝：钨丝，加热后在电场作用下释放电子
        + 聚焦装置：
      + 阳极：
        + 材料：能够承受电子冲击，使用原子序数较高的金属
          + 钨：74
          + 钼：42
          + 铑：45
        + 分类
          + 固体阳极：容易被干烂，焦点较大
          + 旋转阳极：分摊热量，
        + 焦点focal spot
          + 焦斑小：图像清晰
          + 焦斑大：图像模糊，散热性好
          + 旋转阳极边缘做成角度状5~20°
      + 高压发生器
        + 加在阳极与阴极之间，用于将阴极上的电子拉出来轰击阳极靶
        + 40kV~150kV
  + X-ray 分类
    + 连续辐射（轫致辐射）
    + 特征辐射（标识辐射）
  + X-ray 物理特性
    + 穿透性
    + 荧光作用
    + 电离作用
  + X-ray 化学特性
    + 光化作用（感光）
  + X-ray 生物特性
    + 损害作用：与吸收射线量成正比
  + X-ray辐射单位
  
    | 类别     | 惯用单位 | SI单位        | 换算        |
    | -------- | -------- | ------------- | ----------- |
    | 照射量   | R伦琴    | c/kg库伦/千克 | 1c/kg=3876R |
    | 吸收剂量 | rad拉德  | Gy戈瑞        | 1Gy=100rad  |
    | 剂量当量 | rem雷姆  | Sv西弗特      | 1Sv=100rem  |
  + X-ray强度
    + 辐射能量（W/m^2)
    + 与管电流成正比
  + X-ray硬度
    + 用管电压来描述X射线硬度
    + X射线硬度=X射线的质
  + X-ray在组织中的衰减
    + 单能窄束：Io=Ii*exp(-μΔx)
    + 连续宽束：Io=BIi*exp(-μΔx)
  + 与物质的相互作用
    + 主要
      + 低能：光电效应
      + 中能：康普顿效应
      + 高能：电子对效应
    + 次要
      + 相干散射
      + 核心散射
+ X-ray成像系统
  + 组成
    + X射线管
      + 电子源
      + 阳极靶
      + 高速电子流
    + 控制台
      + 成像对象
      + 成像参数
    + 准直器
      + 调节视野范围
    + 滤线片
      + 滤除续发射线
      + 结构：铅光栅
    + 成像系统
      + 载体
        + 荧光屏
        + 胶片增屏
        + 影像增强器
        + 图像板
      + 模拟成像
        + 荧光屏
          + 优点：可行
          + 缺点：发光效率低，需要暗室
        + 影像增强器 
          + 结构：
            + 输入荧光屏
            + 光电阴极
            + 聚焦电极
            + 阳极
            + 输出荧光屏
          + 优点：
            + 提高亮度
            + 提高分辨率
            + 降低辐射量
          + 缺点：
            + 大，重
            + 失真
            + 干扰
        + X-ray电视系统
          + 增强器
          + 闭路电视系统
        + 胶片
          + 医用X射线胶片
            + 功能
              + 记录
              + 显示
              + 储存
            + 特性：感光
          + 胶片增感屏
            + 分类
              + 钨酸钙
              + 稀土
            + 可增大20-40倍吸收