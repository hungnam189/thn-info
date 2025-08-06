# BÀI TẬP CODE: TÍNH LƯƠNG NET CỦA NHÂN VIÊN

- Hãy viết một chương trình Java sử dụng *các kiểu dữ liệu nguyên thủy* để tính lương thực lãnh của một nhân viên.
- Trả về kết quả kiểu double cho hàm calculateNet()

## Dữ liệu đầu vào được gán trực tiếp trong mã nguồn, bao gồm:
- (1) basicSalary Lương cơ bản - kiểu int- giá trị 5,000,000 VNĐ(5 triệu)
- (2) overtimeHours Số giờ làm thêm - kiểu int - giá trị 10.
- (3) overtimeRate Tiền công mỗi giờ làm thêm - kiểu double - giá trị 200,000 VNĐ(200k)

## Công thức tính:
- (4) lương làm thêm = (2) * (3)
- (5) lương gộp(GROSS): (1) + (4)

# Thuế: sử dụng toán tử condition(3 ngôi để xử lý) điều kiện
- Nếu lương gộp ≤ 5,000,000 VNĐ thì thuế = 0.
- Nếu lương gộp > 5,000,000 VNĐ thì thuế = 10% của lương gộp.

## Lương thực lãnh:
- Lương thực lãnh(NET) = lương GROSS - Thuế

## Yêu cầu thêm
- Viết dạng Funtion, hướng đối tượng