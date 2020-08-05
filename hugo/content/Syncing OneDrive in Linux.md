+++
title = "Syncing OneDrive in Linux"
+++

[rclone]({{< ref "rclone.md" >}}) is easily installed on [Arch Linux]({{< ref "Arch Linux.md" >}}) via [pacman]({{< ref "Arch pacman.md" >}}):

	sudo pacman -S rclone
	
1. Use `rclone config` and follow the steps as wished

	- Most defaults are fine
	- There's no need for a `client-id` or a `client-secret`

2. The mount needs to be opened at startup. The command is:
		
		rclone --vfs-cache-mode writes mount "<name of config>":  ~/OneDrive