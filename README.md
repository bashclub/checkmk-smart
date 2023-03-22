# checkmk-smart
Smart Plugin for Check_MK Monitoring System

Testet on Check_MK 2.0.24

Howto Monitor advanced Smart on Linux with Check_MK

Server Side:

Login per SSH to Check_MK Server
su - sitename
curl https://raw.githubusercontent.com/bashclub/checkmk-smart/main/disk_smart_info-0.6-2.mkp > disk_smart_info-0.6-2.mkp
mkp install disk_smart_info-0.6-2.mkp
exit
omd restart sitename

Client Side

curl https://raw.githubusercontent.com/bashclub/checkmk-smart/main/disk_smart_info.py > /usr/lib/check_mk_agent/plugins/disk_smart_info
chmod +x /usr/lib/check_mk_agent/plugins/disk_smart_info
rm /usr/lib/check_mk_agent/plugins/smart # removes obsolet faulty original plugin if present

When done, start client Discovery and activate new Services
