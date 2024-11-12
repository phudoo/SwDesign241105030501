**Phân tích ca sử dụng Create Employee Report**

### Các lớp phân tích

#### Lớp Boundary
- **EmployeeReportForm:** Đây là giao diện người dùng cho phép tạo báo cáo nhân viên.
- **ProjectManagementDatabase:** Cung cấp quyền truy cập vào cơ sở dữ liệu quản lý dự án để lấy thông tin cần thiết.

#### Lớp Control
- **EmployeeReportController:** Điều khiển luồng tạo báo cáo nhân viên, nhận yêu cầu từ `EmployeeReportForm`, truy cập dữ liệu qua `ProjectManagementDatabase`, và tạo đối tượng báo cáo `EmployeeReport`.

#### Lớp Entity
- **EmployeeReport:** Đối tượng biểu diễn báo cáo nhân viên bao gồm các thông tin về loại báo cáo, ngày bắt đầu và kết thúc, số tài khoản chi phí, và nội dung báo cáo.

### Nhiệm vụ của từng lớp

#### Lớp Boundary

- **EmployeeReportForm:**
  - Hiển thị biểu mẫu để người dùng chọn loại báo cáo, nhập khoảng thời gian và số tài khoản chi phí (nếu có).
  - Gửi yêu cầu tạo báo cáo đến `EmployeeReportController`.

- **ProjectManagementDatabase:**
  - Cung cấp dữ liệu cần thiết từ cơ sở dữ liệu cho quá trình tạo báo cáo.

#### Lớp Control

- **EmployeeReportController:**
  - Nhận yêu cầu từ `EmployeeReportForm`.
  - Tương tác với `ProjectManagementDatabase` để lấy dữ liệu cần thiết.
  - Tạo và điền thông tin vào đối tượng `EmployeeReport`.
  - Trả kết quả báo cáo cho `EmployeeReportForm` để hiển thị.

#### Lớp Entity

- **EmployeeReport:**
  - **reportType:** Loại báo cáo (ví dụ: hàng tháng, hàng quý).
  - **beginDate và endDate:** Khoảng thời gian của báo cáo.
  - **chargeNumber:** Số tài khoản chi phí liên quan (nếu có).
  - **content:** Nội dung chi tiết của báo cáo.
  ## Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/f9J1JiCm38RlUGgBC_00713I1e834c98dBtKwm9fCXmNj6VZm2Fn2ZXTMqRLZGbwMBl4_nVdjvFFzu-B9CXILzwWbSXmMQryN1EPUQn3WRpkH-vf5Lck8bV6nY0S_M1giXdrn8Q2E1bAJO62Sqm4TnoVoCej1Yofqk1fEsECwZp1Z5vg2fPWwh1ahE049amer2EXPPf-uEHy95Kuqq1b9G69O3SCtaX7ehSOgfowjFAuRkDLxOJO8Ioo1x-kUnaqkjFAUaN7K3IhOoZrcyIUcbzo6Fggr1c5OfYGGIzmiu2ZXoZeuJhMdE0nyZCLELV0pl0Z0_hifElAEolJ62diw9N0Bf5BWb1NS-BKC7Vhzcz7cJM7CUA-B4VzxggrXxLJEoElsV-KZcHnQ7rIWrFtVm9rQbZnVVjIscIxOI7EiyVmvcJvNVi_-rHI8CQSPNiUkZRgtRBB61EbV78IQjrbsP-TWrpTEdcDVaHxkA_V07qrt7yrypPFy-kkfdyri_vPEDr9tkpVUhWZj8bbK678f-wwWy8bYrpaqTnC5_gRx-ul0000__y30000)

  ## Class Diagram
   ![Diagram](https://www.planttext.com/api/plantuml/png/V591JiGm3Bpt5Jd2eUBU0rgfm0s4M3xWfgORb2R5TYjLY9Tnu4by0OTMrRBTaakL6MV67lVxysl70YHzwxFCUc0sjstduuZuX5qakOlKclVC_9xQSUTXJDZ5vOmrA5DbIKwG72pCN3sn2qhurYFB7WPKxEEyQnc3KFGUQV6sX21u8ZQ0TxN2AszM-QLsmsIMphMbT7qUEpI5sGkvqCnCXOqBDsgWHFhCC8Pw3Te3K8CFVLjfroSwLkV187_Xb5r0IkrFz76hZnHVqSez16YmLLATe0B69P0N57ieZqnvS_epAytpw-tC2yCw8clcKwpPPkLQHXzFg-B_NsqFMEX2D2KSaA_I96nqnP1bE-qf_QS_0000__y30000)

---

**Phân tích ca sử dụng Create Administrative Report**

### Các lớp phân tích

#### Lớp Boundary
- **AdministrativeReportForm:** Giao diện người dùng cho phép tạo báo cáo hành chính.
- **ProjectManagementDatabase:** Cung cấp dữ liệu từ cơ sở dữ liệu quản lý dự án để tạo báo cáo.

#### Lớp Control
- **AdministrativeReportController:** Điều khiển luồng tạo báo cáo hành chính, nhận yêu cầu từ `AdministrativeReportForm`, truy cập dữ liệu qua `ProjectManagementDatabase`, và tạo đối tượng `Report`.

#### Lớp Entity
- **Report:** Đối tượng biểu diễn báo cáo hành chính, chứa thông tin về loại báo cáo, ngày tháng, và nội dung báo cáo.

### Nhiệm vụ của từng lớp

- **AdministrativeReportForm:**
  - Giao diện để người dùng chọn loại báo cáo và nhập các thông tin cần thiết.
  - Gửi yêu cầu đến `AdministrativeReportController`.

- **ProjectManagementDatabase:**
  - Cung cấp dữ liệu cần thiết để tạo báo cáo từ cơ sở dữ liệu.

- **AdministrativeReportController:**
  - Nhận yêu cầu từ `AdministrativeReportForm`.
  - Truy cập dữ liệu từ `ProjectManagementDatabase`.
  - Tạo và điền thông tin vào đối tượng `Report`.
  - Trả kết quả báo cáo cho `AdministrativeReportForm` để hiển thị.

- **Report:**
  - Đối tượng chứa thông tin về loại báo cáo, ngày tháng và nội dung báo cáo.

---

### Các phân tích còn lại

#### Maintain Purchase Order
- **Boundary, Control, Entity**: 

#### Login
- **Boundary, Control, Entity**:

#### Maintain Employee Info
- **Boundary, Control, Entity**: 

#### Run Payroll
- **Boundary, Control, Entity**: 

---

Nếu bạn cần bổ sung hoặc chi tiết hơn các phân tích còn lại, hãy cho mình biết nhé!

# Code Java mô phỏng ca sử dụng Maintain Timecard

```java
package maintain;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.Scanner;

// Class đại diện cho timecard
class Timecard {
    private int employeeId;
    private LocalDate startDate;
    private LocalDate endDate;
    private LocalDate submittedDate;
    private boolean isSubmitted;
    private Map<Integer, Map<LocalDate, Double>> hoursPerChargeNumber; // Charge number -> Date -> hours
    private static final int MAX_HOURS_PER_DAY = 24;
    private static final int MAX_HOURS_PER_WEEK = 40;

    public Timecard(int employeeId) {
        this.employeeId = employeeId;
        this.startDate = LocalDate.now().minusDays(LocalDate.now().getDayOfWeek().getValue() - 1);
        this.endDate = startDate.plusDays(6);
        this.isSubmitted = false;
        this.hoursPerChargeNumber = new HashMap<>();
    }

    public boolean addHours(int chargeNumber, LocalDate date, double hours) {
        if (isSubmitted) {
            System.out.println("Timecard đã được submit, không thể thay đổi.");
            return false;
        }
        
        if (hours > MAX_HOURS_PER_DAY) {
            System.out.println("Số giờ làm việc trong ngày không thể vượt quá 24 giờ.");
            return false;
        }

        if (date.isBefore(startDate) || date.isAfter(endDate)) {
            System.out.println("Ngày không nằm trong khoảng thời gian của timecard.");
            return false;
        }

        // Tính tổng số giờ trong ngày
        double totalHoursForDay = hoursPerChargeNumber.values().stream()
            .mapToDouble(dateMap -> dateMap.getOrDefault(date, 0.0))
            .sum() + hours;

        if (totalHoursForDay > MAX_HOURS_PER_DAY) {
            System.out.println("Tổng số giờ làm việc trong ngày vượt quá 24 giờ.");
            return false;
        }

        hoursPerChargeNumber.computeIfAbsent(chargeNumber, k -> new HashMap<>())
                           .put(date, hours);
        return true;
    }

    public void displayTimecard() {
        System.out.println("\n=== Thông tin Timecard ===");
        System.out.println("Employee ID: " + employeeId);
        System.out.println("Thời gian: " + startDate + " đến " + endDate);
        System.out.println("Trạng thái: " + (isSubmitted ? "Đã gửi" : "Nháp"));
        if (isSubmitted) {
            System.out.println("Ngày gửi: " + submittedDate);
        }
        System.out.println("\nSố giờ làm việc:");
        hoursPerChargeNumber.forEach((chargeNumber, dateMap) -> {
            System.out.println("\nCharge Number: " + chargeNumber);
            dateMap.forEach((date, hours) -> 
                System.out.println(date + ": " + hours + " giờ"));
        });
    }

    public boolean submit() {
        if (isSubmitted) {
            System.out.println("Timecard đã được submit trước đó.");
            return false;
        }

        // Validate total hours per week
        double totalHours = hoursPerChargeNumber.values().stream()
            .flatMap(dateMap -> dateMap.values().stream())
            .mapToDouble(Double::doubleValue)
            .sum();

        if (totalHours > MAX_HOURS_PER_WEEK) {
            System.out.println("Tổng số giờ làm việc trong tuần vượt quá " + MAX_HOURS_PER_WEEK + " giờ.");
            return false;
        }

        this.submittedDate = LocalDate.now();
        this.isSubmitted = true;
        System.out.println("Timecard đã được gửi thành công.");
        return true;
    }

    public boolean isSubmitted() {
        return isSubmitted;
    }
}

// Class quản lý Project Management Database
class ProjectManagementDB {
    private boolean isAvailable;
    private List<Integer> chargeNumbers;

    public ProjectManagementDB() {
        this.isAvailable = true;
        this.chargeNumbers = new ArrayList<>(Arrays.asList(1001, 1002, 1003, 1004));
    }

    public List<Integer> getChargeNumbers() throws DatabaseUnavailableException {
        if (!isAvailable) {
            throw new DatabaseUnavailableException("Project Management Database không khả dụng.");
        }
        return new ArrayList<>(chargeNumbers);
    }

    public void setAvailable(boolean available) {
        this.isAvailable = available;
    }
}

class DatabaseUnavailableException extends Exception {
    public DatabaseUnavailableException(String message) {
        super(message);
    }
}

// Main class để demo với user input
public class Maintain {
    private static Scanner scanner = new Scanner(System.in);
    private static Map<Integer, Timecard> timecards = new HashMap<>();
    private static ProjectManagementDB projectDB = new ProjectManagementDB();

    public static void main(String[] args) {
        System.out.println("Chào mừng đến với Hệ thống Timecard");
        
        while (true) {
            try {
                System.out.println("\n=== Menu ===");
                System.out.println("1. Xem Timecard");
                System.out.println("2. Thêm Giờ");
                System.out.println("3. Gửi Timecard");
                System.out.println("4. Thoát");
                System.out.print("Chọn một tùy chọn: ");

                int choice = Integer.parseInt(scanner.nextLine());
                
                switch (choice) {
                    case 1:
                        viewTimecard();
                        break;
                    case 2:
                        addHours();
                        break;
                    case 3:
                        submitTimecard();
                        break;
                    case 4:
                        System.out.println("Tạm biệt!");
                        return;
                    default:
                        System.out.println("Tùy chọn không hợp lệ. Vui lòng thử lại.");
                }
            } catch (NumberFormatException e) {
                System.out.println("Vui lòng nhập một số hợp lệ.");
            }
        }
    }

    private static void viewTimecard() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.get(employeeId);
        if (timecard == null) {
            System.out.println("Không tìm thấy timecard. Đang tạo timecard mới...");
            timecard = new Timecard(employeeId);
            timecards.put(employeeId, timecard);
        }
        
        timecard.displayTimecard();
    }

    private static void addHours() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.computeIfAbsent(employeeId, Timecard::new);
        
        try {
            List<Integer> chargeNumbers = projectDB.getChargeNumbers();
            System.out.println("Các charge number có sẵn: " + chargeNumbers);
            
            System.out.print("Nhập charge number: ");
            int chargeNumber = Integer.parseInt(scanner.nextLine());
            
            System.out.print("Nhập ngày (YYYY-MM-DD): ");
            LocalDate date = LocalDate.parse(scanner.nextLine());
            
            System.out.print("Nhập số giờ làm việc: ");
            double hours = Double.parseDouble(scanner.nextLine());
            
            if (timecard.addHours(chargeNumber, date, hours)) {
                System.out.println("Giờ đã được thêm thành công.");
            }
        } catch (DatabaseUnavailableException e) {
            System.out.println(e.getMessage());
            System.out.print("Bạn có muốn tiếp tục mà không có charge numbers không? (y/n): ");
            if (scanner.nextLine().toLowerCase().equals("n")) {
                return;
            }
        }
    }

    private static void submitTimecard() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.get(employeeId);
        if (timecard == null) {
            System.out.println("Không tìm thấy timecard cho nhân viên này.");
            return;
        }
        
        timecard.submit();
    }
}
```
