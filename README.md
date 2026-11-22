# ThinkPad Arch Linux Handbook

Bộ tài liệu quản trị, cài đặt, khôi phục và bảo trì chiếc ThinkPad chạy Arch Linux + Hyprland + Serpantinum của tôi.

Mục lục

- [Mục tiêu](#mục-tiêu-của-repo)
- [Cấu trúc](#cấu-trúc-repo)
- [Tài liệu](#tài-liệu)

    [Installation](#installation)

    [System Management](#system-management)

    [Backup & Recovery](#backup--recovery)

    [Desktop Environment](#desktop-environment)

    [Hardware](#hardware)

    [Troubleshooting](#troubleshooting)

    [Script](#scripts)

- [Cấu hình máy hiện tại](#cấu-hình-máy-hiện-tại)

    [Phần cứng](#phần-cứng)

    [Phần mềm](#phần-mềm)

- [Hạn chế](#hạn-chế-của-repo)
- [Triết lí](#triết-lí)
- [Tuyên bố miễn trừ trách nhiệm](#tuyên-bố-miễn-trừ-trách-nhiệm)

## Mục tiêu của repo

- Khi cài lại Arch Linux, tôi có thể làm theo từng bước mà không phải nhớ lại mọi thứ.

- Khi cập nhật hệ thống, biết chính xác cần chạy lệnh nào và cần kiểm tra gì.

- Khi muốn backup sang USB, có quy trình an toàn, tránh ghi đè hoặc xóa nhầm dữ liệu.

- Khi gặp lỗi, có nơi ghi lại nguyên nhân, cách chẩn đoán và cách khắc phục.

- Khi đổi laptop hoặc cài lại hệ thống, có thể tái tạo môi trường làm việc gần như cũ.

## Cấu trúc repo

```text
thinkpad-arch-handbook/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── installation/
│   ├── 01-preparation.md
│   ├── 02-create-bootable-usb.md
│   ├── 03-archinstall.md
│   ├── 04-first-boot.md
│   ├── 05-security-hardening.md
│   └── 06-restore-system.md
│
├── system/
│   ├── daily-commands.md
│   ├── package-management.md
│   ├── system-update.md
│   ├── systemd-services.md
│   ├── disk-management.md
│   ├── hardware-information.md
│   └── troubleshooting-commands.md
│
├── backup/
│   ├── backup-strategy.md
│   ├── backup-to-usb.md
│   ├── restore-data.md
│   └── package-backup.md
│
├── desktop/
│   ├── hyprland.md
│   ├── serpantinum.md
│   ├── shell-and-terminal.md
│   ├── applications.md
│   └── configuration-files.md
│
├── troubleshooting/
│   ├── README.md
│   └── template.md
│
├── hardware/
│   ├── thinkpad-e14-gen7.md
│   └── drivers-and-firmware.md
│
└── scripts/
    ├── backup-home.sh
    ├── export-packages.sh
    └── system-info.sh
```

Trong đó:

|**Thư mục**|**Vai trò**|
|-----------|-----------|
|`installation/`|Cài đặt và tái cài đặt Arch|
|`system/`|Lệnh linux và quản trị hệ thống|
|`backup/`|Sao lưu, phục hồi dữ liệu|
|`desktop/`|Hyprland, Serpantinum và giao diện|
|`troubleshooting/`|Nhật kí lỗi và cách xử lí|
|`hardware/`|Phần cứng ThinkPad|
|`scripts/`|Các scripts tự động hóa|

## Tài liệu

### Installation

- [Preparation](installation/01-preparation.md)
- [Create Bootable USB](installation/02-create-bootable-usb.md)
- [Archinstall](installation/03-archinstall.md)
- [First Boot](installation/04-first-boot.md)
- [Security Hardening](installation/05-security-hardening.md)
- [Restore System](installation/06-restore-system.md)

### System Management

- [Daily Commands](system/daily-commands.md)
- [Package Management](system/package-management.md)
- [System Update](system/system-update.md)
- [Systemd Services](system/systemd-services.md)
- [Disk Management](system/disk-management.md)
- [Hardware Information](system/hardware-information.md)

### Backup & Recovery

- [Backup Strategy](backup/backup-strategy.md)
- [Backup to USB](backup/backup-to-usb.md)
- [Restore Data](backup/restore-data.md)
- [Package Backup](backup/package-backup.md)

### Desktop Environment

- [Hyprland](desktop/hyprland.md)
- [Serpantinum](desktop/serpantinum.md)
- [Shell & Terminal](desktop/shell-and-terminal.md)
- [Applications](desktop/applications.md)

### Hardware

- [ThinkPad E14 Gen 7](hardware/thinkpad-e14-gen7.md)
- [Drivers & Firmware](hardware/drivers-and-firmware.md)

### Troubleshooting

- [Known Issues](troubleshooting/README.md)

### Scripts

- `scripts/backup-home.sh`
- `scripts/export-packages.sh`
- `scripts/system-info.sh`

## Cấu hình máy hiện tại

Lần cập nhật cấu hình cuối: 22/11/2026

### Phần cứng

- Model: Lenovo ThinkPad E14 Gen 7.
- CPU: Intel Core Ultra 5 225H.
- RAM: 16 GB.
- SSD: Samsung NVMe 512 GB.
- Kiến trúc: x86_64.
- GPU: Intel integrated graphics.

### Phần mềm

- OS: Arch Linux
- Kernel: 7.3.4-arch1-2
- Desktop Environment: Hyprland
- Desktop Shell: [Serpantinum v2.5.2 (Ilyamiro)](https://github.com/ilyamiro/serpantinum)
- Terminal Emulator: kitty
- Shell: zsh

- Bootloader: systemd-boot
- Partition: UEFI/GPT
- File system: ext4

## Hạn chế của repo

- Chưa hướng dẫn quá chi tiết ở các bước, các bước vẫn nên tự tra cứu hoặc cập nhật thêm nếu chưa hiểu.
- Chỉ cập nhật cho trường hợp đã cài linux trước đó, đối với từ window chuyển sang linux, nên tự nghiên cứu thêm (dual boot và key bản quyền).
- Repo này chỉ có hiệu lực trong thời gian ngắn, thời gian dài nếu chưa cập nhật lại có khả năng outdate

## Triết lí

- Hiểu trước khi thực thi lệnh.
- Ưu tiên các repo chính thức.
- Luôn kiểm tra kĩ các script AUR (lỗ hổng bảo mật).
- Tránh cập nhật một phần, ưu tiên cập nhật toàn bộ các phần của hệ thống để mọi thứ đồng bộ.
- Thường xuyên giữ các bản backup ngoài.
- Ghi lại các thay đổi quan trọng.

## Tuyên bố miễn trừ trách nhiệm

Lệnh và cấu hình dành dựa theo máy và môi trường của tôi. Hãy xem xét kĩ toàn bộ câu lệnh trước khi thực thi.
