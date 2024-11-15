# Subsystem context diagrams
Một số hệ thống con: BankSystem, PrintService, ProjectManagementDatabase subsystems.

  - Hệ thống con: BankSystem
    
![](https://www.planttext.com/api/plantuml/png/h56zJWCn3Dxz55Qd8f4MrYewLIrBDoHMbf1p8RfSSefpY1FmP0my4gz0SiUXbAvCjcD_FtQ-FZwt75M8VMk16-CmU2Q89bh2dNBDtS2HMXIujuePRunw3Ae5q6DvguRWhTrx5tEaW5BggQWgV0N4zHf3xx2R1fSNy0vWNAHmL9hmK4ZawPewpoOkLIBMJwGRtE2SNcB2-Gn8ZpaStD67LaNZtKWxMIeOfUJ-WQUy2_vb-F7q3og_I2d9fMibwaA_m02StqY8wcJp3IwkLglhUrURG3hE_XX72SPdenPG0kIR4CMY9xrCFhixQ_mrjoLNvv__1W00__y30000)
  - Hệ thống con PrintService
    
![](https://www.planttext.com/api/plantuml/png/h5AzJiCm4Dxz5ATCGI8jh9KLLPIb6r9N5kDSmOfZHsUd8WAUZ857uXMm4r8vXB6Jx-px_ax-_lpQEY_8TurchbO6o3faNdcDS2TCVUYTnmOAs6dX7DmhyKoYOKmExOFeoMgziyR74maubsDJbl360DPheCv0EmxcL-o3CMKyqb58X7qY4QShRArJFXU1MBwWh643KtaD0MSZ85p6Os-EbXhXbJK3xMWfOUJSTKzkh5koh_slfmked96SemdR2jI9VeAPvYdG7f1EAgIE7jfuaRTB0uF8Sgz5KSwsjO7iPhMwVJIL8fH-okHW875mKY9ZAO2_5qModDbR99_q5mz_0_tlRHRmR6v8ENdA6DkYgU9F-m400F__0m00)
  - Hệ thống con ProhectManagementDatabase subsystems

![](https://www.planttext.com/api/plantuml/png/h5FBRi8m4BpxArOv1Qc1zeeYX0eN3fKgSUrbIHRgajZHsg2Yjb_MGp-flr0x3t1ut7hosfwPdHtBlzy_KsEHxQuiXDbA1QmD2IjjGV28Qhiy64ib930hq1YOIzmmba9azVOP3woBOgQLzIinf6dMR2OJ-100en7mJa7L0EE1-192AakynenW4RJmw9mgRQIDqGbdhvHjOGnTUGUEfpt17VfbeTQQIxHIgrgsiHGefgdPhKnJLwpV3wsdV-XoPAOfAPUMamxw1vmEpqvsIRoNRchleV87SNLf86p2-eqo-uGADrIwFdEqk493uMJjJ0RtrE8zAgvEjHS_xGOEp6HPqbN2OkxWpjgWp_AcnELh9ycazuPZYEw7muSNbKjsp2vf0_Le1lOI8n4Iqiya2PwiT-V5krGkBivZlkwj5_lHN9rzvocwIRqL_b6dhEyCjD4Po1qa4c9AAlV_wGy00F__0m00)
# Analysis class to design element map
|  Analysis Class | Design Element |  
|-----------------|----------------|
| LoginForm | LoginForm|
| MaintainTimecardForm | MainEmployeeForm |
| TimecardController | TimecardController |
| PayrollController | PayrollController |
| PayCheck | PayCheck |
| BankService | BankService |
| SystemClockInterface | SystemCLockInterface |
| PayrollController | PayrollControllerImpl |
| Employee | EmployeeEntity |
| Timecard | TimecardEntity |
| Payroll | PayrollProcessor |
| BankTransaction | BankTransactionProcessor |
| PaymentUI | PaymentUIComponent |
| PrintService | PrintServiceProcessor |

# Design element to owning package map
|  Design Element | "Owning" Package |  
|-----------------|----------------|
| LoginForm | Middleware::Security::GUIFramwork |
| MainEmployeeForm | Applications::Employee Activities |
| TimecardController | Applications::Employee Activities |
| SystemClockInterface | Applications::Payroll |
| PayrollController | Applications: Payroll |
| PayCheck | Business Services::Payroll Artifacts |
| BankService | Business::Banking |
| EmployeeEntity | Data Access::Employee Management |
| TimecardEntity | Data Access::Employee Management |
| PayrollProcessor | Business Services::Payroll Processing |
| BankTransactionProcessor | Business Services::Banking |
| PaymentUIComponent | Middleware::User Interface Components |
| PaymentUIComponent | Middleware::Print Services |

# Architectural layers and their dependencies

![]()
