# Jar Builder

Repo dùng để **tạo file .jar từ mã nguồn bất kỳ**. Bạn chỉ cần gửi mã nguồn, GitHub sẽ tự build và trả về file .jar. Mã nguồn không cần nằm trong repo này, nên một repo dùng được cho nhiều dự án.

Dùng được cho mod Minecraft (Fabric, NeoForge, Forge), plugin Paper/Spigot, thư viện Java hoặc bất kỳ dự án Java nào build bằng **Gradle**.

## Yêu cầu với mã nguồn
- Nén cả dự án thành một file `.zip`.
- Trong zip phải có `build.gradle` hoặc `build.gradle.kts`. Có thể nằm trong một thư mục con, repo sẽ tự tìm.
- Nếu dự án có `gradlew`, repo sẽ dùng nó. Nếu không có, repo dùng Gradle do workflow cài sẵn.

## Cách 1: gửi file zip
1. Vào thư mục `inbox/` trong repo này.
2. Chọn **Add file → Upload files**, tải file `.zip` lên rồi **Commit**.
3. Vào tab **Actions** và đợi workflow chạy xong (khoảng 2–5 phút).
4. Tải file jar ở mục **Releases** bên phải trang repo.

## Cách 2: dán link
1. Vào tab **Actions → Build mod jar → Run workflow**.
2. Dán link tải trực tiếp file `.zip` vào ô *zip_url*.
3. Nếu cần, đổi phiên bản Java hoặc Gradle, rồi bấm **Run workflow**.

Cách này không để lại file nào trong repo.

## Lấy file jar
- **Releases:** mỗi lần build là một bản `Build #số`, có sẵn file jar để tải.
- **Artifacts:** nằm cuối trang của lần chạy trong tab Actions, tên `mod-jar`.

Trong kết quả có thể có thêm file `-sources.jar` (chứa mã nguồn). File cần dùng là file jar chính, không có đuôi `-sources`.

## Cài đặt một lần
Vào **Settings → Actions → General → Workflow permissions**, chọn **Read and write permissions** rồi Save. Nếu không, workflow không tạo được Release (vẫn tải được từ Artifacts).

## Phiên bản mặc định
- Java 25
- Gradle 9.7.1

Dự án cũ (ví dụ Minecraft 1.20 hoặc 1.21) thường cần Java 17 hoặc 21. Hãy đổi trong form *Run workflow* ở Cách 2.

## Khi build lỗi
Bấm vào bước màu đỏ trong tab Actions để xem log. Các lỗi hay gặp:
- **Không thấy build.gradle:** zip thiếu file này, hoặc bạn nén sai thư mục.
- **Sai phiên bản Java:** đổi `java_version` cho khớp dự án.
- **Dự án dùng Maven (`pom.xml`):** workflow hiện chỉ hỗ trợ Gradle.
