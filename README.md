# termux miner
yes | pkg update && pkg upgrade
'''
yes | pkg install libjansson nano git
'''

git clone https://github.com/zikyu7/ccminer
cd ccminer
chmod +x ccminer start.sh
nano config.json

cd ..
nano ../usr/etc/bash.bashrc
cd ccminer/&&./start.sh


5. wallet
```
{
        "pools":[
        {
                "name": "Vipor",
        "url": "stratum+tcp://sg.vipor.net:5045",
                "timeout": 150,
                "disabled": 0
        },
        {
                "name": "vipor2",
        "url": "stratum+tcp://cn.vipor.net:5045",
                "timeout": 60,
                "time-limit": 600,
                "disabled": 0
        }],

        "user": "RWzo3bqZLfGiQCowKXVWRn9mrLg5VneA6X.donasi",
        "algo": "verus",
        "threads": 8,
        "cpu-priority": 1,
        "retry-pause": 5,
        "api-allow": "192.168.0.0/16",
        "api-bind": "0.0.0.0:4068"
}
```
7. Finally run the miner with:
```
~/ccminer/start.sh
```
