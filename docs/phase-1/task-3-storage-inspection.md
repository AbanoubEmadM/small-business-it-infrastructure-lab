# Task 3: Inspect Storage

## 1. Objective

Inspect the RHEL 9 server's storage configuration to understand disk capacity, partition layout, filesystem types, mount points, and directory space usage.

The purpose of this task is to establish a storage baseline and identify potential disk-space concerns before deploying infrastructure services.

## 2. Tools Used

| Command | Purpose |
|---|---|
| `df -h` | Display filesystem capacity, used space, available space, and utilization |
| `du -h` | Investigate disk-space usage by files and directories |
| `lsblk -f` | Inspect block devices, partitions, filesystem types, UUIDs, and mount points |

## 3. Filesystem Utilization

The following results were observed using `df -h`.

| Filesystem | Size | Used | Available | Use | Mount Point |
|---|---|---|---|---|---|
| `/dev/sda5` | 29 GB | 4.1 GB | 25 GB | 15% | `/` |
| `/dev/sda1` | 495 MB | 246 MB | 250 MB | 50% | `/boot` |
| `/dev/sda2` | 7.0 GB | 173 MB | 6.9 GB | 3% | `/home` |

The system also displayed virtual and memory-backed filesystems, which are not ordinary disk partitions.

## 4. Findings

- **Root filesystem (`/`):** Approximately 15% utilized, with about 25 GB available.
- **Boot filesystem (`/boot`):** Approximately 50% utilized. This should be monitored as kernel updates accumulate.
- **Home filesystem (`/home`):** Approximately 3% utilized, with substantial free space.
- **Separate filesystems:** The root, boot, and home directories are mounted on separate partitions, allowing their capacity and utilization to be monitored independently.

No immediate filesystem capacity issue was apparent from the recorded `df -h` output.

## 5. Disk and Partition Inspection

The `lsblk -f` command was used to inspect the block-device hierarchy and filesystem information.

- **Filesystem types:** XFS
- **Mount points:** `/boot`, `/home`, `/`
- **Unmounted partitions:** None

## 6. Directory Space Usage

The `du -h` command was used to investigate directory space consumption.

- **Largest directory:** `/usr/`

## 7. Conclusion

The initial storage inspection established a baseline for filesystem capacity and utilization on the RHEL 9 server. The recorded output showed that the root and home filesystems had substantial available space, while the boot filesystem was half utilized.

This baseline can be used for future capacity monitoring and troubleshooting. No storage configuration changes were made during this inspection.