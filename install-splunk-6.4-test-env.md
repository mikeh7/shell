Installation instructions for Splunk v6.4 in a test environment
===============================================================


1. upload .tgz file to server with psftp
```
psftp username@servername
*cd /tmp* use /tmp as home directories are very small
*put filename.tgz*

quit
```
2. login to server with putty
```
note, update future version with screenshot
create saved session, by typing hostname in hostname box ie. wmd-wpkstap1.markets.global.lloydstsb.com
give it a name ie. wmd-pkstap1
click save
double click on name in saved sessions list
```
3. switch to the service account (svcsplunkd)
```
sudo su - svcsplunkd
type in your password
your prompt should show svcsplunkd@hostname
```
4. copy file from /tmp to svcsplunkd's home
```
cp /tmp/filename.tgz ~
```
5. check the install location and if necessary remove/backup old copy
```
ls /app/splunk
if there is a blue splunk folder, rename it with current date
mv /app/splunk/splunk /app/splunk/backup-yyyy-mm-dd
```
6. extract splunk to /app/splunk with
```
tar xvzf filename.tgz -C /app/splunk
```
7. change to install location and start splunk
```
cd /app/splunk/splunk/bin
./splunk start
```
8. page through the licence agreement and accept.
```
<space button>or 'f' key
when gets to 100%, type y
```
9. observe start up messages for any errors and note that the web ui is now available at http://hostname:8000
10. go to webpage and change admin password (default admin/changeme)

DONE!
