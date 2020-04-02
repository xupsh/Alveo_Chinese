# 文档说明

本文档为高校用户获得Alveo板卡后快速安装使用准备，内容为相关Xilinx官方资源列表，请按照资源列表准备。

------

如有技术问题可以在Xilinx官方中文或英文论坛咨询

- https://forums.xilinx.com/t5/Alveo-Data-Center-Accelerator/bd-p/alveo
- https://forums.xilinx.com/t5/SDx/bd-p/CN_HLS

如提问在官方论坛工作日2天内无答复，或5天内没有解决，可向[xup_china@xilinx.com](mailto:xup_china@xilinx.com) 发送邮件，并附上提问的帖子链接，寻求进一步处理。 此文档将持续更新

## 板卡安装

### 注意事项与软件下载

- Alveo板卡的开发需要Xilinx Runtime (XRT)、xilinx VITIS、Deployment Target Platform、Development Target Platform。每个型号的板卡都有先赢的Platform对应。

- 板卡安装注意版本匹配，不配套的vitis和xrt可能出现兼容性问题。现在推荐的版本是[Vitis 2019.2](https://www.xilinx.com/member/forms/download/xef-vitis.html?filename=Xilinx_Vitis_2019.2_1106_2127.tar.gz), [XRT 2.5](https://www.xilinx.com/bin/public/openDownload?filename=xrt_201920.2.5.309_7.4.1708-x86_64-xrt.rpm)。Platform请在板卡相应的页面下载：如[U200](https://www.xilinx.com/products/boards-and-kits/alveo/u200.html#tabAnchor-gettingStarted)。

- U200的硬件安装和系统配置请严格按照[UG1301](https://www.xilinx.com/support/documentation/boards_and_kits/accelerator-cards/1_4/ug1301-getting-started-guide-alveo-accelerator-cards.pdf)文档的说明进行。

- XRT有一个重要的依赖是EPEL，这个不在centos官方的库里，建议用户手动安装（下载地址：[EPEL](https://pkgs.org/download/epel-release)），详情见UG1301手册的21页。

- 先安装XRT，然后安装Deployment platform，才能安装Development platform。安装完Deployment platform后会有类似以下的提示：

```bash
      DSA package installed successfully.
     Please flash card manually by running below command:
      sudo /opt/xilinx/xrt/bin/xbmgmt flash --update --shell <shell_name>
```

​		请记录最后一条命令，这条命令可将Alveo板卡刷成适配当前Platform的固件。

- 

- 配置要求，Alveo板卡的开发对软硬件配置要求较高，具体的需求如下：

  | 项       | 需求                                                         |
  | -------- | ------------------------------------------------------------ |
  | 操作系统 | 64 位linux，具体含ubuntu 16.04, 18.04; CentOs 7.4, 7.5, 7.6; RHEL 7.4 7.5 7.6。 |
  | 内存     | Alveo cards: 最小64GB，推荐80GB以上                          |
  | 硬盘空间 | 100GB以上                                                    |
  

### 相关手册

- U200的官方地址

https://www.xilinx.com/products/boards-and-kits/alveo/u200.html#gettingStarted

- DS962 - 参数手册

https://www.xilinx.com/support/documentation/data_sheets/ds962-u200-u250.pdf

- UG1120 - Alveo加速卡的platform说明

https://www.xilinx.com/support/documentation/boards_and_kits/accelerator-cards/ug1120-alveo-platforms.pdf

- UG1238 - 开发工具使用手册

https://www.xilinx.com/support/documentation/sw_manuals/xilinx2019_1/ug1238-sdx-rnil.pdf

- UG1301 - Alveo加速卡安装入门

https://www.xilinx.com/support/documentation/boards_and_kits/accelerator-cards/1_4/ug1301-getting-started-guide-alveo-accelerator-cards.pdf

- UG1289 - Alveo加速卡用户使用指导

https://www.xilinx.com/support/documentation/boards_and_kits/accelerator-cards/ug1289-u200-u250-reconfig-accel.pdf

- Xilinx Runtime 源码

https://github.com/Xilinx/XRT




### 软件License 获取

VITIS是免费授权
针对学术用户， 如还需要用Vivado软件正版license 可以在这里免费申请

https://www.xilinx.com/support/university/donation-program.html

*注：必须是老师邮箱申请，学生申请无效*


## 培训&案例
### SDAccel/Alveo在线培训视频

https://www.xilinx.com/video/software/setting-up-alveo-u200-accelerator-card-for-sdaccel.html

https://www.xilinx.com/training/customer-training/using-xilinx-alveo-accelerate-workloads.html

https://www.xilinx.com/xilinxtraining/assessments/portal/ml-cloud/using-ml-suite-custom-applications-alveo/story_html5.html

https://www.xilinx.com/xilinxtraining/assessments/portal/ml-cloud/ml-suite-supported-frameworks/story_html5.html

### vitis 每周一课
- Vitis/Vitis AI工具详细介绍：https://www.bilibili.com/video/BV1wE41137e1
- Vitis工具设计流程：https://www.bilibili.com/video/BV1sE411N7LS
- Vitis AI新特性及开发流程介绍：https://www.bilibili.com/video/BV17K411L7gF

### Alveo相关开源参考案例

PYNQ2.5开始支持Alveo板卡https://github.com/Xilinx/PYNQ

HLS 免费电子书和案例 https://github.com/xupsh/pp4fpgas-cn

SDAccel 使用入门 https://github.com/Xilinx/SDAccel-Tutorials

SDAccel 案例 https://github.com/Xilinx/SDAccel_Examples

ML-Suite 机器学习库 https://github.com/Xilinx/ml-suite

Kubernetes K8S插件 https://github.com/Xilinx/FPGA_as_a_Service/tree/master/k8s-fpga-device-plugin/trunk

数据分析 https://github.com/Xilinx/data-analytics

数据压缩 GZip, WebP, LZ4 https://github.com/Xilinx/Applications

二项期权定价模型 https://github.com/Xilinx/BinomialModel

HLS案例 https://github.com/Xilinx/HLx_Examples

CERN 超大规模数据处理案例HLS4ML https://github.com/hls-fpga-machine-learning/hls4ml


### 合作伙伴商业解决方案

- https://www.xilinx.com/products/apps-and-libraries.html
- https://www.xilinx.com/products/acceleration-solutions.html

# FAQ

- 安装XRT时出现死机，重启无法进入系统，启动信息如下：

![xrt安装报错](xrt安装报错.png)

这个可能是Alveo板卡可能与其他OpenCL设备冲突（如独立显卡）。拔掉Alveo板卡即可启动系统。拔掉其他OpenCL设备（如显卡），重新安装系统）

- 板卡原来可以使用，突然出现XRT无法识别板卡的情况

  使用以下命令重新加载XRT模块：

  ```bash
  $sudo rmmod xocl
  $sudo rmmod xclmgmt
  $sudo modprobe xocl
  $sudo modprobe xclmgmt
  $xbutil validate
  ```

- lspci只显示一个kernel module（正常会显示XCLMGMT和XOCL两个）

使用记录的命令对板卡重新刷固件，关闭服务器，拔下板卡，等待3分钟（让电容充分放电），插入板卡后冷重启服务器。
