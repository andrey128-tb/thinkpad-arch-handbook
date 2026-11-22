# Tạo USB boot

Làm theo quy trình dưới đây

## Bước 1: Tải Arch Linux ISO

Nguồn chính thức: [Arch Linux Download](https://archlinux.org/download/)

Kéo xuống dưới cùng trang kiếm `Vietnam` -> chọn 1 link bất kì để tải xuống file ISO (1-2 GB).

## Bước 2: Xác minh ISO

Xác minh chữ kí PGP, SHA256, BLAKE2b. Cách xác minh có trong trang tải xuống của [Bước 1](#bước-1-tải-arch-linux-iso)

## Bước 3: Xác định USB boot

Dùng lệnh sau:

```bash
lsblk -o NAME,SIZE,MODEL,TRAN,FSTYPE,MOUNTPOINTS
```

Ví dụ USB boot là: `/dev/sdX`

> [!CAUTION]
> Phải xác định đúng thiết bị. Lệnh ghi ISO sẽ xóa dữ liệu trên USB được chọn.

## Bước 4: Tạo USB boot

Dùng lệnh sau:

```bash
sudo umount /dev/sdX*
sudo dd if=archlinux.iso of=/dev/sdX bs=4M status=progress oflag=sync
```

Thay `sdX` bằng thiết bị thực tế, không phải phân vùng như `sdX1`.

## Bước 5: Boot từ USB

- Khởi động lại ThinkPad
- Nhấn F12 để vào Boot Menu
- Chọn USB UEFI
- Khởi động Arch Linux Installation Medium

> [!WARNING]
> Arch ISO hiện không hỗ trợ Secure Boot mặc định, do đó cần tắt Secure Boot để boot USB cài đặt. Sau khi cài xong, có thể thiết lập lại Secure Boot nếu muốn.
