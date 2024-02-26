@echo off

REM Set the working directory to D:\automation
cd /d "D:\automation"

REM Get the current date and time
for /f "delims=" %%a in ('wmic OS Get localdatetime ^| find "."') do set datetime=%%a

REM Format the date and time to be suitable for a folder name
set datetime=%datetime:~0,4%-%datetime:~4,2%-%datetime:~6,2%_%datetime:~8,2%-%datetime:~10,2%-%datetime:~12,2%

REM Create the folder
mkdir "%datetime%"

echo Folder created: %datetime%

git add .
git commit "another"
git push origin main