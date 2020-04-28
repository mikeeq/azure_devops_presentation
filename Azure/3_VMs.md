
AMD's 2.35Ghz EPYC 7452 "Rome" Zen2 (PCs Ryzen 3xxx architecture)
  Base:2.35GHz
  Turbo: 3.35GHz
  CPU Cores: 32
  Threads: 64
  PCIe 4.0 x128
  DDR4 3200MHz
    Memory Channels:  8
    Per Socket Mem Bandwith: 204.8 GB/s
  Docs: <https://www.amd.com/en/products/cpu/amd-epyc-7452>

Q2 2020 GA expected in UK regions

D vs DS series:

Dasv4-series
ACU: 230-260
Premium Storage: Supported
Premium Storage caching: Supported
Live Migration: Supported
Memory Preserving Updates: Supported

- AMD SMT needs to be enabled, because the biggest offered VM is:
Standard_D96a_v4	96	384	2400	32	96000 / 1000 / 500	8 / 30000
3003.30 GBP

Standard_D64a_v4	64	256	1600	32	96000 / 1000 / 500	8 / 30000
2002.20 GBP
Standard_D64s_v3	64	256	512	32	128000/1024 (1600)	80000/1200	8/30000
2089,25 GBP
vs

Dav4-series
ACU: 230-260
Premium Storage: Not Supported
Premium Storage caching: Not Supported
Live Migration: Supported
Memory Preserving Updates: Supported

__________________________
DSv2-series
ACU: 210-250
Intel® Xeon® 8171M 2.1GHz (Skylake),
Intel® Xeon® E5-2673 v4 2.3 GHz (Broadwell),
Intel® Xeon® E5-2673 v3 2.4 GHz (Haswell) processors
- Intel Turbo Boost Technology 2.0

Dsv3-series VMs
ACU: 160-190
Intel® Xeon® E5-2673 v3 2.4 GHz (Haswell), (Intel Core 4gen)
Intel® Xeon® E5-2673 v4 2.3 GHz (Broadwell), (Intel Core 5gen, 20core, DDR4 2400, 2016)
Intel® Xeon® 8171M 2.1GHz (Skylake), (Intel Core 6gen, 6 × DDR4-2666, 2017)
- Intel Turbo Boost Technology 2.0
- Intel® Hyper-Threading Technology.


Linux nhsapp-dsv4-test 5.3.0-1018-azure #19-Ubuntu SMP Fri Mar 27 10:00:54 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux

apt-get update; apt-get install -y screen curl sysbench gdebi-core zip python
apt-get upgrade -y

geekbench 5.1.0

curl -LO http://cdn.geekbench.com/Geekbench-5.1.0-Linux.tar.gz
tar -xf Geekbench-5.1.0-Linux.tar.gz

curl -LO http://phoronix-test-suite.com/releases/repo/pts.debian/files/phoronix-test-suite_9.4.1_all.deb

apt-get install ./phoronix-test-suite_9.4.1_all.deb
phoronix-test-suite install pts/build-firefox
