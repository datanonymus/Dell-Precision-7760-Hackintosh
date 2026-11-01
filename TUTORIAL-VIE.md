[Change to English tutorial here!](https://github.com/datanonymus/Dell-Precision-7760-Hackintosh/blob/main/TUTORIAL-ENG.md)

# 📖 Hướng dẫn cài đặt chi tiết

### 🛠 Các thiết bị cần chuẩn bị

1. 1 chiếc USB dung lượng từ 1GB trở lên để nhét OpenCore và Recovery của Mac.
2. Não 🐔!

### ⚙️ Hướng dẫn chi tiết

**Bước 1:** Vào Windows -> Mở `Disk Management` -> Cắt ra 1 phân vùng từ 50GB trở lên và format nó theo chuẩn NTFS.

**Bước 2:** Format USB theo định dạng bắt buộc là `FAT32`.

**Bước 3:** Vào trang GitHub chứa source EFI, chọn `Code` -> `Download Zip` để tải về máy. Sau đó giải nén ra USB. Đảm bảo rằng thư mục `EFI` nằm ở ngoài cùng của ổ USB.

**Bước 4:** Vào [trang Google Drive này](https://drive.google.com/drive/folders/1jF8dr618N80z5FbvR1IqrAyxI52rl60N) và tải bản Tahoe về máy. Sau đó, copy thư mục `com.apple.recovery.boot` vào thư mục ngoài cùng của USB, ngang hàng với thư mục `EFI`.

**Bước 5:** Mở trình duyệt lên, truy cập vào [OCAuxiliaryTools Releases](https://github.com/ic005k/OCAuxiliaryTools/releases) và tải bản có tên là `OCAT-Win64.zip` về máy. Giải nén ra, và tìm file `OCAT.exe` để mở phần mềm lên.

**Bước 6:** Sau khi mở phần mềm lên, bấm chọn `File` -> `Open` -> Trỏ đến USB -> `EFI` -> `OC` -> `config.plist` và mở lên.

**Bước 7:** Bấm vào mục `PI`. Ở bên cạnh dòng `SystemProductName`, bấm nút **Generate** để tạo thông tin ID thiết bị. Sau đó nhấn `Ctrl + S` để lưu lại cấu hình.

**Bước 8:** Khởi động lại máy, nhấn `F2` liên tục để vào BIOS và làm các thiết lập sau:

- **Advanced Optimus / Hybrid Card:** OFF
- **Secure Boot:** OFF

**Bước 9:** Lưu lại và thoát ra. Khi máy khởi động lại, nhấn liên tục `F12` để vào menu Boot Options. Dùng con trỏ chuột (hoặc bàn phím) chọn vào biểu tượng USB của bạn.

**Bước 10:** Ở menu OpenCore, trỏ xuống, chọn vào mục có chữ `Recovery`, và nhấn Enter để vào bộ cài macOS.

**Bước 11:** Sau khi vào được giao diện cài đặt, bạn sẽ thấy 1 giao diện toàn tiếng Nga (Well... chả biết tại sao 🤷‍♂️! Đổ lỗi cho Apple đi =))!). Chọn vào mục thứ 2 tính từ logo Apple trên góc màn hình đếm sang tay phải, sau đó chỉnh ngôn ngữ về tiếng mà các bạn thích.

**Bước 12:** Sau khi chỉnh ngôn ngữ xong, chọn `Disk Utilities` -> chọn `View` -> Chọn `Show all devices`. Nhìn vào thiết bị ổ cứng chứa Windows, chọn phân vùng 50GB mà các bạn đã chuẩn bị trước đó. Nhấn `Erase` -> Đặt tên và format dưới định dạng **APFS** -> Nhấn `Erase` để nó format phân vùng đó về chuẩn của macOS.

**Bước 13:** Thoát Disk Utility, chọn `Cài đặt macOS Tahoe 26`. **Lưu ý:** Cắm cáp mạng Ethernet vào để Recovery tải bộ cài xuống, hoặc nếu may mắn thì kext Wifi hoạt động và bạn có thể kết nối Wifi! (Well... idk 🤔. Test by yourself! 🤷‍♂️). Cứ Next và Next. Đến đoạn chọn ổ cứng thì chọn cái ổ APFS vừa format xong và nhấn Next lần nữa.

**Bước 14:** Đi pha ấm trà đi 🗿! 1 tiếng nữa rồi quay lại =)))!

**Bước 15:** Sau khi tải và cài xong, máy sẽ tự khởi động lại. Lúc này, tuỳ chọn `Installer (ext)` sẽ xuất hiện. Nhấn vào nó và đợi. Máy sẽ khởi động lại tầm 2-3 lần gì đấy, cứ chọn `Installer` mỗi khi khởi động lại, cho đến khi nhìn thấy chữ `macOS Tahoe 26` ở lần khởi động tiếp thì mới chọn vào nó =))). *(Lưu ý nhỏ: Nếu bị đứng quá lâu ở 1 giai đoạn nào đó—cỡ tầm 2 tiếng... maybe 🤷‍♂️—thì hãy giữ nút nguồn 10 giây để tắt máy, xong khởi động lại là sẽ ổn thôi!)*.

**Bước 16:** Sau khi vào được macOS và setup xong mọi thứ (yên tâm là lúc này chưa có tăng tốc đồ hoạ nên sẽ lag lòi 🐔!), mở Safari truy cập vào [Github của nullMoth](https://github.com/nullmoth/nvidia-macos-driver) và tải bản `.dmg` mới nhất về. Mở lên, nhấn xong để bỏ qua cảnh báo. Mở `Settings` -> `Quyền truy cập & Bảo mật` -> Lướt xuống dưới thấy cảnh báo chặn mở app `1401` -> Nhấn nút `Vẫn mở` -> Nhập mật khẩu.

**Bước 17:** Trong app, có 4 bước tương ứng với 4 nút. Nhấn lần lượt: `Download` -> `Show me the changes` -> `Install driver`. Mỗi bước sẽ hơi lâu nên các bạn kiên nhẫn chờ nhé!

**Bước 18:** Khi nút `Restart Now` sáng lên, quay lại `Settings` -> `Quyền truy cập & bảo mật` -> Lướt xuống chỗ app 1401 -> Nhấn nút `Xem` (cùng vị trí nút Vẫn mở) để xem các cài đặt mới thêm -> Nhấn `Xong`.

**Bước 19:** Mở Safari, truy cập lại [OCAuxiliaryTools Releases](https://github.com/ic005k/OCAuxiliaryTools/releases) tải bản `OCAT_Mac.dmg` về. Làm tương tự bước 16 để cấp quyền và mở ứng dụng OCAT lên.

**Bước 20:** Bấm vào `File` -> `Open`, trỏ đến USB của các bạn -> `EFI` -> `OC` -> `config.plist` và nhấn mở.

**Bước 21:** Tìm đến mục `NVRAM` -> tab `Add` -> chọn dòng `7C436110-AB2A-4BBB-A880-FE41995C9F82` -> Bấm đúp vào ô string ở dòng `boot-args` và xoá biến `-nvoff` ở cuối đi -> Bấm `Cmd + S` để lưu lại.

**Bước 22:** Quay lại app `1401` và bấm nút `Restart Now`.

**Bước 23:** Khởi động lại, chọn `macOS Tahoe 26` và tận hưởng!

### 🚀 Các bước tiếp theo để khởi động không cần USB

**Bước 1:** Khi đang ở macOS, tải phần mềm `Hackintool` về. Cấp quyền mở tương tự app 1401.

**Bước 2:** Mở app lên, chọn phần `Disk` -> nhìn phần `EFI Partitions` xem ổ cứng chứa Windows là ổ nào -> nhấn biểu tượng `Mount`, nhập mật khẩu. Lúc này, phân vùng được mount dưới tên `NO NAME`.

**Bước 3:** Mở USB của bạn lên, copy toàn bộ thư mục `OC`. Mở thiết bị `NO NAME` -> `EFI` -> dán thư mục `OC` vào đây.

**Bước 4:** Vào USB của bạn -> mở thư mục `EFI` -> `BOOT` -> copy file `BOOTx64.efi`. Mở thiết bị `NO NAME` -> `EFI` -> `Boot` -> đổi tên file cũ thành `Bootx64.efi.bak` và dán file `BOOTx64.efi` của bạn vào.

**Bước 5:** Khởi động lại, nhấn `F2` vào BIOS -> Mở mục `Boot Configuration` -> Nhấn `Add Boot Option` -> Ở phần `Browser File`, mở từng mục cho đến khi thấy cấu trúc thư mục EFI của ổ `NO NAME` -> Mở thư mục `Boot` -> Chọn file `BOOTx64.efi` -> Đặt tên là `OpenCore` -> Nhấn lưu thiết lập -> Nhấn `Apply Changes` -> Đẩy tuỳ chọn `OpenCore` lên vị trí đầu tiên -> Nhấn `Apply Changes` lần nữa.

**Bước 6:** Thoát ra, khởi động lại và tận hưởng! 🗿
