```markdown
### How to Mount and Partition a Drive on Linux

#### Step 1: Check if the Drive is Mounted
```bash
df -h
```

#### Step 2: Check if the Drive is Detected
```bash
lsblk
```

If the drive is not detected, reboot your system and check again:
```bash
sudo reboot
```

Re-run the first two steps to verify if the drive is detected:
```bash
lsblk
```

#### Step 3: Partition the Drive
Let's partition the drive using `gdisk`. For this example, we will partition the 1TB drive (`/dev/sdb`).

1. Run `gdisk` to create a new GPT partition table:
   ```bash
   sudo gdisk /dev/sdb
   ```

2. In the prompt, type `n` to create a new partition, then press Enter.

3. Choose a partition number (default: 4) and set the first and last sector (default values work for most cases). 

4. Change the partition type to `Linux filesystem` (hex code 8300), and then type `w` to write the changes to the disk.

The output should look like this:
```bash
GPT fdisk (gdisk) version 1.0.10

The protective MBR's 0xEE partition is oversized! Auto-repairing.

Partition table scan:
  MBR: protective
  BSD: not present
  APM: not present
  GPT: present

Found valid GPT with protective MBR; using GPT.

Command (? for help): n
Partition number (4-128, default 4):
First sector (34-1953525134, default = 1323008) or {+-}size{KMGTP}:
Last sector (1323008-1953525134, default = 1953523711) or {+-}size{KMGTP}:
Current type is 8300 (Linux filesystem)
Hex code or GUID (L to show codes, Enter = 8300):
Changed type of partition to 'Linux filesystem'

Command (? for help): w

Final checks complete. About to write GPT data. THIS WILL OVERWRITE EXISTING PARTITIONS!!

Do you want to proceed? (Y/N): y
OK; writing new GUID partition table (GPT) to /dev/sdb.
The operation has completed successfully.
```

#### Step 4: Format the New Partition
After partitioning the drive, format it with `ext4`:
```bash
sudo mkfs.ext4 /dev/sdb4  # Change sdb4 to your partition name
```

#### Step 5: Create a Mount Folder
Create a directory to mount the new drive:
```bash
sudo mkdir /mnt/dhdd_storage  # Change dhdd_storage to your folder name
```

#### Step 6: Mount the New Drive
Mount the new drive:
```bash
sudo mount /dev/sdb4 /mnt/dhdd_storage
```

Check if the drive is mounted:
```bash
df -h
```
You should see something like:
```bash
/dev/sdb4       916G   28K  869G   1% /mnt/dhdd_storage
```

#### Step 7: Make the Drive Mount Automatically on Boot
1. Get the drive's UUID:
   ```bash
   lsblk -f
   ```

   Example output:
   ```bash
   sdb4 ext4 1.0 892569c6-e1d9-4fcb-87db-********* 868.6G 0% /mnt/dhdd_storage
   ```

2. Copy the UUID of your partition (e.g., `892569c6-e1d9-4fcb-87db-*********`).

3. Edit the `fstab` file to auto-mount the drive on boot:
   ```bash
   sudo nano /etc/fstab
   ```

4. Add the following line to the bottom of the file:
   ```bash
   #Storage Mount
   /dev/disk/by-uuid/892569c6-e1d9-4fcb-87db-********* /mnt/dhdd_storage ext4 defaults 0 2
   ```

5. Save the file and exit.

#### Step 8: Reboot and Verify
Reboot the system:
```bash
sudo reboot
```

Check if the drive is mounted:
```bash
df -h
```

#### Step 9: Troubleshooting
If your system boots into emergency mode due to a mistake in `fstab`, you can edit the file again:
```bash
sudo nano /etc/fstab
```

Fix the issue, save the file, and reboot the system.

Now your drive should mount automatically every time the system starts.
```