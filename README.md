# jellyfin-rpi3b-docker-compose
Docker Compose YML for Raspberry Pi 3 B

Jellyfin is very resource hungry and was blocking my entire Raspberry Pi 3B a few minutes after starting, until I limited the resouces available to the docker through this docker-compose definition. The lines in the docker-compose.yml for this are:

mem_limit: 250m
cpus: 0.50

In order through this docker to work, it is also required to enable cgroups in Raspberry Pi 3B, by editing the /boot/cmdline.txt and adding the following lines: 'cgroup_enable=memory swapaccount=1 cgroup_memory=1 cgroup_enable=cpuset'.
