# RAM-Cache-Folder

:: APPDATA     =%USERPROFILE%\AppData\Roaming
:: LOCALAPPDATA=%USERPROFILE%\AppData\Local

@echo OFF

CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\Cache"                        "B:\Cache\Brave\Default\Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\Code Cache"                   "B:\Cache\Brave\Default\Code Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\GPUCache"                     "B:\Cache\Brave\Default\GPUCache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\Service Worker"               "B:\Cache\Brave\Default\Service Worker"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\Session Storage"              "B:\Cache\Brave\Default\Session Storage"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Default\session_profiles\Tor Profile" "B:\Cache\Brave\Tor Profile"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Guest Profile\Cache"                  "B:\Cache\Brave\Guest Profile\Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Guest Profile\Code Cache"             "B:\Cache\Brave\Guest Profile\Code Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\Guest Profile\GPUCache"               "B:\Cache\Brave\Guest Profile\GPUCache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\ShaderCache"                          "B:\Cache\Brave\ShaderCache"
CALL :CreateSymLink "%LOCALAPPDATA%\BraveSoftware\Brave-Browser\User Data\System Profile\Cachex"                "B:\Cache\Brave\System Profile\Cache"

CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\Default\Cache"           "B:\Cache\Chrome\Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\Default\Code Cache"      "B:\Cache\Chrome\Code Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\Default\GPUCache"        "B:\Cache\Chrome\GPUCache"
CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\Default\Service Worker"  "B:\Cache\Chrome\Service Worker"
CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\Default\Session Storage" "B:\Cache\Chrome\Session Storage"
CALL :CreateSymLink "%LOCALAPPDATA%\Google\Chrome\User Data\ShaderCache"             "B:\Cache\Chrome\ShaderCache"

CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Cache"           "B:\Cache\Edge\Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Code Cache"      "B:\Cache\Edge\Code Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\GPUCache"        "B:\Cache\Edge\GPUCache"
CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Service Worker"  "B:\Cache\Edge\Service Worker"
CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Session Storage" "B:\Cache\Edge\Session Storage"
CALL :CreateSymLink "%LOCALAPPDATA%\Microsoft\Edge\User Data\ShaderCache"             "B:\Cache\Edge\ShaderCache"

CALL :CreateSymLink "%LOCALAPPDATA%\Mozilla\Firefox\Profiles" "B:\Cache\Firefox"

CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable"                 "B:\Cache\Opera\Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable\Code Cache"      "B:\Cache\Opera\Code Cache"
CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable\GPUCache"        "B:\Cache\Opera\GPUCache"
CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable\Service Worker"  "B:\Cache\Opera\Service Worker"
CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable\Session Storage" "B:\Cache\Opera\Session Storage"
CALL :CreateSymLink "%LOCALAPPDATA%\Opera Software\Opera Stable\ShaderCache"     "B:\Cache\Opera\ShaderCache"



::To move the Java file in the Ramdrive, you have to manually do the following steps:
::1. Go here: %SYSTEMDRIVE%\Users\%USERNAME%\AppData\LocalLow\Sun\Java\Deployment\
::2. Edit the document in Notepad: deployment.properties
::3. Add or edit the field: deployment.user.cachedir=B\:\\Cache\\Java
::4. Go to Java properties and adjust the amount of disk space to at most half of the ram drive.

MD "B:\Cache\Java"

@PAUSE
EXIT /B

:CreateSymLink
:: Remove both folders (the original and the destination)
	RD /S /Q %1
	RD /S /Q %2
:: Creates the folder and the link
	MD %2
	ECHO MKLINK /D %1 %2
	MKLINK /D %1 %2
GOTO :EOF



::SDG

:: Those are the folders to be created in the RAMDisk

TEMP
Cache\IE\ActionCenterCache
Cache\IE\AppCache
Cache\IE\INetCache
Cache\IE\PRICache
Cache\IE\WebCache
Cache\Firefox
Cache\Chrome\Cache
Cache\Chrome\Code Cache
Cache\Chrome\GPUCache
Cache\Chrome\Service Worker
Cache\Chrome\Session Storage
Cache\Chrome\ShaderCache
Cache\Opera\Cache
Cache\Opera\Code Cache
Cache\Opera\GPUCache
Cache\Opera\Service Worker
Cache\Opera\Session Storage
Cache\Opera\ShaderCache
Cache\Brave\Default\Cache
Cache\Brave\Default\Code Cache
Cache\Brave\Default\GPUCache
Cache\Brave\Default\Service Worker
Cache\Brave\Default\Session Storage
Cache\Brave\Guest Profile\Cache
Cache\Brave\Guest Profile\Code Cache
Cache\Brave\Guest Profile\GPUCache
Cache\Brave\ShaderCache
Cache\Brave\System Profile\Cache
Cache\Brave\Tor Profile	
Cache\Edge\Cache
Cache\Edge\Code Cache
Cache\Edge\GPUCache
Cache\Edge\Service Worker
Cache\Edge\Session Storage
Cache\Edge\ShaderCache
