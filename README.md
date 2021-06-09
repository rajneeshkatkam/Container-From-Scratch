# Basic-Container

### Command: sudo ./container <hostname> <root_filesystem_name> <network_namespace> <veth_netns_ip_addr> <veth_parent_ip_addr> <cgroup_enable_flag>

## For Cgroup Disabled:
	Container-1: sudo ./container tom rootfs netns1 10.1.1.1 10.1.1.2 0
	Container-2: sudo ./container tom2 rootfs-2 netns2 10.1.2.1 10.1.2.2 0

## For Cgroup Enabled:
	Container-1: sudo ./container tom rootfs netns1 10.1.1.1 10.1.1.2 1
	Container-2: sudo ./container tom2 rootfs-2 netns2 10.1.2.1 10.1.2.2 1


## Check for Cgroup values:

	sudo su

	echo "200000" > /sys/fs/cgroup/cpu/demo/cpu.cfs_quota_us
	cat /sys/fs/cgroup/cpu/demo/cpu.cfs_quota_us

	echo "1000000" > /sys/fs/cgroup/cpu/demo/cpu.cfs_period_us
	cat /sys/fs/cgroup/cpu/demo/cpu.cfs_period_us

	echo "22944" > /sys/fs/cgroup/cpu/demo/cgroup.procs
	cat /sys/fs/cgroup/cpu/demo/cgroup.procs
