
## Phần 1: Xác định

Thực thể: BOOKING:

Thuộc tính: 

+ BookingID: int (PK)
+ CustomerID: int (FK)
+ Status: varchar(50)

Thực thể CUSTOMER:

Thuộc tính: 

+ CustomerID: int (PK)
+ CustomerEmail: varchar(300)
+ CustomerName: varchar(80)
+ CustomerPhone: varchar(11)
+ IsVip: bit

Thực thể: CINEMA_BRANCH:

Thuộc tính:

+ BranchID: int (PK)
+ BranchAddress: varchar(255)
+ BranchName: varchar(255)
+ IsOpened: bit

Thực thể STORAGE:

Thuộc tính:

+ StorageID: int (PK)
+ ComboID: int (FK)
+ BranchID: int (FK)
+ Quantity: int

Thực thể COMBO: 

Thuộc tính:

+ ComboID: int (PK)
+ ComboName: varchar(255)
+ ComboPrice: double
+ ComboDescription: varchar(255)
+ IsActivate: boolean

Thực thể BOOKING_DETAIL

Thuộc tính:

+ B_Detail_id: int (PK)
+ ComboID: int (FK)
+ BookingID: int (FK)
+ Status: boolean
+ Quantity: int
+ PriceAtPurchase: double
+ TotalPrice: double

Thực thể TICKET: 

Thuộc tính: 

+ ShowTimeID: int (PK + FK)
+ SeatID: int (PK + FK)
+ PricingID: int (FK)
+ Status: varchar(30)

Thực thể: PRICING:

Thuộc tính:

+ PricingID: int (PK)
+ BasePrice: doube
+ Condition: enum('TimeSlot', 'DayType')

Thực thể SHOWTIME

Thuộc tính:

+ ShowtimeID: int (PK)
+ StartTime: datetime
+ EndTime: datetime

Thực thể SEAT:

Thuộc tính:

+ SeatID: int (PK)
+ SeatPosition: varchar(10)
+ SeatType: varchar(25)

## Phần 3:

+ Tại vì với Cấu trúc của BOOKING_DETAIL thì khi người dùng mua thì sẽ lưu trực tiếp giá mua của người dùng tại thời điểm đó đồng thời sau này khi tính lại doanh thu của tháng thì sẽ không bị sai lệch khi chỉnh lại giá của vé tháng sau

+ Còn đối với Combo thì ta sẽ để mỗi chi nhánh sẽ có 1 kho riêng, tỏng kho đó ta sẽ lưu số lượng combo để khi mà nếu người dùng mua combo tại đó thì sẽ cập nhật trực tiếp trong kho ấy mà không cần phải dùng chung với các chi nhánh, tách biệt ra với các chi nhánh
