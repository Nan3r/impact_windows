sourcee:https://github.com/maaaaz/CrackMapExecWin/wiki/How-to-compile-CrackMapExec-for-Windows

##1. Set up the compilation environment

python-2.7.10.msi
[Git-2.6.1-32-bit.exe] (https://github.com/git-for-windows/git/releases/download/v2.6.1.windows.1/Git-2.6.1-32-bit.exe) to clone the impacket repo
crackmapexec prerequisities with pip install --upgrade -r requirements.txt
VCForPython27.msi to be able to compile the pyinstaller core module
pyinstaller with pip install pyinstaller
##2. Monkey-Patch the original code General rules to ensure Windows compatibility:

Remove references to Unix stuff like os.geteuid(), that don't make sense on Windows
Patch the code section related to term colors from
from termcolor import cprint, colored
to

from termcolor import cprint, colored
import colorama
colorama.init()
Take a look at the following link for more information on that topic.
3. Remove illegal chars in created/accessed filenames

##3. Compile pyinstaller --clean --onefile crackmapexec.py

##4. Profit Find the executable in the created dist folder


1.安装python,
pyinstaller(http://www.microsoft.com/en-us/download/details.aspx?id=44266)  ,
install python project,
pip install 
{
pyinstaller
pyasn1
Crypto
pycrypto
}
2.去除一些linux 下的操作函数：os.getuid() 这种函数
如果有颜色输出的，见英文

3.去除文件名中的非法字符
4.pyinstaller --clean --onefile psexec.py 