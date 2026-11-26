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

| Name                  | URL                                |
| --------------------- | ---------------------------------- |
| Argo CD               | <https://argocd.fjktkm.com>        |
| Argo CD Image Updater |                                    |
| External Secrets      |                                    |
| Longhorn              | <https://longhorn.fjktkm.com>      |
| kube-prometheus-stack | <https://grafana.fjktkm.com>       |
| cloudflared           |                                    |
| nitech-status         | <https://nitech-status.fjktkm.com> |
| pdf2image             |                                    |
| duel-masters-ml       |                                    |
| Outline               | <https://outline.fjktkm.com>       |

## Scheduled operations

| Operation                                  | Time (JST) | Schedule |
| ------------------------------------------ | ---------- | -------- |
| Longhorn Outline volume snapshots          | 02:00      | Daily    |
| Longhorn duel-masters-ml web data snapshot | 03:00      | Daily    |
| UDM SE UniFi OS auto-update                | 04:00      | Daily    |
| UniFi Network app auto-update              | 04:00      | Daily    |
| UniFi device auto-update                   | 05:00      | Daily    |
