@ECHO OFF
TITLE Jason's Command Central v1.0.0
ECHO Jason's Command Central v1.0.0
ECHO +----------------------------+
ECHO OS Info
ECHO +----------------------------+
:: get os info
systeminfo | findstr /c:"OS Name"
systeminfo | findstr /c:"OS Version"
ECHO +----------------------------+
ECHO Choices
ECHO +----------------------------+
:: choices
ECHO 1 = Open Chrome
ECHO 2 = Get more info
ECHO 3 = Open Firefox
ECHO 4 = How to use
ECHO 5 = Changelogs
:: set up the choices
set choice=
set /p choice=Type a number to print.
if not '%choice%'=='' set choice=%choice:~0,1%
if '%choice%'=='1' goto chromeopenpls
if '%choice%'=='2' goto moreinfopls
if '%choice%'=='3' goto firefoxopenpls
if '%choice%'=='4' goto howtousepls
if '%choice%'=='5' goto changelog
ECHO "%choice%" isn't valid. Sorry!
:: run programs
goto start
:chromeopenpls
start chrome https://www.google.co.in/
ECHO Opened!
pause
goto end
:moreinfopls
ECHO +----------------------------+
ECHO More Info
ECHO +----------------------------+
ECHO ++--------------------------++
ECHO OS Info
ECHO ++--------------------------++
systeminfo | findstr /c:"OS Name"
systeminfo | findstr /c:"OS Version"
systeminfo | findstr /c:"System Type"
ECHO ++--------------------------++
ECHO Hardware Info
ECHO ++--------------------------++
systeminfo | findstr /c:"Total Physical Memory"
wmic cpu get name
wmic diskdrive get name,model,size
wmic path win32_videocontroller get name
wmic path win32_VideoController get CurrentHorizontalResolution,CurrentVerticalResolution
ECHO ++--------------------------++
ECHO Network Info
ECHO ++--------------------------++
ECHO Not yet...
pause
goto end
:firefoxopenpls
start firefox https://www.google.co.in/
ECHO Opened!
pause
goto end
:howtousepls
ECHO +----------------------------+
ECHO How to use
ECHO +----------------------------+
ECHO JCC is a very simple thing. Just simply input a number and magically watch
ECHO as a program opens to your desire. This was made to simplify the computer
ECHO to be as simple as possible.
pause
goto end
:changelog
ECHO v1.0.0
ECHO +----------------------------+
ECHO Release!
pause