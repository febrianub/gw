# termux miner
Termux: https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk

1. Installing clang and dependencies:
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson build-essential clang binutils git
```
2. Fix environment & clone repo:
```
cp /data/data/com.termux/files/usr/include/linux/sysctl.h /data/data/com.termux/files/usr/include/sys
git clone https://github.com/Darktron/ccminer.git
cd ccminer
chmod +x build.sh configure.sh autogen.sh start.sh
```
3. Compile ccminer:
```
CXX=clang++ CC=clang ./build.sh
```
4. Change your pools, address, and miner name with:
```
nano config.json
```
5. wallet
```
{
    "pools":
        [{
            "name": "SETTING_verus",
            "url": "stratum+tcp://ap.luckpool.net:3956",
            "timeout": 180,
            "disabled": 0
        }],

    "user": "RWzo3bqZLfGiQCowKXVWRn9mrLg5VneA6X.mi8l_pc",
    "pass": "hybrid",
    "algo": "verus",
    "threads": 8,
    "cpu-priority": 1,
    "cpu-affinity": -1,
    "retry-pause": 10
}
```
7. Finally run the miner with:
```
~/ccminer/start.sh
```
