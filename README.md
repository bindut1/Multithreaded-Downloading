# Multithreaded Download Manager

Ứng dụng quản lý tải xuống đa luồng được phát triển bằng Java và JavaFX, hỗ trợ tải xuống file từ link trực tiếp và torrent với khả năng tải đa luồng để tăng tốc độ tải xuống.

## 📋 Mục lục

- [Demo](#demo)
- [Tính năng](#tính-năng)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
- [Cài đặt](#cài-đặt)
- [Hướng dẫn sử dụng](#hướng-dẫn-sử-dụng)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Đóng góp](#đóng-góp)

## 🎥 Demo

Xem video demo ứng dụng tại đây: [Demo Video](https://drive.google.com/file/d/1XzKyuHAFFOUQ4Q5VBoF-fpJ0yFcjFoqY/view?usp=drive_link)

## ✨ Tính năng

- **Tải xuống đa luồng**: Tăng tốc độ tải xuống bằng cách chia file thành nhiều phần và tải đồng thời
- **Hỗ trợ nhiều loại tải xuống**:
  - Tải xuống từ link trực tiếp (HTTP/HTTPS)
  - Tải xuống file torrent
- **Giao diện người dùng thân thiện**: Sử dụng JavaFX với JFoenix để tạo giao diện Material Design
- **Quản lý tải xuống**:
  - Tạm dừng và tiếp tục tải xuống
  - Xóa tải xuống
  - Theo dõi tiến trình tải xuống
  - Hiển thị tốc độ tải xuống
  - Xem lịch sử tải xuống đã hoàn thành
- **Lập lịch tải xuống**: Hẹn giờ bắt đầu tải xuống tự động
- **Tích hợp Selenium**: Hỗ trợ tải xuống từ các trang web phức tạp
- **Tracking file**: Lưu trữ thông tin file đang tải và đã hoàn thành

## 🛠️ Công nghệ sử dụng

- **Java**: Ngôn ngữ lập trình chính
- **JavaFX**: Framework xây dựng giao diện người dùng
- **JFoenix**: Thư viện Material Design cho JavaFX
- **Maven**: Quản lý dependencies và build project
- **Selenium WebDriver**: Tự động hóa trình duyệt để tải xuống
- **Apache Commons Net**: Xử lý kết nối FTP
- **TTorrent**: Xử lý tải xuống file torrent
- **SLF4J**: Logging framework

## 💻 Yêu cầu hệ thống

- Java JDK 8 trở lên
- Maven 3.6+
- Hệ điều hành: Windows, macOS, Linux

## 📦 Cài đặt

### 1. Clone repository

```bash
git clone https://github.com/bindut1/Multithreaded-Downloading.git
cd Multithreaded-Downloading
```

### 2. Build project với Maven

```bash
mvn clean install
```

### 3. Chạy ứng dụng

```bash
mvn javafx:run
```

Hoặc chạy trực tiếp từ file JAR sau khi build:

```bash
java -jar target/Downloading-0.0.1-SNAPSHOT.jar
```

## 📖 Hướng dẫn sử dụng

### Tạo tải xuống mới

1. Click vào nút **"New Download"** hoặc **"+"**
2. Nhập URL của file cần tải xuống
3. Chọn đường dẫn lưu file
4. Click **"Download"** để bắt đầu

### Quản lý tải xuống

- **Tạm dừng**: Click vào nút pause trên file đang tải
- **Tiếp tục**: Click vào nút resume trên file đã tạm dừng
- **Xóa**: Click vào nút delete để xóa tải xuống
- **Mở thư mục**: Double click vào file đã hoàn thành để mở thư mục chứa file

### Lập lịch tải xuống

1. Click vào nút **"Schedule"**
2. Thiết lập thời gian bắt đầu tải xuống
3. Ứng dụng sẽ tự động bắt đầu tải xuống vào thời điểm đã đặt

### Cài đặt

- Truy cập **Settings** để cấu hình:
  - Số luồng tải xuống
  - Đường dẫn lưu file mặc định
  - Các tùy chọn khác

## 📁 Cấu trúc dự án

```
Multithreaded-Downloading/
├── src/
│   └── main/
│       └── java/
│           ├── download/              # Xử lý logic tải xuống
│           │   ├── AbstractDownloadObject.java
│           │   ├── DownloadDirectLink.java
│           │   ├── DownloadObject.java
│           │   └── DownloadTorrent.java
│           ├── downloadUI/            # UI cho các item tải xuống
│           │   ├── Downloading.java
│           │   └── DownloadWaiting.java
│           ├── util/                  # Các tiện ích hỗ trợ
│           │   ├── FileHandle.java
│           │   ├── HttpConnection.java
│           │   └── TimeHandle.java
│           ├── utilUI/                # Các component UI
│           │   ├── DownloadItem.java
│           │   ├── MainTableItem.java
│           │   ├── style.css
│           │   └── style1.css
│           └── view/                  # Các màn hình chính
│               ├── AlertUI.java
│               ├── DownloadUI.java
│               ├── MainUI.java
│               ├── ProgressUI.java
│               ├── PromptUI.java
│               ├── ScheduleUI.java
│               └── SettingUI.java
├── CompletedFileTracking.txt          # Lưu danh sách file đã tải
├── WaitingFileTracking.txt            # Lưu danh sách file đang chờ
├── pom.xml                            # Maven configuration
└── README.md
```

## 🤝 Đóng góp

Mọi đóng góp đều được chào đón! Vui lòng:

1. Fork repository
2. Tạo branch mới (`git checkout -b feature/AmazingFeature`)
3. Commit thay đổi (`git commit -m 'Add some AmazingFeature'`)
4. Push lên branch (`git push origin feature/AmazingFeature`)
5. Tạo Pull Request

## 📝 License

Dự án này được phát triển cho mục đích học tập và nghiên cứu.

## 📧 Liên hệ

Nếu bạn có bất kỳ câu hỏi hoặc góp ý nào, vui lòng tạo issue trên GitHub repository.

---

⭐ Nếu bạn thấy project này hữu ích, hãy cho một star nhé!
