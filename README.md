# notes

## 对于系统重装后，vscode无法更新的修复
系统重装后，找到vscode的安装目录，执行code.exe, 可以正常打开，但是无法更新。

执行更新是，vscode会在系统盘的C:\Program Files\目录下新建Microsoft VS Code文件，并一直反复这个过程，文件更新失败。

同时也不应该在C:\Program Files\Microsoft VS Code下创建vs。

修复步骤：
- 1、打开注册表，找到以下路径：
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\{EA457B21-F73E-494C-ACAB-524FDE069978(编号不固定)}_is1
- 2、将这里面所有设置为C:\Program Files\Microsoft VS Code的项全部改为vscode的实际安装路径。
- 3、重启vscode，检查更新，这时就可以正常更新了。
