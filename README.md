# FK-Onmyoji

**阴阳师抗检测多功能护肝辅助脚本**

 - 支持**游戏多开**，多种**游戏模式**同时运行

 - 支持道馆突破自动准备

 - 支持组队**章节探索**队员**自动更换选定狗粮**

 - 鼠标键盘模拟输入，指针变速移动，非固定点点击，随机间隔连点

 - **掉线、失败、占用**警报提示

 - 抗失效随机点击复位

 - 自动接受悬赏封印邀请

 - QQ消息反馈

 - 跟进最新活动副本


 
----------


# 开始

## 方案1：直接下载可执行程序 ##
 
 [Beta 1.0.0下载地址][1]

## 方案2：手动部署Python脚本运行环境 ##

 1. 安装Python3.7（>=3.7）。

 2. 安装拓展库：

    **PyAutoGUI**

    **OpenCV-Python**

    **PyWin32**

 3. 下载脚本源代码。


 
----------


# 准备

 1. 调整阴阳师窗口分辨率至固定大小（可选）：

    -打开阴阳师安装目录下的**neox.xml文件**，修改**WindowClientHeight**（窗口高度），**WindowClientWidth**（窗口宽度）。**推荐宽度为683，高度为384**。

 2. 根据**screenshots文件夹**下的截图样例截取图片（推荐宽高下可跳过）。

 3. 运行**screenshots文件夹**下的**convert.py**：（可选，截取新截图后推荐，可防止libpng相关警告，需要安装**ImageMagick**，下附下载地址）
 
    -打开**convert.py**文件修改**imageMagickPath**变量的值为**ImageMagick安装路径**后运行该脚本。
 
 [ImageMagick-6.2.7-Q16下载地址][2]

 
----------


# 入门使用
 
 1. 手动完成一局**已选游戏类型**以锁定阵容。

 2. 以**管理员身份**运行（必须，以防止鼠标键盘模拟输入失效）。

 3. 根据提示输入相关信息（因为设置的窗口宽高不包括边框宽高，故需将**高度**适当增大，比如30）

	
	-样例：

![样例][3]

 4. 挂机（按P**暂停/继续**）。
 
# 详细使用

 - 多人御魂/觉醒：

     1.手动完成一局以锁定阵容，注意队员和队长都要锁定。

     2.在组队界面运行脚本。

     3.挂机。

 - 章节探索：

     单人：

     1.手动完成一局以锁定阵容。

     2.在有"挑战"按钮的界面运行脚本。如图：

     ![样例2][4]

     3.挂机。

     多人：

     1.手动完成一局以锁定阵容，注意队员不锁定，队长锁定。

     2.队长在有"组队"按钮的界面点击组队并勾选队员，注意不要点击"邀请"。如图：

     ![样例3][5]

     3.挂机。

 - 单人御魂/业原火/御灵：

     1.锁定阵容。

     2.在有"挑战"按钮的界面运行脚本。

     3.挂机。

 - 结界突破：

     1.锁定阵容。

     2.在有"刷新"按钮的界面运行脚本。

     3.挂机。

 - 道馆：

     1.在有"准备"按钮的界面运行脚本。

     2.挂机

 - 活动-修罗战场：

     1.点击"修罗战场"后选择难度。

     2.运行脚本。

     3.挂机。


# 配置文件（**config.ini**）说明

	ExitAfterfinish = False          （完成所有游戏类型后退出程序）

	CloseGamesAfterFinish = False    （完成所有游戏类型后关闭所有游戏）

	ExitAfterFailure = False         （失败后退出程序，不可用）

	CloseGamesAfterFailure = True    （失败后关闭所有游戏）

	ExitIfOccupied = False           （检测到账户在其他设备登录后退出程序，不可用）

	CloseGamesIfOccupied = True      （检测到账户在其他设备登录后关闭所有游戏）

	ExitIfFoodNotEnough = False      （检测到体力不足后退出程序）

    CloseGamesIfFoodNotEnough = True  （检测到体力不足后关闭游戏）

    ReplaceIfShikigamiFull = True     （检测到式神经验已满后更换式神）

# 相关问题 & 注意事项

 1. **注意**：以下情况**蜂鸣器**会发出**警报声**（加*的建议进行人工操作）：
    
	-已选模式全部结束
	
    -检测到悬赏封印邀请
	
    *-失败（警报声结束后关闭所有游戏，结界突破除外，可修改配置）
	
    *-失去连接
	
    *-脚本可能失效，超过5分钟未进行任何操作
	
    *-检测到账户在其他设备登录（警报声结束后关闭所有游戏，可修改配置）
	
 2. **问题**：窗口起始位置是什么？
    
	-窗口边框左上角相对于屏幕左上角的位置
 3. **问题**："QQ反馈者"必填吗？填什么？
    
	-可选，请填入聊天窗口的标题，不需要请填写任意字符。聊天窗口位置没有要求，不能最小化。
 4. **问题**：怎样去除"**警报声结束后关闭所有游戏**"的功能？
    
	-打开配置文件**config.ini**进行配置

 5. **问题**：如何设定被更换的狗粮？

    -在战斗准备时截取式神**稀有度**选项卡图片，将截图替换"./screenshots/Story/selectedLevel.png"

    ![样例4][6]

    -在战斗准备时截取式神选项卡图片，将截图替换"./screenshots/Story/shikigamiSelected.png"
    
    ![样例5][7]

# 关于

学了一天Python来**练手**的。


  [1]: https://t00y.com/file/15016760-403156759
  [2]: https://t00y.com/file/15016760-403129810
  [3]: https://github.com/BluePlumStudio/FK-Onmyoji/blob/master/sample.png
  [4]: https://github.com/BluePlumStudio/FK-Onmyoji/blob/master/sample2.png
  [5]: https://github.com/BluePlumStudio/FK-Onmyoji/blob/master/sample3.png
  [6]: https://github.com/BluePlumStudio/FK-Onmyoji/blob/master/screenshots/Story/selectedLevel.png
  [7]: https://github.com/BluePlumStudio/FK-Onmyoji/blob/master/screenshots/Story/shikigamiSelected.png