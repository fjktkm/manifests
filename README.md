# Manifests

## Machines

| Hostname | Product                   | OS                            | CPU                                     | Memory | Storage          | Role                |
| -------- | ------------------------- | ----------------------------- | --------------------------------------- | ------ | ---------------- | ------------------- |
| rpi-01   | Raspberry Pi 5            | Raspberry Pi OS Lite (trixie) | Broadcom BCM2712 (Cortex-A76, 4C/4T)    | 8 GB   | 256 GB NVMe SSD  | control-plane, etcd |
| rpi-02   | Raspberry Pi 5            | Raspberry Pi OS Lite (trixie) | Broadcom BCM2712 (Cortex-A76, 4C/4T)    | 8 GB   | 256 GB NVMe SSD  | control-plane, etcd |
| rpi-03   | Raspberry Pi 5            | Raspberry Pi OS Lite (trixie) | Broadcom BCM2712 (Cortex-A76, 4C/4T)    | 8 GB   | 256 GB NVMe SSD  | control-plane, etcd |
| opt-01   | Dell OptiPlex 3080 Micro  | Ubuntu Server 26.04 LTS       | Intel Core i5-10500T (6C/12T)           | 8 GB   | 256 GB NVMe SSD  | worker              |
| opt-02   | Dell OptiPlex 3080 Micro  | Ubuntu Server 26.04 LTS       | Intel Core i5-10500T (6C/12T)           | 8 GB   | 256 GB NVMe SSD  | worker              |
| opt-03   | Dell OptiPlex 3080 Micro  | Ubuntu Server 26.04 LTS       | Intel Core i5-10500T (6C/12T)           | 8 GB   | 256 GB NVMe SSD  | worker              |

## Services

| Name          | URL                                |
| ------------- | ---------------------------------- |
| Argo CD       | <https://argocd.fjktkm.com>        |
| Longhorn      | <https://longhorn.fjktkm.com>      |
| Headlamp      | <https://headlamp.fjktkm.com>      |
| cloudflared   |                                    |
| nitech-status | <https://nitech-status.fjktkm.com> |
| pdf2image     |                                    |
