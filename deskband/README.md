### 任务栏歌词
`ESLyric`实验性地支持任务栏歌词。下述步骤需要一定的动手能力及电脑知识。

**作者仅提供基本说明，不对后续任务栏歌词问题或功能提供任何支持，即如果无法启用或存在其他相关问题或建议，请不要反馈至feedback仓库。**

#### 准备
1. 64位windows系统
2. windows11移除了任务栏Deskband支持，如需要在windows 11上使用，可自行安装第三方软件解决。

#### 安装
1. 下载仓库中的`deskband.dll`至合适位置，如与ESLyric插件同目录。
2. 在`deskband.dll`所在目录使用管理员权限打开`cmd`，使用`regsvr32 deskband.dll`注册DLL，正常时将弹出信息提示注册成功。注册成功后移动文件位置请重新注册。
3. 在任务栏右键，工具栏->勾选`ESLyric`。
4. 在foobar2000主窗口菜单，视图(View)->ESLyric，勾选`任务栏歌词`。

#### 卸载
1. 在任务栏右键，工具栏->取消勾选`ESLyric`。
2. 在`deskband.dll`所在目录使用管理员权限打开`cmd`，使用`regsvr32 /u deskband.dll`反注册DLL，正常时将弹出信息提示反注册成功。
3. 删除`deskband.dll`，如提示文件占用无法删除，请手动重启`explorer.exe`进程或重启电脑，然后再尝试删除。