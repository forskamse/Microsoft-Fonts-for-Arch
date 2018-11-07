# Microsoft-Fonts-for-Arch
## Usage
To enhance the experience of wine on Arch-Based system, you should have to install [Microsoft Fonts](https://wiki.archlinux.org/index.php/Microsoft_fonts) from AUR.  
As an example, follow the steps to install ttf-ms-win10:

```
yaourt ttf-ms-win10
```
After you have download the source from AUR to local yaourt working directory (Probably /tmp/yaourt-tmp-\*\*/aur-ttf-ms-win10/), clone this repository and put all the files to the working directory. Remember that you sholud overwrite the original PKGBUILD with mine.
Continue to compile ttf-ms-win10.

## Why should you overwrite PKGBUILD
**Trouble：**  
Marlett.ttf was missing when I extracted the fonts from a installed Windows 10. So I encountered this problem:
```
Retrieving sources...
Unable to find file://marlett.ttf, please read the PKGBUILD
... ...
Validating source files with sha256sums...
marlett.ttf ... FAILED
... ...
ERROR: One or more files did not pass the validity check!
```
**Solution：**  
Edit PKGBUILD（Probably on /tmp/yaourt-tmp-\*\*/aur-ttf-ms-win10/）  
(1). Delete the term 'marlett.ttf' in _ttf_ms_win10()：  
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
(2). Delete the sha256sum corresponding to 'marlett.ttf' in sha256sums=():
```
sha256sums=(
... ...
 'b7397adf2dcc24ca790348a3c26deb2122b45e5728fd25fc588de4cf5a75b469'
... ...
```
