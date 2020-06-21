---
title: Arduino Workshop
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2016-11-22 22:08:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592718595/Img/BlogCover/ArduinoWorkshop_ni25f9.jpg
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592718595/Img/BlogCover/ArduinoWorkshop_ni25f9.jpg
password:
summary: 关于Arduino，关于硬件
categories:
- Read
tags:
- Dev
- Arduino
- Read
keywords:
updated: 2016-11-22 22:08:00
---

## 一 起步  
  
**章节内容**  
* 简要介绍 Arduino 能做什么以及一些作品  
* Arduino 集成开发环境(IDE)的安装  
* 关于 Arduino 使用的一些安全提示  
  
### 所需的软件  
[Arduino IDE 官方下载页面（包含各系统对应版本）](https://www.arduino.cc/en/Main/Software)  

#### Windows XP 及后续版本  
1. Windows 版本的Arduino IDE 下载后为一个压缩包，解压后即为软件以及相关文件，无需安装过程。可以将软件包放到自己想要放到的位置，然后直接为软件包内的 arduio.exe 创建一个桌面快捷方式即可。  
2. 软件下载并解压好后需要安装驱动才可进行后续工作。  
3. 不能忘记在IDE软件内设置 Arduino 的型号和串口号。  
4. Tips：软件语言可以设置为英文或中文。在软件菜单 File —— Preference 中设置。  

### 安全  
* Arduino 几乎不需要用到市电。  
  
---
## 二 探索 Arduino 板和 IDE  
  
**章节内容**  
* 介绍基本Arduino板上主要小部件  
* Arduino IDE 简要介绍  
* Arduino 程序的基本结构以及检查和修改  

### Arduino 板  
1. 带 ~ 符号的引脚都可以进行模拟信号的操作。  
2. 引脚A4、A5和引脚0、1均也是串口，可以用来与其他器件发送和接收数据。  
3. 使用多个盾板时，要记住每块盾板都用了哪些引脚，避免相互引起冲突。  

### 在 IDE 里创建第一个程序  
#### setup 函数  
* setup 函数只在每次开机或重启时执行一次。  

#### loop 函数  
* loop 函数是程序运行期间持续循环运行的部分。  
* Arduino IDE 不会自动保存当前文件，需要经常手动保存当前文件。  
* 引脚控制中，HIGH 和 LOW 可以分别用 1 和 0 代替，效果一样。  

#### 检查程序  
* 程序出错时，错误一般出在高亮标识的那一行或前一行。  
  
---
## 三 第一步  
### 电子元件  
#### 电阻  
* 电阻阻值读法：  
**第一环**：标示阻值的第一个数字  
**第二环**：标示阻值的第二个数字  
**第三环**：标示倍数（如果共有4环）或第三个数字（共有5环）  
**第四环**：一共有5环的倍数  
**第五环**：表示误差（精度）  
* 电阻色环颜色对应数值  
**颜色** —— **欧姆**  
黑色——0  
棕色——1  
红色——2  
橙色——3  
青色——4  
绿色——5  
蓝色——6  
紫色——7  
灰色——8  
白色——9

#### 发光二极管  
* 使用LED的过程中要考虑到 LED 的工作电压和电流  
* 红色LED一般需要 1.7V 电压和 5~12mA 的电流  
* Arduino 的输出为 5V，以及能输出大的多的电流  
* 不太确定的情况下可选择阻值稍大一些的电阻  

#### 面包板  
* 使用面包板要明确面包板的插孔内部是如何连接的  

### 作品1：做出闪烁的LED波  
#### 算法  
1. 点亮 LED 1  
2. 等待半秒  
3. 熄灭 LED 1  
4. 点亮 LED 2  
5. 等待半秒  
6. 熄灭 LED 2  
7. 持续重复上述步骤直至 LED 5 被点亮，然后从 LED 5 做到 LED 1  
8. 不停地重复  

#### 元件  
* Arduino 和 USB连接线  
* 5个 LED  
* 5个 560Ω 左右的电阻  
* 一块面包板  
* 若干连接线  

#### 程序  

```c
// ArduionWorkshop_Work1_闪烁的LED波
// ezhq_16/11/25
void setup()
{
  pinMode(2,OUTPUT); // 设置数字引脚2~6为输出
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
}
void loop()
{
  digitalWrite(2,HIGH); //点亮 LED 1
  delay(500); //等待半秒
  digitalWrite(2,LOW); //熄灭 LED 1
  digitalWrite(3,HIGH); //按同样规律点亮剩余LED灯
  delay(500); 
  digitalWrite(3,LOW);
  digitalWrite(4,HIGH);
  delay(500);
  digitalWrite(4,LOW);
  digitalWrite(5,HIGH);
  delay(500);
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  delay(500);
  digitalWrite(6,LOW); //从LED5 开始反向进行
  digitalWrite(5,HIGH);
  delay(500);
  digitalWrite(5,LOW);
  digitalWrite(4,HIGH);
  delay(500);
  digitalWrite(4,LOW);
  digitalWrite(3,HIGH);
  delay(500);
  digitalWrite(3,LOW);
  //程序会从开头循环运行
}
```

#### 电路  
### 作品2：用for 循环做重复动作  

* 作品2中，第二个for循环中，将“a>1”改为“a>2”,会使得最终效果更顺畅自然。  

```c
// ArduionWorkshop_Work2_用 for 循环做重复动作
// ezhq_16/11/25
int d = 100;

void setup()
{
  pinMode(2,OUTPUT); // 设置数字引脚2~6为输出
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
}
void loop()
{
  for ( int a = 2; a < 7; a++)
  {
    digitalWrite(a, HIGH);
    delay(d);
    digitalWrite(a, LOW);
    delay(d);
  }
  for ( int a = 5; a > 2; a--)
  {
    digitalWrite(a, HIGH);
    delay(d);
    digitalWrite(a, LOW);
    delay(d);
  }
}
```

### 用脉冲宽度调制变化LED的亮度  

* PWM(Pulse Width Modulation)脉冲宽度调制/脉宽调制  
* Aruino 的 PWM 大约每秒500次的速度切换 LED 亮灭来形成各种来形成各种亮度  
* 亮度的变化由数字输出引脚输出高电平的时间和低电平的时间的比值不同来实现（占空比）  
* 产生 PWM 信号，所用函数为analogWrite(x, y), x 为数字引脚编号；y 为占空比的比值，范围为 0~255，255 表示 100% 占空比。  

### 作品3：演示PWM  

```c
// ArduionWorkshop_Work3_演示PWM
// ezhq_16/11/25
int d = 5;

void setup()
{
  pinMode(3,OUTPUT); // LED 控制引脚3，3是具有带有 PWM 功能的引脚
}
void loop()
{
  for ( int a = 0; a < 256; a++)
  {
    analogWrite(3, a);
    delay(d);
  }
  for ( int a = 255; a >=0; a--)
  {
    analogWrite(3, a);
    delay(d);
  }
  delay(d);
}
```

### 更多的电子元件  
#### 晶体管 
* 使用晶体管一定要确定晶体管的管脚排列，正确连接管脚  

#### 整流二极管  
* 整流二极管的负极为标有黑色环的一端    

#### 继电器  
### 高压电路  
* 高压电路注意保护电路的安排，以免损害设备器件  

---
## 四 构建模块  
### 电容  
#### 数字输入  
* 使用开关时要注意开关抖动现象的存在并对此情况进行考虑  

### 作品4：演示数字输入  

```c
// ArduionWorkshop_Work4_演示数字输入
// ezhq_17/01/11
// 注：若没有电容，可以直接在开关输出引脚处直接外加一个220R的电阻到GND

#define LED 12
#define BUTTON 7

void setup()
{
  pinMode(LED, OUTPUT);
  pinMode(BUTTON, INPUT);
}

void loop()
{
  if ( digitalRead(BUTTON) == HIGH)
  {
    digitalWrite(LED,HIGH);
    delay(500);
    digitalWrite(LED,LOW);
  }
}
```

* 注：若没有电容，可以直接在开关输出引脚处直接外加一个220R的电阻到GND实现去除抖动的作用  


## 五 使用函数  


## 六 数字、变量和算术  


## 七 液晶显示器  


## 八 扩展 Arduino  


## 九 数字键盘  


## 十 用触摸屏获得用户输入  


## 十一 认识 Arduino 系列  


## 十二 电机和运动  


## 十三 用 Arduino 接 GPS  


## 十四 无线数据通信  


## 十五 红外遥控  


## 十六 读RFID 标签  


## 十七 数据总线  


## 十八 真实时钟  


## 十九 互联网  


## 二十 手机通信  
