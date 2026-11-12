# Jar Builder

**Language / Ngôn ngữ:** [English](#english) | [Tiếng Việt](#tiếng-việt)

---

## English

### Introduction
This repo **builds a `.jar` file from any Gradle-based source code**. You send the source code, GitHub builds it automatically and gives you the `.jar`. The source does not need to live in this repo, so one repo works for many projects.

It works for Minecraft mods (Fabric, NeoForge, Forge), Paper/Spigot plugins, Java libraries, or any Java project built with **Gradle** (Maven / `pom.xml` is not supported).

### Usage

**Requirements for the source code**
- Zip the whole project into a single `.zip` file.
- The zip must contain `build.gradle` or `build.gradle.kts`. It may sit inside a subfolder (up to 2 levels deep); the workflow finds it.
- If the project has `gradlew`, it is used. Otherwise the workflow installs Gradle for you.

**Method 1: upload a zip**
1. Open the `inbox/` folder in this repo.
2. Choose **Add file → Upload files**, upload your `.zip`, then **Commit**. The build starts automatically on every commit that touches `inbox/`.
3. Open the **Actions** tab and wait for the **Build mod jar** run to finish (about 2–5 minutes).
4. Download the jar from **Releases** (right side of the repo page).

**Method 2: paste a link**
1. Go to **Actions → Build mod jar → Run workflow**.
2. Paste a direct download link to the `.zip` into **zip_url**.
3. If needed, change the Java or Gradle version, then click **Run workflow**.

This method leaves no files in the repo. Java and Gradle versions can only be changed here; Method 1 always uses the defaults.

**Getting the jar**
- **Releases:** every build creates a release named `Build #number` containing the main jar only.
- **Artifacts:** at the bottom of the run page in the Actions tab, named `mod-jar`. It may also contain a `-sources.jar` (source code); use the main jar, the one without the `-sources` suffix.

**One-time setup:** go to **Settings → Actions → General → Workflow permissions**, select **Read and write permissions** and Save. Without it, no Release is created (you can still download from Artifacts).

**Defaults:** Java 25 and Gradle 9.7.1. Older projects (e.g. Minecraft 1.20 / 1.21) often need Java 17 or 21; set it in the **Run workflow** form (Method 2).

---

## Tiếng Việt

### Giới thiệu
Repo này dùng để **tạo file `.jar` từ mã nguồn Gradle bất kỳ**. Bạn chỉ cần gửi mã nguồn, GitHub sẽ tự build và trả về file `.jar`. Mã nguồn không cần nằm trong repo này, nên một repo dùng được cho nhiều dự án.

Dùng được cho mod Minecraft (Fabric, NeoForge, Forge), plugin Paper/Spigot, thư viện Java hoặc bất kỳ dự án Java nào build bằng **Gradle** (không hỗ trợ Maven / `pom.xml`).

### Cách sử dụng

**Yêu cầu với mã nguồn**
- Nén cả dự án thành một file `.zip`.
- Trong zip phải có `build.gradle` hoặc `build.gradle.kts`. File này có thể nằm trong thư mục con (tối đa 2 cấp), workflow sẽ tự tìm.
- Nếu dự án có `gradlew`, workflow sẽ dùng nó. Nếu không có, workflow tự cài Gradle.

**Cách 1: gửi file zip**
1. Vào thư mục `inbox/` trong repo này.
2. Chọn **Add file → Upload files**, tải file `.zip` lên rồi **Commit**. Mỗi commit có thay đổi trong `inbox/` sẽ tự động chạy build.
3. Vào tab **Actions**, đợi lần chạy **Build mod jar** hoàn tất (khoảng 2–5 phút).
4. Tải file jar ở mục **Releases** (bên phải trang repo).

**Cách 2: dán link**
1. Vào tab **Actions → Build mod jar → Run workflow**.
2. Dán link tải trực tiếp file `.zip` vào ô **zip_url**.
3. Nếu cần, đổi phiên bản Java hoặc Gradle, rồi bấm **Run workflow**.

Cách này không để lại file nào trong repo. Chỉ ở đây mới đổi được phiên bản Java và Gradle; Cách 1 luôn dùng giá trị mặc định.

**Lấy file jar**
- **Releases:** mỗi lần build tạo một bản `Build #số`, chỉ chứa file jar chính.
- **Artifacts:** nằm cuối trang của lần chạy trong tab Actions, tên `mod-jar`. Trong đó có thể có thêm file `-sources.jar` (mã nguồn); file cần dùng là file jar chính, không có đuôi `-sources`.

**Cài đặt một lần:** vào **Settings → Actions → General → Workflow permissions**, chọn **Read and write permissions** rồi Save. Nếu không, workflow không tạo được Release (vẫn tải được từ Artifacts).

**Mặc định:** Java 25 và Gradle 9.7.1. Dự án cũ (ví dụ Minecraft 1.20 hoặc 1.21) thường cần Java 17 hoặc 21, hãy đổi trong form **Run workflow** (Cách 2).
