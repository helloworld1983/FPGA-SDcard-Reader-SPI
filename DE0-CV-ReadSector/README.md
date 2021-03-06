读取扇区示例
===========================

该示例在 [**DE0-CV 开发板**](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=163&No=921) 上运行，该示例读取 **SD卡** 的 **0号扇区**，将最后两字节显示在数码管上。

# 运行示例

1、 准备一个 **microSD卡** ， 文件系统不限 。

2、 将 **microSD卡** 插入 **DE0-CV 开发板** 的卡槽。

3、 将 **DE0-CV 开发板** 上电，并插入 USB-Blaster 线到 PC 机。

4、 用 **Quartus13.1** (或更高版本) 打开工程 **DE0-CV-ReadSector.qpf** ，综合并烧录。

5、 观察到开发板数码管的变化。按下 **DE0-CV 开发板** 上的 **FPGA_RESET按钮** 可以重新读取。

# 数码管含义

| 数码管位 (从右往左) | 含义   |
| :-------------   | :---  |
| 第0位   | 若为 **8** ，说明SD卡已完成初始化 |
| 第1位   | **0**代表**未知类别** ，**1**代表**SDv1卡** ，**2**代表**SDv2卡** ， **3**代表**SDHCv2卡** |
| 第3~6位 | SD卡 **第0扇区(MBR扇区)** 的最后两字节。若为**55AA**，代表MBR扇区有效。

| ![readsector示例照片](https://github.com/WangXuan95/FPGA-SDcard-Reader-SPI/blob/master/images/readsector_test.jpg) |
| :------: |
| 图：在图中，数码管显示初始化完成，卡类型为 **SDHCv2卡** ，第0扇区最后两字节为**55AA** |
