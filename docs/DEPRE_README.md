Installation of Ubuntu:
* Disable both secure boot (how this is disabled depends on the motherboard system) and fast boot.
* (Optional) If you are using a laptop, pay attention to how the hard drive is read (RAID/AHCI).
* UEFI and legacy boot mode.
* Mannually allocate hard drive space. If you are installing multiple ubuntu systems, it’s recommended to allocate a large data partition for all the systems and leave minimal space to each system.
* Don’t use ‘sudo apt-get upgrade’ under any circumstances.

Setting up Ubuntu system:
* Set up apt source to let it point to mainland mirrors.
https://zhuanlan.zhihu.com/p/61228593
* Set up Anaconda which is highly recommended since it helps you to separate python environments and bundle compatible python libraries together.
* Set up pip/conda source. Make them point to Tsinghua mirror.
https://blog.csdn.net/xd_wjc/article/details/80587488
https://blog.csdn.net/u014061630/article/details/92744781
* (Optional) Set up a VPN and polipo to make it easier to access Github.

Setting up CUDA and nvidia driver:
* Some cards are not compatible with drivers of older version.
* Install nvidia driver: Using apt is basically the same as using the ‘Software & Updates’ in system setting. Or you can download debian files (or is it runfiles?) from nvidia official site to install a driver of any version. Things to note: a. reboot the system after installing the driver; b. build-essential and install system kernel header when you are installing from runfiles; c. remove all nvidia related packages if you decide to install a driver of different version (simply using ‘sudo apt-get remove --purge nvidia*’ is not recommended but it’s easy).
* Install runtime cuda any way you see fit since you can always switch version by changing the environment variable. (add paths to $PATH and $LD_LIBRARY_PATH after the installation)
* Download cudnn, unzip it and copy the files to the correct directories to set up cudnn.
* Running cudnn demo is the best way to validate an installation of cuda and cudnn.

