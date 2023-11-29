# windows

## wsl2的使用

设置wsl默认版本`wsl --set-default-version 2`
更新wsl`wsl --update`
关闭wsl`wsl --shutdown`
查看安装版本`wsl -l --all -v`
导出系统`wsl --export Ubuntu-22.04 E:\WSL-Ubuntu-22.04.tar`
注销当前版本`wsl --unregister Ubuntu-22.04`
重新导入`wsl --import Ubuntu-22.04 E:\WSL-Ubuntu-22.04 E:\WSL-Ubuntu-22.04.tar --version2`
