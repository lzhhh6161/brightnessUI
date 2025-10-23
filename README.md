# brightnessUI

## Introduction
独显GPU工作下系统亮度无法调节，此软件可以直接调节，摘自https://gitee.com/shu-peixuan/brightnessUI

A simple UI to change screen backlight (brightness) for Ubuntu20.

Purpose: An alternative for those computers with system brightness slider not working. This UI changes the backlight by modifying `/sys/class/backlight/xxx/brightness` directly, where `xxx` differs according to your computer.

![img](https://gitee.com/shu-peixuan/brightnessUI/raw/master/pictures/ui.png)

## Install

- ### Method1 (From source)


```bash
git clone https://gitee.com/shu-peixuan/brightnessUI.git
cd brightnessUI/
./install.sh
```
If can not find brightness-ui command:

```bash
echo "export PATH=$PATH:~/.local/bin" >> ~/.bashrc
```

- ### Method2 (From PyPI)

May NOT be up-to-date:

```bash
pip3 install brightnessUI # from PyPI
brightness-ui-install # install desktop and application menu shortcuts
```

If can not find brightness-ui command:

```bash
echo "export PATH=$PATH:~/.local/bin" >> ~/.bashrc
```

To uninstall:

```bash
pip3 uninstall brightnessUI
rm ~/Desktop/brightness-ui.desktop
sudo rm /usr/share/applications/brightness-ui.desktop
```

## Usage

```bash
brightness-ui
```

Or click the desktop icon on the Desktop or Application Menu. 

It is needed to allow launching for the desktop icon.

![img](https://gitee.com/shu-peixuan/brightnessUI/raw/master/pictures/allow_lauching.png)

It is recommended to add the ui in the application menu to favorites.

![img](https://gitee.com/shu-peixuan/brightnessUI/raw/master/pictures/add_to_favorites.png)

## Develop

Upload on PyPI:

```bash
sudo apt install twine -y
python3 setup.py sdist bdist_wheel
twine upload dist/*
```

## other ways to adjust backlight:

```bash
xrandr | grep " connected" | cut -f1 -d " "
```

用输出替换下面的DP-2：

```bash
xrandr --output DP-2 --brightness 0.8
```
