# Manjaro安装Win10字体错误记录
安装Win10字体 - ttf-ms-win10-zh_cn时，提取Win10字体缺少marlett.ttf，提示错误：  
```
Retrieving sources...
Unable to find file://marlett.ttf, please read the PKGBUILD
... ...
Validating source files with sha256sums...
marlett.ttf ... FAILED
... ...
ERROR: One or more files did not pass the validity check!
```
Solution：  
编辑PKGBUILD文件（位于/tmp/yaourt-tmp-**/aur-ttf-ms-win10-zh_cn/）  
(1). 删除_ttf_ms_win10()下的marlett.ttf项：  
```
_ttf_ms_win10=(
#########################################################################################
# Normal         Bold          Italic        Bold+Italic    #  Full name                #
#########################################################################################
... ...
marlett.ttf                                                 # Marlett
... ...
)
```
(2). 删除sha256sums=() 下marlett.ttf对应的sha256sum：  
```
sha256sums=(
... ...
 'b7397adf2dcc24ca790348a3c26deb2122b45e5728fd25fc588de4cf5a75b469'
... ...
```
