# **Lab 1: Phân tích kiến trúc và ca sử dụng hệ thống Payroll System**  

## **1. Kiến trúc đề xuất**  
### **1.1. Kiến trúc lựa chọn**  
- **Three-Tier Architecture**

### **1.2. Lý do lựa chọn kiến trúc Three-Tier Architecture**  
- **Phân tách rõ ràng các tầng**:  
  *Presentation, Business Logic, và Data hoạt động độc lập giúp dễ dàng bảo trì, mở rộng, hoặc thay thế từng thành phần.*  
- **Tăng khả năng mở rộng (Scalability)**:  
  *Các tầng có thể triển khai trên các máy chủ khác nhau để tối ưu hiệu suất.*  
- **Tăng bảo mật**:  
  *Tầng dữ liệu không tương tác trực tiếp với người dùng, giảm thiểu rủi ro từ các cuộc tấn công.*  
- **Dễ bảo trì**:  
  *Thay đổi logic nghiệp vụ hoặc giao diện sẽ không ảnh hưởng tới các thành phần khác.*  

---

### **1.3. Ý nghĩa của từng thành phần trong kiến trúc**  

#### **a. Presentation Layer (Tầng Giao Diện)**  
- *Cung cấp giao diện người dùng để tương tác với hệ thống (giao diện web, ứng dụng desktop hoặc mobile).*  
- *Kiểm tra tính hợp lệ của dữ liệu đầu vào trước khi gửi đến tầng nghiệp vụ (ví dụ: kiểm tra ngày tháng hợp lệ, định dạng số tài khoản).*  
- *Gửi yêu cầu đến tầng nghiệp vụ để thực hiện các hành động như tính lương hoặc lưu thông tin chấm công.*  
- *Nhận phản hồi từ tầng nghiệp vụ và hiển thị kết quả cho người dùng (ví dụ: xác nhận thanh toán thành công hoặc thông báo lỗi).*  

**Ý nghĩa trong hệ thống Payroll System:**  
- *Đảm bảo dữ liệu nhập vào từ người dùng được kiểm soát tốt, giảm lỗi trước khi gửi xuống tầng dưới.*  
- *Cải thiện trải nghiệm người dùng qua các giao diện trực quan, dễ sử dụng.*  

---

#### **b. Business Logic Layer (Tầng Xử Lý Nghiệp Vụ)**  
- *Thực hiện các quy tắc tính toán và logic nghiệp vụ liên quan đến quản lý nhân viên, tính lương và phương thức thanh toán (như áp dụng thuế và thưởng).*  
- *Quản lý logic nghiệp vụ liên quan đến các hoạt động như chấm công, thanh toán, bảo mật thông tin nhân viên và quản lý quyền truy cập.*  
- *Kiểm tra các điều kiện nghiệp vụ trước khi tương tác với cơ sở dữ liệu (ví dụ: xác nhận nhân viên có đủ giờ làm việc hợp lệ để được thanh toán).*  

**Ý nghĩa trong hệ thống Payroll System:**  
- *Đảm bảo quy tắc nghiệp vụ được thực hiện nhất quán và chính xác.*  
- *Giúp bảo mật thông tin nhạy cảm bằng cách kiểm soát chặt chẽ quy trình xử lý và quyền truy cập dữ liệu.*  

---

#### **c. Data Layer (Tầng Dữ Liệu)**  
- *Tương tác với cơ sở dữ liệu để lưu trữ thông tin như nhân viên, thời gian làm việc và thông tin thanh toán.*  
- *Đảm bảo tính toàn vẹn và bảo mật dữ liệu, ngăn chặn việc truy cập trái phép hoặc thao tác sai trên dữ liệu quan trọng.*  
- *Trả về kết quả truy vấn cho tầng nghiệp vụ để xử lý và hiển thị dữ liệu đúng theo yêu cầu (ví dụ: tìm kiếm lịch sử thanh toán hoặc truy vấn thông tin chấm công).*  

**Ý nghĩa trong hệ thống Payroll System:**  
- *Giữ cho dữ liệu được tổ chức tốt và dễ dàng truy xuất khi cần thiết.*  
- *Bảo vệ dữ liệu nhạy cảm và giảm thiểu rủi ro thất thoát thông tin.*  

---
![Package Diagram](https://www.planttext.com/api/plantuml/png/V9CnImCn5CVtV8h7kUXGg8gBY9Jsg895X1PnS0btuHfwJOuaXnpYvE1S7CLH74HqzO88LlmU-GH-1PDKsvEsPijxx____rwE-z9l3QcmKFamHN90MOO57aA6em5EI5SLAG518bNfoJwE-Hbb2IYHaqeZuiECCy8Kd2E0fhL81CzPtE8f5x3IRhUtmj1rk8Y9c5G5YMsbpPdwcQhxOslTlp4No9vP5kCnaII3hJfIL5d89ZNwCeUFaT7NS41D-SQiS5n6K8Dzewz0zOqUMRVW21U2fobq2wd8C83LJKYDlidM47AROfPOkw1dodixlKSnXz1wNx40i8JUkbzkjchm_f3YWeXtNPs5m-JpsUXR2k7uXIMdRFL8M5wciAASGSSfrhnXjUxBRjDvZXEZ7w4pVhN6VPUGmR7HTnEaZUL8YsKMfvbBoeYKqE49ZQf0lntV-8SeDFe9Eiuqds1iBiVeYRo0bYaViwhCOeHOuMgukqypvvu6TcgrtGM0i3rvU-K-UuOM37ZXrDpEUwB84yMEAFL423K8Yzsly0q00F__0m00)

---

## **2. Cơ chế phân tích**  
- **Kiểm tra tính hợp lệ của dữ liệu**: Đảm bảo dữ liệu chấm công và thanh toán chính xác.  
- **Bảo mật thông tin**: Quản lý quyền truy cập của từng đối tượng trong hệ thống.  
- **Xử lý logic phức tạp**: Đảm bảo các nghiệp vụ như tính lương và tính thuế được thực hiện chính xác.  
- **Đảm bảo tính toàn vẹn dữ liệu**: Dữ liệu phải nhất quán và chính xác trong suốt quá trình hoạt động.  

---

## **3. Phân tích ca sử dụng: Select Payment**  

### Ca Sử Dụng: Payment
- **Tên ca sử dụng:** Payment
- **Tác Nhân chính:** Khách hàng
- **Mô tả:** Khách hàng thực hiện thanh toán cho đơn hàng thông qua hệ thống. Hệ thống xử lý thông tin thanh toán và gửi thông báo đến khách hàng về kết quả thanh toán.

### Các Lớp Phân Tích

1. **Boundary Class: PaymentView**
   - **Mô tả:** Lớp này quản lý giao diện người dùng cho việc thanh toán.
   - **Nhiệm vụ:**
     - Nhận dữ liệu thanh toán từ khách hàng (số thẻ, ngày hết hạn, mã CVV, v.v.).
     - Hiển thị kết quả thanh toán cho khách hàng.

2. **Control Class: PaymentService**
   - **Mô tả:** Lớp này xử lý toàn bộ quy trình thanh toán.
   - **Nhiệm vụ:**
     - Nhận dữ liệu thanh toán từ `PaymentView`.
     - Gọi lớp `Order` để xác minh thông tin đơn hàng.
     - Tạo đối tượng `Payment` để ghi lại thông tin thanh toán.
     - Thực hiện xác thực thanh toán và gửi kết quả trở lại `PaymentView`.

3. **Entity Class: Payment**
   - **Mô tả:** Lớp này đại diện cho thông tin thanh toán.
   - **Nhiệm vụ:**
     - Lưu trữ các thuộc tính liên quan đến thanh toán như số tiền, phương thức thanh toán, và trạng thái thanh toán.
     - Cung cấp phương thức để thực hiện thanh toán.

4. **Entity Class: Order**
   - **Mô tả:** Lớp này đại diện cho đơn hàng của khách hàng.
   - **Nhiệm vụ:**
     - Lưu trữ các thông tin chi tiết của đơn hàng, bao gồm `orderId`, `customerId`, và `totalAmount`.
     - Cung cấp phương thức để truy xuất thông tin chi tiết của đơn hàng.

### Biểu Đồ Sequence

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/Z5AzJiCm4DxlAKwTOEWBT42LYWH822e14gkRM8tLvDmw5wIEY96fRq1KCLPYO8g73a5z3py1hu3J4fAX1RpTdR-_ip_jkf-oC9mbCK0wKOH6fnA05SSIEqC_Ke6Q2k8KktWZPvcaGEAf4cCZaWw025WR76GfwqGQ6EcCGc7cE1JpH1BVNI04cjZek6uDTcKi3O8l5VzSXb2m68bKuhK9gp50JOpTauQoXrUHArPJvAXyfp6ojysHe0XPbpaT7KEZtk0QtHwUERjIVy9RJZtDrbCFBrtnEcz3FnQRd30gNsZieJldtVsojyOLItnmzl4mmLxjxwPdS4MkFSBPXVU_UNDsMR7iStyW-dsP1qZL_lwLkhNqS-NiKmLozXadhbWpph8gq2-xhz_FEzy57fNU_s6mFtr9eV-ENm000F__0m00)


### Nhiệm Vụ của Từng Lớp Phân Tích

- **PaymentView:**
  - Nhận dữ liệu thanh toán từ khách hàng.
  - Hiển thị thông báo về kết quả thanh toán.

- **PaymentService:**
  - Nhận dữ liệu thanh toán từ `PaymentView`.
  - Tương tác với lớp `Order` để xác minh đơn hàng.
  - Tạo và lưu trữ thông tin thanh toán qua đối tượng `Payment`.
  - Xác thực thanh toán và trả kết quả về cho `PaymentView`.

- **Payment:**
  - Chứa các thuộc tính như `amount`, `paymentMethod`, `paymentStatus`.
  - Cung cấp phương thức để thực hiện thanh toán.

- **Order:**
  - Chứa các thuộc tính như `orderId`, `customerId`, `totalAmount`.
  - Cung cấp thông tin cần thiết cho quá trình thanh toán.

### Biểu Đồ Lớp

![Class Diagram](https://www.planttext.com/api/plantuml/png/R56xJWD13EptAwnKeRWVk085GPC24IKIlRLdE8jzd6nleYZYooZu97w1t0DqEjXgF3EsnzglZy-D6egL69o-SGB9IiuPMo3OKq3ZdBJbJg62-u2gyC3uAXYTyqEvmtEaPCzC9xWuk3uXJtoaRUgAhMy6gc7j0fxtf2NqtFkY-q1oP4_JW4wo9zL9czkVf24PN1Na7c-R0VkYbkDlQTamtCLSalrPDNNZgFQm6uL7iZOtS-PWQ4M7I3wd5vOuPfcVN5MtooDgA4hg5cnl7EFNiE9a9EXDuSJMhlxp_iIjmGkXNGUw3QMc_wXl0000__y30000)


### Giải Thích Biểu Đồ Lớp

- **PaymentView:** 
  - Chịu trách nhiệm giao tiếp với người dùng, thu thập thông tin thanh toán và hiển thị kết quả.

- **PaymentService:** 
  - Chịu trách nhiệm xử lý toàn bộ quy trình thanh toán. Nó tương tác với lớp `Order` để kiểm tra thông tin cần thiết và với `Payment` để lưu trữ thông tin thanh toán.

- **Payment:** 
  - Lưu trữ thông tin liên quan đến thanh toán, bao gồm số tiền, phương thức thanh toán và trạng thái thanh toán. Cung cấp phương thức để xác thực thanh toán.

- **Order:** 
  - Chứa thông tin về đơn hàng mà khách hàng đang thanh toán. Cung cấp thông tin cần thiết để thực hiện thanh toán.

---

## **4. Phân tích ca sử dụng: Maintain Timecard**  

   **Mô tả ca sử dụng "Maintain Timecard"**:
   - Tên ca sử dụng: Maintain Timecard
   - Tác Nhân: Nhân viên (Employee)
   - Mô tả: Nhân viên có thể thực hiện các thao tác xem, thêm, sửa đổi, và xóa thông tin thời gian làm việc. Hệ thống sẽ lưu trữ và quản lý thông tin thời gian làm việc một cách chính xác.

 **Các lớp phân tích**:

   - **Boundary Class: TimecardUI**
     - Mô tả: Quản lý giao diện người dùng cho việc quản lý thời gian làm việc.
     - Nhiệm vụ: Hiển thị thông tin thời gian làm việc cho nhân viên, cho phép thêm, sửa, hoặc xóa thông tin.

   - **Control Class: TimecardController**
     - Mô tả: Điều phối logic quản lý thời gian làm việc.
     - Nhiệm vụ: Nhận yêu cầu từ TimecardUI, xử lý các thao tác thêm, sửa, hoặc xóa, và tương tác với lớp Timecard.

   - **Entity Class: Timecard**
     - Mô tả: Đại diện cho thông tin thời gian làm việc của nhân viên.
     - Nhiệm vụ: Lưu trữ chi tiết thời gian vào/ra, ngày tháng, và trạng thái của từng lần chấm công.

   - **Entity Class: Employee**
     - Mô tả: Đại diện cho thông tin chi tiết của nhân viên.
     - Nhiệm vụ: Lưu trữ thông tin như ID, tên, và các thông tin liên quan khác để hỗ trợ quản lý thời gian làm việc.

 **Biểu đồ Sequence**:

![Diagram](https://www.planttext.com/api/plantuml/png/Z9CzJiD048NxESM89b14wLEWI041DKOAvMQpibViJrYl8wL451GS0I4bea2Ab8xABYXyaZq1Ls0YAyG9cCHouzMyxxrvjh-AprxgcVEPLW3fdJJeR2e0lFHAu57VQYsCJx6Dr-8-4uOBF9CiTamV0RIYHAP8DyDKcfW4IXg1l181T5gmcT2Pyh8DMnEj3j35kBSEp_LOsQaGCBIP6J4tnKXgmPaRtLm1jyOxgtwE-jMp4Ww88_rc660DmlPf3T75WT3ear2yIembCwZAcSQ93CKJFpw1sYZMbHkdBjwMYmnvoDyp0fKV9aPFXTMOTKuJ978XVyD9A1wQ8RzrkyjSKkx7IlQydqCxaNvTpA5gR6eoIih5Vrrks_vLmaKebhB16NKeNkJU5YX6oEVsK4XJaa4vvsYIa2zNUjgh_WwR-uygrs5P9PYP1FdgPETBscgzJoRZoilNOfC4UiACw1Vy1W00__y30000)

  
 **Giải thích nhiệm vụ của từng lớp**:

   - **TimecardUI**: Đảm nhiệm việc hiển thị thông tin và cung cấp giao diện để nhân viên thực hiện các thao tác quản lý thời gian.
   - **TimecardController**: Xử lý yêu cầu từ giao diện, điều phối các thao tác với thông tin thời gian.
   - **Timecard**: Lưu trữ chi tiết về thời gian làm việc của nhân viên.
   - **Employee**: Cung cấp thông tin về nhân viên.

   **Biểu đồ lớp**:

![Diagram](https://www.planttext.com/api/plantuml/png/j99DJWCn38NtFaMMiCW5Pe4gTLZC2WdH0qIDDLZaPnHxG0ZrP5rm9Av0CZIqHDCbMIJoI-BlnSxNyNF3OfBCtW7m2mML8YE0a3XKZ-YCK0pyJ1ChhRRECAkUp9YC1u3z4Z-Hnxr9TZUe3r1vl1A-LV7cTf6CjOqoJzO8Dg95Xt_4GmlPnY0fEeVf11jH_ekr43JwoSLtnA7lA4XHIhAkJ2MGV7W8dIfhZHzcEGkvlZ9pnv8eZ0jvpU8Lax_luzRa_SbMDjbQrC5uh40zHQRInBE3dBBUxb4CEVv9VD58hUzMIWuhNRWyUMs_qc23mUQlzWq00F__0m00)


  

## **5. Hợp nhất kết quả phân tích**  
  - Lớp Employee: Được sử dụng trong cả hai ca sử dụng "Maintain Timecard" và "Payment", do đó, chỉ có một lớp Employee duy nhất.
  - Lớp TimecardUI và PaymentUI: Các lớp này quản lý giao diện cho các chức năng khác nhau của hai ca sử dụng.
  - Lớp TimecardController và PaymentController: Các lớp điều khiển riêng biệt để xử lý logic cho hai ca sử dụng khác nhau.
  - Lớp Timecard: Lưu trữ thông tin thời gian làm việc cho nhân viên.
  - Lớp Payment: Lưu trữ thông tin về thanh toán cho nhân viên.
---
![](https://www.planttext.com/api/plantuml/png/T99B2eCm54NdMSNRW3iG4Ke77HHAQHSGugE8-KYI3aHSMGTTKhVGn2PDj5OCICxnvLxnzNZMnb9jxu8JOhfMWbO6YRzwoZfwGpZILbxyQWKogXieopCoMrKm4W1tCqwDWOYlXtaVmfh8Zx5Jqch5EMfd4h8jVOTaR2zwhWP4psRYX2a5FT51eBJBVE7Lm6AurU10Gx0vLt8MYis8FzizPSMBejfecJbPzTpzRyJAdo-TMdYsJfs4L6GrOvF7Qk0RrIWR_pEy0G00__y30000)
