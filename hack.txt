@echo off

REM Set the working directory to D:\automation
cd /d "D:\githack"

REM Get the current date and time
for /f "delims=" %%a in ('wmic OS Get localdatetime ^| find "."') do set datetime=%%a

REM Format the date and time
set formatted_datetime=%datetime:~0,4%-%datetime:~4,2%-%datetime:~6,2%_%datetime:~8,2%-%datetime:~10,2%-%datetime:~12,2%

REM Create and write to a text file
echo %formatted_datetime% > "%formatted_datetime%.txt"

echo File created: "%formatted_datetime%.txt"

REM Commit and push to Git
git add .
git commit -m "another"
git push origin main
