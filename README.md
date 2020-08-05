# micropython_ps2
ps2 controller in micropython


这是一份中文说明，If you want to see other version ,you can use google translate

在互联网上关于ps2 控制器的驱动还是有不少的，大多来自一个 ps2-arduino-lib ，然而用这个翻译成micropython以及在淘宝上买各种ps2控制器后发现各种不匹配，在痛苦的折腾了好几个版本的软件以及好几个厂家的硬件之后，终于发现最大的问题是来自于硬件，最后发现来自「上海猎神游戏数码店」这家淘宝店的ps2无线手柄有用，其余几家，都不能驱动上。其他几家手柄，命令延时很长，不够灵敏，最大的问题是滚轮无法驱动。

我在我买的esp32上，配置端口di口13， do口12, cs口15, clk口14， 利用这个代码

```
from ps2 import ps2ctl
ps2ct.run() 
```

可以运行，会打印出按键。注意在运行之前，手柄插上电池，运行前要按一下start键


如果你要定制端口

```
from ps2 import PS2Controller
ps2ctl = PS2Controller(di_pin_no=13, do_pin_no=12, cs_pin_no=15, clk_pin_no=14)
ps2ctl.run()
```

希望这段代码对你有用
