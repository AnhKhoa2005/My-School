# BÁO CÁO PHÂN TÍCH CODE WEBSITE TRƯỜNG THPT LƯƠNG THẾ VINH

Tài liệu này được tạo ra để cung cấp một cái nhìn tổng quan chi tiết về cấu trúc và mã nguồn của website Trường THPT Lương Thế Vinh. Mục tiêu là giúp bạn hiểu rõ cách trang web được xây dựng, từ đó có thể học hỏi, bảo trì và phát triển trong tương lai.

Tài liệu bao gồm 3 phần chính:

1.  **Phân tích HTML**: Giải thích ý nghĩa và cách sử dụng của tất cả các thẻ (tags) và thuộc tính (attributes) HTML có trong dự án.
2.  **Phân tích CSS**: Giải thích ý nghĩa và cách sử dụng của các thuộc tính (properties) và giá trị (values) CSS quan trọng.
3.  **Ánh xạ HTML & CSS**: Liên kết cấu trúc HTML của từng trang với các quy tắc CSS tương ứng, giúp hiểu rõ phần nào của CSS đang định dạng cho phần nào của HTML.

---

## PHẦN 1: PHÂN TÍCH CÁC THẺ VÀ THUỘC TÍNH HTML

Phần này liệt kê và giải thích tất cả các thẻ HTML và các thuộc tính của chúng được sử dụng trong toàn bộ dự án.

### 1. Cấu trúc cơ bản của một trang (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`)

- `<!DOCTYPE html>`: Khai báo cho trình duyệt biết đây là một tài liệu HTML5. Đây là dòng bắt buộc phải có ở đầu mỗi tệp `.html`.
- `<html lang="vi">`: Thẻ gốc, bao bọc toàn bộ nội dung trang web.
  - `lang="vi"`: Thuộc tính khai báo ngôn ngữ chính của trang là Tiếng Việt, giúp các công cụ tìm kiếm và trình duyệt hiểu rõ hơn về nội dung.
- `<head>`: Chứa các thông tin "meta" (siêu dữ liệu) cho trang web, không hiển thị trực tiếp nhưng rất quan trọng.
  - `<meta charset="UTF-8">`: Khai báo bộ ký tự (character set) là UTF-8 để hiển thị tiếng Việt có dấu đúng cách.
  - `<meta name="viewport" content="width=device-width, initial-scale=1">`: Giúp trang web hiển thị tốt trên các thiết bị di động (responsive) bằng cách đặt chiều rộng của trang bằng chiều rộng thiết bị và tỷ lệ ban đầu là 1.0.
  - `<title>`: Đặt tiêu đề cho trang, hiển thị trên tab của trình duyệt và quan trọng cho SEO (tối ưu hóa công cụ tìm kiếm).
  - `<link>`: Dùng để liên kết đến các tài nguyên bên ngoài.
    - `rel="preconnect"`: Dùng để kết nối sớm đến các tên miền (ví dụ: `fonts.googleapis.com`), giúp tăng tốc độ tải font.
    - `rel="stylesheet"`: Liên kết đến các tệp CSS để định dạng cho trang web.
- `<body>`: Chứa toàn bộ nội dung sẽ được hiển thị trên trang web (văn bản, hình ảnh, video, liên kết...).

### 2. Các thẻ định dạng khối và cấu trúc (`<div>`, `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)

- `<div>`: Thẻ khối chung nhất, được dùng để nhóm các phần tử lại với nhau để định dạng (qua CSS) hoặc xử lý (qua JavaScript).
  - `class="..."`: Thuộc tính phổ biến nhất, dùng để gán một hoặc nhiều "lớp" cho thẻ, giúp CSS và JavaScript có thể chọn và tác động đến nó. Ví dụ: `<div class="container">` nhóm nội dung và căn giữa.
- `<header>`: Đại diện cho phần đầu của một trang hoặc một khu vực. Trong dự án này, nó chứa logo, tên trường và thanh điều hướng chính.
- `<nav>`: Đại diện cho khu vực chứa các liên kết điều hướng (navigation). Trong dự án, nó chứa menu chính của trang web.
- `<main>`: Chứa nội dung chính, độc nhất của trang. Mỗi trang chỉ nên có một thẻ `<main>`.
- `<section>`: Dùng để nhóm các nội dung có liên quan với nhau thành một khu vực riêng biệt (ví dụ: khu vực "Giới thiệu", "Tin tức nổi bật").
- `<footer>`: Đại diện cho phần chân của một trang hoặc một khu vực. Thường chứa thông tin bản quyền, liên hệ, liên kết mạng xã hội.

### 3. Các thẻ văn bản (`<h1>` đến `<h6>`, `<p>`, `<span>`, `<a>`)

- `<h1>`, `<h2>`, `<h3>`, `<h4>`: Các thẻ tiêu đề (heading), dùng để xác định các cấp độ tiêu đề khác nhau. `<h1>` là tiêu đề quan trọng nhất (thường là tên trang hoặc tên trường), và mức độ quan trọng giảm dần đến `<h6>`.
- `<p>`: Thẻ đoạn văn (paragraph), dùng để chứa các đoạn văn bản thông thường.
- `<span>`: Thẻ nội tuyến (inline), dùng để nhóm một phần nhỏ của văn bản hoặc các phần tử nội tuyến khác để định dạng riêng mà không làm thay đổi cấu trúc. Ví dụ: `<span class="breadcrumb__separator">/</span>` chỉ để định dạng dấu gạch chéo.
- `<a>`: Thẻ liên kết (anchor).
  - `href="..."`: Thuộc tính quan trọng nhất, chứa URL hoặc đường dẫn đến trang sẽ được chuyển đến khi người dùng nhấp vào. Ví dụ: `href="index.html"`, `href="tel:0935308369"`.
  - `target="_blank"`: Mở liên kết trong một tab mới của trình duyệt. Thường dùng cho các liên kết ra ngoài trang web.

### 4. Các thẻ danh sách (`<ul>`, `<li>`)

- `<ul>`: Danh sách không có thứ tự (unordered list). Dùng để tạo một danh sách các mục mà thứ tự không quan trọng.
- `<li>`: Mục trong danh sách (list item). Phải được đặt bên trong một thẻ `<ul>` (hoặc `<ol>`). Trong dự án, menu điều hướng được xây dựng bằng `<ul>` và `<li>`.

### 5. Các thẻ đa phương tiện (`<img>`, `<video>`, `<source>`, `<iframe>`)

- `<img>`: Hiển thị hình ảnh.
  - `src="..."`: Chứa đường dẫn đến tệp hình ảnh.
  - `alt="..."`: Cung cấp một đoạn văn bản thay thế, sẽ hiển thị nếu ảnh không tải được. Rất quan trọng cho khả năng truy cập (cho người khiếm thị) và SEO.
  - `class="..."`: Dùng để định dạng kích thước, vị trí của ảnh.
- `<video>`: Nhúng và phát video.
  - `autoplay`, `loop`, `controls`: Các thuộc tính boolean. `autoplay` tự động phát, `loop` lặp lại video, `controls` hiển thị các nút điều khiển (play, pause, âm lượng).
- `<source>`: Được đặt bên trong thẻ `<video>` hoặc `<audio>`, chỉ định nhiều định dạng tệp media khác nhau để trình duyệt có thể chọn định dạng mà nó hỗ trợ.
  - `src="..."`: Đường dẫn đến tệp media.
  - `type="..."`: Loại media (ví dụ: `video/mp4`).
- `<iframe>`: Nhúng một trang web khác vào trang hiện tại. Được sử dụng để nhúng video từ YouTube và các bài đăng từ Facebook.
  - `src="..."`: URL của trang cần nhúng.
  - `width`, `height`: Chiều rộng và chiều cao của khung nhúng.
  - `frameborder="0"`: Xóa đường viền của khung.
  - `allowfullscreen`: Cho phép nội dung trong iframe hiển thị toàn màn hình.

### 6. Các thẻ biểu mẫu (`<form>`, `<input>`, `<label>`, `<select>`, `<option>`, `<textarea>`, `<button>`)

Các thẻ này được sử dụng chủ yếu trong trang `Gopy.html`.

- `<form>`: Bao bọc các phần tử của một biểu mẫu.
- `<label>`: Nhãn cho một phần tử `<input>`. Giúp người dùng biết cần nhập thông tin gì.
  - `for="..."`: Liên kết `label` với một `input` có `id` tương ứng. Khi nhấp vào label, con trỏ sẽ tự động nhảy vào ô input.
- `<input>`: Thẻ nhập liệu đa năng.
  - `type="text"`: Ô nhập văn bản một dòng.
  - `type="email"`: Ô nhập email (có kiểm tra định dạng cơ bản).
  - `type="tel"`: Ô nhập số điện thoại.
  - `type="checkbox"`: Ô đánh dấu (có thể chọn nhiều). Trong dự án này, nó được dùng một cách sáng tạo để tạo menu trên di động (checkbox hack).
  - `type="radio"`: Nút chọn một trong nhiều (chỉ được chọn một).
  - `type="file"`: Cho phép người dùng chọn tệp để tải lên.
  - `id="..."`: Đặt một định danh duy nhất cho thẻ, dùng để `label` và JavaScript có thể tham chiếu đến.
  - `placeholder="..."`: Hiển thị một đoạn văn bản gợi ý bên trong ô nhập liệu.
  - `required`: Thuộc tính boolean, bắt buộc người dùng phải điền vào ô này trước khi gửi form.
- `<select>`: Tạo một danh sách thả xuống.
- `<option>`: Một lựa chọn trong danh sách `<select>`.
  - `value="..."`: Giá trị sẽ được gửi đi khi lựa chọn này được chọn.
- `<textarea>`: Ô nhập văn bản nhiều dòng.
  - `rows="..."`: Số dòng hiển thị ban đầu.
  - `maxlength="..."`: Giới hạn số ký tự tối đa.
- `<button>`: Nút bấm.
  - `type="submit"`: Nút gửi biểu mẫu.
  - `type="reset"`: Nút xóa toàn bộ dữ liệu đã nhập trong biểu mẫu.

### 7. Các thẻ bảng (`<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>`)

Các thẻ này được sử dụng trong trang `Thoikhoabieu.html` và `Lichthikiemtra.html`.

- `<table>`: Thẻ bao bọc toàn bộ bảng.
- `<thead>`: Phần đầu của bảng, thường chứa hàng tiêu đề.
- `<tbody>`: Phần thân của bảng, chứa các hàng dữ liệu.
- `<tr>`: Một hàng (table row) trong bảng.
- `<th>`: Ô tiêu đề (table header) trong một hàng. Văn bản trong `<th>` thường được in đậm và căn giữa.
- `<td>`: Ô dữ liệu (table data) trong một hàng.

### 8. Các thẻ Scripting (`<script>`)

- `<script>`: Dùng để nhúng hoặc tham chiếu đến mã JavaScript.
  - Nếu có thuộc tính `src="..."`, nó sẽ tải và thực thi tệp JavaScript từ đường dẫn đó.
  - Nếu không có `src`, mã JavaScript sẽ được viết trực tiếp bên trong thẻ.
  - `async`, `defer`: Các thuộc tính dùng để kiểm soát cách trình duyệt tải và thực thi script, giúp tối ưu tốc độ tải trang. Được dùng cho script của Facebook và Tawk.to.

---

## PHẦN 2: GIẢI THÍCH CHI TIẾT CÁC THUỘC TÍNH CSS

Phần này cung cấp một tài liệu tra cứu toàn diện về các thuộc tính, giá trị và quy tắc CSS được sử dụng trong dự án và các thuộc tính phổ biến khác.

### 1. Quy tắc @ (At-Rules)

Đây là những quy tắc đặc biệt, cung cấp cho CSS những chỉ dẫn về cách hoạt động trong những điều kiện nhất định.

- **`@keyframes`**: Dùng để định nghĩa một hoạt ảnh (animation). Bạn xác định các giai đoạn của hoạt ảnh (ví dụ từ `from` đến `to`, hoặc theo phần trăm `0%`, `50%`, `100%`) và các thuộc tính CSS sẽ thay đổi ở mỗi giai đoạn.

  - **Ví dụ trong dự án**:
    ```css
    @keyframes float {
      0%,
      100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-15px);
      }
    }
    ```
    Hoạt ảnh này tạo ra hiệu ứng "nổi" lên xuống cho một phần tử.

- **`@media`**: Dùng để áp dụng các khối CSS khác nhau cho các kích thước màn hình hoặc loại thiết bị khác nhau. Đây là nền tảng của **Responsive Web Design**.
  - **Cú pháp**: `@media (điều kiện) { ... }`
  - **Các điều kiện phổ biến**:
    - `max-width: 768px`: Áp dụng khi chiều rộng màn hình nhỏ hơn hoặc bằng 768px (cho tablet và mobile).
    - `min-width: 769px`: Áp dụng khi chiều rộng màn hình lớn hơn hoặc bằng 769px (cho desktop).
    - `orientation: portrait`: Áp dụng khi thiết bị ở chiều dọc.
  - **Ví dụ trong dự án**:
    ```css
    @media (max-width: 768px) {
      .nav__list {
        display: none; /* Ẩn menu chính trên mobile */
      }
    }
    ```

### 2. Định vị (Positioning)

- **Thuộc tính `position`**: Xác định phương thức định vị của một phần tử.

  - **Giá trị**:
    - `static`: Mặc định. Phần tử được định vị theo luồng thông thường của trang. Các thuộc tính `top`, `right`, `bottom`, `left`, `z-index` không có tác dụng.
    - `relative`: Phần tử được định vị theo luồng thông thường, nhưng sau đó có thể được điều chỉnh vị trí tương đối so với vị trí ban đầu của nó bằng các thuộc tính `top`, `right`, `bottom`, `left`. Nó cũng tạo ra một "ngữ cảnh xếp chồng" (stacking context) mới và làm gốc cho các phần tử con có `position: absolute`.
    - `absolute`: Phần tử bị xóa khỏi luồng thông thường của trang và được định vị dựa trên phần tử cha có `position` khác `static` gần nhất. Nếu không có, nó sẽ được định vị dựa trên thẻ `<body>`.
    - `fixed`: Phần tử bị xóa khỏi luồng thông thường và được định vị dựa trên khung nhìn (viewport) của trình duyệt. Nó sẽ giữ nguyên vị trí ngay cả khi người dùng cuộn trang. Ví dụ: một header cố định trên cùng.
    - `sticky`: Là sự kết hợp giữa `relative` và `fixed`. Phần tử hoạt động như `relative` cho đến khi người dùng cuộn trang đến một ngưỡng nhất định (được xác định bởi `top`, `bottom`...), lúc đó nó sẽ hoạt động như `fixed`.

- **Thuộc tính `top`, `right`, `bottom`, `left`**: Dùng để chỉ định khoảng cách cho phần tử được định vị (khi `position` không phải là `static`).

- **Thuộc tính `z-index`**: Xác định thứ tự xếp chồng của các phần tử được định vị. Phần tử có `z-index` cao hơn sẽ nằm trên phần tử có `z-index` thấp hơn. Chỉ hoạt động với các phần tử có `position` khác `static`.

- **Thuộc tính `inset`**: Là thuộc tính viết tắt cho `top`, `right`, `bottom`, `left`.
  - **Ví dụ**: `inset: 0;` tương đương với `top: 0; right: 0; bottom: 0; left: 0;`.

### 3. Mô hình Hộp (Box Model)

Mọi phần tử HTML đều có thể được coi là một chiếc hộp. Mô hình hộp mô tả cách các thuộc tính kích thước và khoảng cách hoạt động.

- **Thuộc tính `width`, `height`**: Xác định chiều rộng và chiều cao của vùng nội dung (content area) của phần tử.

- **Thuộc tính `padding`**: Xác định khoảng trống giữa vùng nội dung và đường viền (border) của phần tử.

- **Thuộc tính `border`**: Xác định đường viền xung quanh padding và nội dung. Có thể thiết lập `border-width`, `border-style` (`solid`, `dashed`...), và `border-color`.

- **Thuộc tính `margin`**: Xác định khoảng trống bên ngoài đường viền, tạo khoảng cách giữa phần tử này và các phần tử khác.

- **Thuộc tính `box-sizing`**: Thay đổi cách tính toán kích thước tổng thể của hộp.
  - **Giá trị**:
    - `content-box` (mặc định): `width` và `height` chỉ áp dụng cho vùng nội dung. Kích thước thực tế của hộp sẽ là `width` + `padding` + `border`.
    - `border-box`: `width` và `height` áp dụng cho toàn bộ hộp, bao gồm cả `padding` và `border`. Kích thước thực tế của hộp sẽ chính là giá trị `width` bạn đặt. **Đây là giá trị được khuyến khích sử dụng trong hầu hết các dự án hiện đại** vì nó giúp việc tính toán layout dễ dàng hơn nhiều.

### 4. Layout (Bố cục)

- **Thuộc tính `display`**: Xác định cách một phần tử được hiển thị và cách nó tương tác với các phần tử khác.

  - **Giá trị**:
    - `block`: Phần tử bắt đầu trên một dòng mới và chiếm toàn bộ chiều rộng có sẵn. Ví dụ: `<div>`, `<p>`, `<h1>`.
    - `inline`: Phần tử không bắt đầu trên dòng mới và chỉ chiếm chiều rộng cần thiết. Các thuộc tính `width`, `height`, `margin-top`, `margin-bottom` không có tác dụng. Ví dụ: `<span>`, `<a>`, `<img>`.
    - `inline-block`: Giống `inline` nhưng cho phép thiết lập `width`, `height` và `margin` dọc.
    - `none`: Ẩn hoàn toàn phần tử.
    - `flex`: Biến phần tử thành một "flex container", cho phép sắp xếp các phần tử con (flex items) một cách linh hoạt.
    - `grid`: Biến phần tử thành một "grid container", cho phép sắp xếp các phần tử con theo cả hàng và cột.

- **Flexbox (dành cho `display: flex`)**:

  - `flex-direction`: Hướng sắp xếp các item (`row`, `column`).
  - `justify-content`: Căn chỉnh các item theo trục chính (`flex-start`, `center`, `flex-end`, `space-between`, `space-around`).
  - `align-items: center`: Căn chỉnh các item theo trục phụ (`flex-start`, `center`, `flex-end`, `stretch`).
  - `gap`: Khoảng cách giữa các item.

- **Grid (dành cho `display: grid`)**:
  - `grid-template-columns`: Định nghĩa số lượng và kích thước của các cột.
    - **Ví dụ**: `repeat(auto-fit, minmax(300px, 1fr))` tạo ra một lưới responsive, tự động điều chỉnh số cột dựa trên không gian có sẵn.
  - `gap`: Khoảng cách giữa các ô trong lưới.

### 5. Kiểu chữ (Typography)

- **`font-family`**: Chỉ định phông chữ. Nên cung cấp một danh sách các phông chữ (font stack), kết thúc bằng một loại chung (`sans-serif`, `serif`).
- **`font-size`**: Kích thước của chữ. Đơn vị phổ biến: `px`, `rem`, `em`, `vw`.
- **`font-weight`**: Độ đậm của chữ (`normal`, `bold`, hoặc các giá trị số `400`, `700`).
- **`color`**: Màu sắc của văn bản.
- **`text-align`**: Căn chỉnh văn bản theo chiều ngang (`left`, `center`, `right`, `justify`).
- **`text-decoration`**: Thêm hoặc bớt các đường trang trí (`none`, `underline`, `line-through`).
- **`line-height`**: Chiều cao của một dòng văn bản, dùng để kiểm soát khoảng cách giữa các dòng.
- **`text-shadow`**: Thêm bóng đổ cho văn bản.

### 6. Màu sắc và Nền (Colors & Backgrounds)

- **`background-color`**: Đặt màu nền cho một phần tử.
- **`background-image`**: Đặt một hoặc nhiều hình ảnh làm nền.
  - **Giá trị**: `url('path/to/image.jpg')`, `linear-gradient(...)`.
- **`background-size`**: Kích thước của ảnh nền.
  - **Giá trị**: `cover` (lấp đầy, có thể bị cắt), `contain` (hiển thị toàn bộ, có thể có khoảng trống).
- **`background-position`**: Vị trí của ảnh nền.
- **`opacity`**: Độ trong suốt của một phần tử (từ `0` đến `1`).

### 7. Hiệu ứng và Chuyển động

- **`transition`**: Tạo hiệu ứng chuyển đổi mượt mà khi một thuộc tính CSS thay đổi giá trị (ví dụ khi `:hover`).

  - **Cú pháp rút gọn**: `transition: [thuộc tính] [thời gian] [hàm thời gian] [độ trễ];`
  - **Ví dụ**: `transition: background-color 0.3s ease;`
  - **Ví dụ**: `transition: opacity 1s ease-in-out;`
  - **Ví dụ**: `transition: transform 0.5s ease;`

- **`animation`**: Gán một hoạt ảnh (`@keyframes`) cho một phần tử.

  - **Cú pháp rút gọn**: `animation: [tên] [thời gian] [hàm thời gian] [độ trễ] [số lần lặp] [hướng];`
  - **Ví dụ**: `animation: float 5s ease-in-out infinite;`

- **`transform`**: Thay đổi hình dạng, kích thước và vị trí của một phần tử mà không ảnh hưởng đến các phần tử khác.
  - **Giá trị (hàm)**:
    - `translate(x, y)`: Di chuyển phần tử.
    - `rotate(angle)`: Xoay phần tử.
    - `scale(x, y)`: Phóng to/thu nhỏ phần tử.
    - `skew(x-angle, y-angle)`: Làm nghiêng phần tử.

### 8. Các thuộc tính khác

- **`overflow`**: Xử lý nội dung bị tràn ra ngoài kích thước của phần tử.
  - **Giá trị**: `visible` (mặc định), `hidden` (ẩn phần tràn), `scroll` (luôn hiển thị thanh cuộn), `auto` (chỉ hiển thị thanh cuộn khi cần).
- **`cursor`**: Thay đổi hình dạng con trỏ chuột khi di qua phần tử (`pointer`, `text`, `not-allowed`...).
- **`border-radius`**: Bo tròn các góc của phần tử.
- **`box-shadow`**: Thêm bóng đổ cho hộp phần tử.
- **`object-fit`**: Xác định cách một phần tử `<img>` hoặc `<video>` nên được thay đổi kích thước để vừa với vùng chứa của nó.
  - **Giá trị**: `cover` (lấp đầy, giữ tỷ lệ, có thể bị cắt), `contain` (hiển thị toàn bộ, giữ tỷ lệ, có thể có khoảng trống).

---

## PHẦN 3: ÁNH XẠ HTML & CSS

Phần này sẽ kết nối trực tiếp các đoạn mã HTML từ các trang cụ thể với các quy tắc CSS tương ứng đã tạo ra chúng. Điều này giúp bạn hình dung rõ ràng cách các lớp BEM và các thuộc tính CSS được áp dụng để xây dựng các thành phần trực quan trên trang web.

Chúng ta sẽ không phân tích mọi phần tử trên mọi trang, mà sẽ chọn ra các ví dụ tiêu biểu.

### Ví dụ 1: Header và Thanh điều hướng (Tệp `index.html` và `Chung.css`)

Đây là thành phần chung xuất hiện trên tất cả các trang.

**HTML (`index.html`):**

```html
<header class="header">
  <div class="container">
    <div class="header__top">
      <div class="header__logo">
        <a href="index.html">
          <img src="./Images/logo.png" alt="Logo Lương Thế Vinh" />
        </a>
      </div>
      <div class="header__school-name">
        <h1>TRƯỜNG THPT LƯƠNG THẾ VINH</h1>
        <h2>NƠI CHẮP CÁNH NHỮNG ƯỚC MƠ</h2>
      </div>
    </div>
    <nav class="nav">
      <ul class="nav__list">
        <li class="nav__item">
          <a href="index.html" class="nav__link">TRANG CHỦ</a>
        </li>
        <!-- ... các mục menu khác ... -->
      </ul>
    </nav>
  </div>
</header>
```

**CSS (`Chung.css`):**

```css
.header__top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 0;
}

.header__logo img {
  max-width: 100px;
}

.header__school-name h1 {
  font-size: 2.4rem;
  color: var(--primary-color);
}

.nav__list {
  display: flex;
  list-style: none;
  justify-content: center;
  background-color: var(--primary-color);
}

.nav__item {
  margin: 0 1.5rem;
}

.nav__link {
  color: white;
  text-decoration: none;
  padding: 1.5rem 0;
  display: block;
}
```

**Giải thích liên kết:**

- Thẻ `<header class="header">` là khối chính.
- Bên trong, `<div class="header__top">` được áp dụng `display: flex` để xếp `div.header__logo` và `div.header__school-name` nằm trên cùng một hàng. `justify-content: space-between` đẩy logo sang trái và tên trường sang phải.
- Thanh menu `<nav class="nav">` chứa danh sách `<ul class="nav__list">`. Quy tắc `.nav__list` cũng dùng `display: flex` để các thẻ `<li>` (mục menu) xếp thành hàng ngang.
- Mỗi liên kết `<a>` trong menu có lớp `.nav__link` được định dạng màu trắng, bỏ gạch chân và có `padding` để tăng vùng có thể nhấp.

### Ví dụ 2: Lưới tin tức và Thẻ Card (Tệp `Tintuc.html` và `Tintuc.css`)

**HTML (`Tintuc.html`):**

```html
<main class="news-page">
  <div class="container">
    <div class="news-grid">
      <div class="card">
        <a href="Hoatdongtruong.html">
          <img
            src="./Images/pic-1.jpg"
            alt="Hoạt động trường"
            class="card__image"
          />
          <div class="card__content">
            <h3 class="card__title">HOẠT ĐỘNG TRƯỜNG</h3>
            <p class="card__excerpt">
              Tổng hợp các hoạt động nổi bật của trường...
            </p>
          </div>
        </a>
      </div>
      <!-- ... các card khác ... -->
    </div>
  </div>
</main>
```

**CSS (`Tintuc.css` và `Chung.css`):**

```css
/* Trong Tintuc.css */
.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

/* Trong Chung.css (thành phần tái sử dụng) */
.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
}

.card__image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card__content {
  padding: 1.5rem;
}

.card__title {
  font-size: 1.8rem;
  margin-bottom: 1rem;
}
```

**Giải thích liên kết:**

- `<div class="news-grid">` được áp dụng `display: grid` để tạo một layout dạng lưới.
  - `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));` là một kỹ thuật responsive mạnh mẽ: trình duyệt sẽ tự động tạo ra các cột có chiều rộng tối thiểu `300px`. Nếu không đủ chỗ, các card sẽ tự động xuống hàng.
  - `gap: 2rem;` tạo khoảng trống giữa các card.
- Mỗi `<div class="card">` là một thẻ tin tức. Các quy tắc trong `.card` từ `Chung.css` tạo ra hiệu ứng đổ bóng, bo góc.
- Các phần tử bên trong như `.card__image` và `.card__content` được định dạng để đảm bảo hình ảnh và nội dung hiển thị đúng cách. `object-fit: cover` trên ảnh giúp ảnh không bị méo khi lấp đầy khung chứa.

### Ví dụ 3: Biểu mẫu (Tệp `Gopy.html` và `Gopy.css`)

**HTML (`Gopy.html`):**

```html
<form class="feedback-form">
  <div class="form-group">
    <label for="fullname">Họ và tên:</label>
    <input type="text" id="fullname" name="fullname" required />
  </div>
  <div class="form-group">
    <label for="message">Nội dung góp ý:</label>
    <textarea id="message" name="message" rows="5" required></textarea>
  </div>
  <button type="submit" class="btn">Gửi góp ý</button>
</form>
```

**CSS (`Gopy.css` và `Chung.css`):**

```css
/* Trong Gopy.css */
.form-group {
  margin-bottom: 2rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: bold;
}

.form-group input,
.form-group textarea,
.form-group select {
  width: 100%;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

/* Trong Chung.css */
.btn {
  display: inline-block;
  padding: 1rem 2rem;
  border: none;
  border-radius: 5px;
  background-color: var(--primary-color);
  color: white;
  cursor: pointer;
}
```

**Giải thích liên kết:**

- Mỗi cặp `label` và `input` (hoặc `textarea`) được nhóm trong một `<div class="form-group">` để tạo khoảng cách (`margin-bottom`).
- `label` được đặt là `display: block` để nó nằm trên một hàng riêng so với ô nhập liệu.
- Các ô nhập liệu (`input`, `textarea`) được đặt `width: 100%` để chúng chiếm toàn bộ chiều rộng của thẻ chứa, tạo ra một biểu mẫu gọn gàng, thẳng hàng.
- Nút bấm sử dụng lại lớp `.btn` chung từ `Chung.css` để có giao diện nhất quán với các nút khác trên trang web.

---

Tài liệu phân tích đến đây là hoàn tất. Hy vọng qua 3 phần này, bạn đã có một cái nhìn chi tiết và hệ thống về cách trang web được xây dựng. Từ nền tảng này, bạn có thể dễ dàng hơn trong việc học hỏi, chỉnh sửa, bảo trì và phát triển dự án trong tương lai.
