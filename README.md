# micropyos
Small os for micropython

This small os i made to work out how to use the micropython commands for wifi network ect.
you can copy files to and from a remote computer using scp and cal also get files from the internet with the wget command.

How to run micropyos
edit settings.py 
edit ssid and wifipassword for wifi connection
retmoteIP remotePath uname and upass are for scp copying of files.



import uos
remoteIP='192.168.0.3'
remotePath='/Users/thecodeman/Projects/micropyos/'
uname='username'
upass='password'
wifiSSID = 'ssid'
wifiPass = 'wifipassword'

sdCardCLK = 4
sdCardMOSI = 12
sdCardMiso = 2
sdCardCS =15

timeZone= 'PST8PDT'


autostartWiFi = True
autoMountSD = True

def initSDCard():
#	uos.sdconfig(uos.SDMODE_4LINE, sdCardCLK , sdCardMOSI, sdCardMiso, sdCardCS)
	uos.sdconfig(uos.SDMODE_4LINE)
	try:
	    uos.mountsd()
	except Exception as e:
	    print(e)



Once you get the settings file done just import micropyos.

Commands:

ls      - list files current directory
lr      - list files on remote server (optional directory)
cat     - display contents file
rm      - remove file
df      - display drive space
time    - display time and date
get     - scp from server
put     - scp to server
md      - make directory
rmdir   - remove directory
run     - run python script
edit    - edit file using pye
modules - list installed modules
reset   - reset board
wget    - get file over http and save to file
cp 		- copy files local 

