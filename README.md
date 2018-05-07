# verium-docker
Dockerized vrm miner for targets amd64, rpi, orangepizero based on jenstuxen/magi-docker repo

It builds from git repository https://github.com/VeriumReserve/veriumMiner

Raspberry pi images based on resin images https://resin.io/.

Idea from https://www.novaspirit.com/2017/10/19/crypto-mining-sbc/.

# Examples
replace `-o stratum+tcp://ip:port -u user.worker -p password` with your own
## Latest by auto detected architecture
* benchmark
```bash
docker run --rm -it urukalo/verium-docker cpuminer --benchmark
```
* example
```bash
docker run -d urukalo/verium-docker cpuminer -o stratum+tcp://ip:port -u user.worker -p password
```
## specify arhitecture/device/os (see tags)
```bash
docker run -d jenstuxen/magi-docker:alpine-armhf-rpi2 m-minerd -o stratum+tcp://ip:port -u user.worker -p password
```

# Build
```bash
git clone https://github.com/urukalo/verium-docker
cd verium-docker
cd rpi/2/ #or your specific device
docker build -t local/verium-docker:rpi2 .
docker run -it local/verium-docker:rpi2 cpuminer --benchmark
```
