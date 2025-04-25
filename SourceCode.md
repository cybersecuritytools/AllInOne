###Source code

@echo off
:begin
cls
color
echo.
echo ----------------
echo   hacker sites
echo ----------------
echo.
echo digite "1" para ver os sites
echo digite "2" para ver os downloads
set /p op=@
if %op%==1 goto menu
if %op%==2 goto downloads
:menu
cls
echo.
echo ----------------
echo       menu
echo ----------------
echo.
echo 1. grabify
echo 2. shodan
echo 3. deepseek
echo 4. proton mail
echo.
set /p op=@
if %op%==1 goto grabify
if %op%==2 goto shodan
if %op%==3 goto deepseek
if %op%==4 goto protonmail
:grabify
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
start https://grabify.link
goto begin
:shodan
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
start https://shodan.io
goto begin
:deepseek
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
start https://chat.deepseek.com
goto begin
:protonmail
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
start https://mail.proton.me
goto begin

:downloads
cls
echo.
echo -----------------
echo     downloads
echo -----------------
echo.
echo 1.WSL
echo 2.zenmap
echo 3.wireshark
echo 4.burpsuite
echo 5.OWASPzap
set /p op=@
if %op%==1 goto WSL
if %op%==2 goto zenmap
if %op%==3 goto wireshark
if %op%==4 goto burpsuite
if %op%==5 goto OWASPzap
:WSL
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
start /b powershell -Command "wsl --install ubuntu"
pause
goto begin
:zenmap
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
bitsadmin /transfer job /download /priority high "https://npcap.com/dist/npcap-1.82.exe" "C:\"
start /B "" "C:\npcap-1.82.exe"
:loop
tasklist | find "npcap-1.82.exe" > nul
if not errorlevel 1 (
  timeout /t 5 > nul
  goto :loop
)
bitsadmin /transfer job /download /priority high "https://nmap.org/dist/nmap-7.95-setup.exe" "C:\"
start /B "" "C:\nmap-7.95-setup.exe"
:loopB
tasklist | find "nmap-7.95-setup.exe"
if not errorlevel 1 (
	timeout /t 5 > nul
	goto :loopB
)
pause
goto begin
:wireshark
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
bitsadmin /transfer job /download /priority high "https://2.na.dl.wireshark.org/win64/Wireshark-4.4.6-x64.exe"
start /B "" "C:\Wireshark-4.4.6-x64.exe"
:loopC
tasklist | find "Wireshark-4.4.6-x64.exe"
if not errorlevel 1 (
  timeout /t 5 > nul
  goto :loopC
)
pause
goto begin
:burpsuite
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
bitsadmin /transfer job /download /priority high "https://portswigger.net/burp/releases/download?product=community&version=2024.1.1&type=Windows" "C:\"
start /B "" "C:\BurpSuiteCommunity-2024.1.1.exe"
:loopD
tasklist | find "BurpSuiteCommunity-2024.1.1.exe"
if not errorlevel 1 (
  timeout /t 5 > nul
  goto :loopD
)
pause
goto begin
:OWASPzap
cls
echo.
echo Pressione qualquer tecla para continuar
echo.
pause >nul
bitsadmin /transfer job /download /priority high "https://github.com/zaproxy/zaproxy/releases/download/v2.16.1/ZAP_2_16_1_windows.exe" "C:\"
start /B "" "C:\ZAP_2_16_1_windows.exe"
:loopE
tasklist | find "ZAP_2_16_1_windows.exe"
if not errorlevel 1 (
  timeout /t 5 > nul
  goto :loopE
)
pause
goto begin
