# Dùng ArchInstall để cài Arch nhanh gọn tiện lợi

Dùng các lệnh sau trước khi chạy:

```bash
lsblk -f
ip link
timedatectl
```

Nếu có dùng Wi-fi:

```bash
iwctl
```

Trong giao diện `iwctl`

```bash
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect TEN_WIFI
exit
```

Kiểm tra Internet:

```bash
ping -c 4 archlinux.org
```

Chạy trình cài đặt:

```bash
archinstall
```

|**Mục cấu hình**|**Nội dung cần chọn**|
|----------------|---------------------|
|Disk configuration|Chọn SSD NVMe đúng|
|Partitioning|UEFI/GPT|
|Bootloader|systemd-boot|
|Filesystem|ext4|
|Root|`/`|
|Home|`/home`|
|Swap|tùy nhu cầu|
|Kernel|linux và linux-lts|
|Network|NetworkManager|
|Audio|PipeWire|
|Profile|Minimal hoặc phù hợp với Hyprland|
|User|Tài khoản người dùng thông thường|
|Authentication|Mật khẩu mạnh|
|Timezone|Asia/Ho_Chi_Minh|
|Locale|en_US.UTF-8 hoặc theo nhu cầu|
|Additional packages|Các gói thực sự cần thiết|

> [!WARNING]
> Việc dùng archinstall để chia phân vùng tự động mặc định sẽ ghi đè toàn bộ dữ liệu. Do đó hãy chắc chắn biết bản thân đang làm gì.
<!--break block-->
> [!TIP]
> Khoảng chia phân vùng hợp lí: `/`:60-200 GB, `/home`: phần còn lại nếu không tính cho swap.
> Phân vùng lí tưởng (theo cấu hình máy hiện tại): `/`: 100 GB, `/home`: 400 GB, `swap`: 8 GB, khác: còn lại
