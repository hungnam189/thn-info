**Coding Conventions**

# 1. Tài liệu tham khảo

**Microsoft**
[**https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions**](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)

**Google Style**
[**https://google.github.io/styleguide/csharp-style.html**](https://google.github.io/styleguide/csharp-style.html)

**Thắng Chung**
[**https://github.com/thangchung/clean-code-dotnet**](https://github.com/thangchung/clean-code-dotnet)

# 2. Quy ước đặt tên (Naming conventions)

- Có 3 cách đặt tên phổ dụng nhất:

<table><tbody><tr><th><p><strong>Kiểu đặt tên</strong></p></th><th><p><strong>Mô tả</strong></p></th><th><p><strong>Ví dụ</strong></p></th></tr><tr><td><p><strong>Pascal Case</strong></p></td><td><ul><li>Chữ cái đầu tiên trong từ định danh và chữ cái đầu tiên của mỗi từ nối theo sau phải được viết hoa.</li><li>Sử dụng Pascal Case để đặt tên cho một tên có từ 3 ký tự trở lên.</li></ul></td><td><p><strong>CodingConvention</strong></p></td></tr><tr><td><p><strong>Camel Case</strong></p></td><td><ul><li>Chữ cái đầu tiên trong từ định danh là chữ thường và chữ cái đầu tiên của mối từ nối theo sau phải được viết hoa.</li></ul></td><td><p><strong>codingConvention</strong></p></td></tr><tr><td><p><strong>Uppercase</strong></p></td><td><ul><li>Tất cả các ký tự trong từ định danh phải được viết hoa.</li><li>Sử dụng quy tắc này đối với tên định danh có từ 2 ký tự trở xuống</li><li>hoặc tên biết Global</li></ul></td><td><p><strong>System.IO, System.Web.IO</strong></p></td></tr></tbody></table>

- Tóm tắt cách sử dụng các quy tắc.

| **Loại** | **Kiểu đặt tên** | **Ví dụ** | **Ghi chú** |
| --- | --- | --- | --- |
| Biến(Public variable) | Pascal Case | FirstName | Danh từ |
| Biến (private field) | Camel Case | \_lowerCamelCase | Có tiền tố “\_” |
| Biến (Local field) | Camel Case | lowerCamelCase | Tiền tố chữ thường |
| Hằng số Public (constant) | Uppercase | FIRST_WEEK_DAY  <br>FirstWeekDay | Dấu gạch chân giữa các từ  <br>Hoặc sử dụng Pascal Case |
| Hằng số private (constant) | Camel Case | firstWeekDay | Như biến bình thường |
| Tên Class, Enum | Pascal Case | UserRepository | Danh từ |
| Tham số(parameters) | Camel Case | displayTime | Danh từ |
| Thuộc tính(Prototype) | Pascal Case | BackgroundColor | Danh từ |
| Phương thức(Method) | Pascal Case | GetAge() | Động từ |
| Sự kiện(Event) | Pascal Case | SelectIndexChanged | Có hậu tố EventHandler |
| Giao diện(Interface) | Pascal Case | IUserRepository | Có tiền tố “I” |

- Tránh thêm các tiền tố hoặc hậu tố dư thừa vô nghĩa.

| **Nên** | **Không nên refactor** |
| --- | --- |
| enum Border { ... } | enum BoderEnum { ... } |
| class Human { ... } | class CHuman { ... } |

- Không thêm tên lớp chứa vào tên thuộc tính.

| **Nên** | **Không nên** |
| --- | --- |
| Animal.Weight | Animal.WeightAnimal |

- Tên biến, phương thức bool phải thể hiện được ý nghĩa nếu trả về true hoặc false. Nên sử dụng tiền tố “Is” “Can” “Has” trước tên biến, phương thức.

| **Nên** | **Không nên refactor** |
| --- | --- |
| bool IsAdmin(int n) { } | bool CheckAdmin(int n) { } |
| bool IsExpired() { } | bool Expired() { } |
| bool isChecked = true; | bool checked = true; |

- Không dùng các tên giống nhau(chỉ phân biệt kiểu chữ in hoa hay thường), Ta khó nhận ra các định danh nhất là khi trong cùng ngữ cảnh và chỉ phân biệt các định danh bằng kiểu chữ in hoa/thường.
- Không tạo 2 namespace cùng tên và chỉ khác nhau ở kiểu chữ viết(chữ hoa/Chữ thường). Ví dụ:

```
Namespace SunAsterisk

Namespace sunAsterisk
```

- Không nên xây dựng 1 phương thức với các tham số có cùng tên và chỉ khác nhau kiểu chữ. Ví dụ: “**void MyFunction(string a, string A)”**
- Không xây dựng 1 kiểu các tên Prototype giống nhau và chỉ phân biệt kiểu chữ. Ví dụ:

```
int Color {get, set}

int COLOR {get, set}
```


- Không đặt tên các phương thức có cùng tên và chỉ khác nhau ở kiểu chữ

```
void total()

void Total()
```


# 3. Tiền tố một số Control (Web)

- Bắt buộc đặt tên cho tất cả các control có tham gia xử lý dưới nền. Một số control được đặt theo kiểu Pascal với phần tiền tố như sau:

| **Control** | **Tiền tố** | **Ví dụ** |
| --- | --- | --- |
| Panel | pnl | pnlUser |
| Check box | chk | chkReadOnly |
| CheckBoxList | cbl |     |
| Combo box | cmb | cmbLanguage |
| DropDownList | ddl |     |
| Button | btn | btnCreate, btnExit, btnSave |
| Dialog | dlg | dlgFileOpen |
| Form | frm | frmCreateUser |
| Label | lbl | lblFullName |
| Textbox | txt | txtFullName |
| HiddenField | hdn |     |
| Listbox | lst |     |
| DataList | dtl | dtlCustomers |
| DataGrid | dtg |     |
| Fieldset | flds | fldsCreateUserGroup |
| CheckedListBox | ckl |     |
| DateTimePicker | dtp |     |
| MaskedTextBox | mtx |     |
| LinkLabel | llb |     |
| RadioButton | rdo |     |
| TreeView | tvw |     |
| ListView | lvw |     |
| MultiView | mv  |     |
| PictureBox | pic |     |
| RickTextBox | rtx |     |
| ProgressBar | prg |     |
| Image | img |     |
| DataTable | dt  | dtUsers |
| DataSet | dts | dtsUsers |


# 4. Quy định phân bổ mã nguồn

- Mỗi file mã nguồn chỉ chứa duy nhất một Class. Tên class chính phải trùng với tên file mã nguồn. Ví dụ: **Class Student** sẽ được chứa trong file **Student.cs** .
- Với các kiểu enum, struct độc lập đơn giản ngoài class có thể được khai báo trong một file mã nguồn riêng hoặc trong file mã nguồn của class khác.
- Interface phải được khai báo trong một file mã nguồn riêng.

# 5. Quy ước viết câu lệnh/ về số lượng:

- Mỗi câu lệnh riêng rẽ trên một dòng
- Hàm (Method) không được quá 30 dòng.(Clean Code)
- Lớp (class) không được quá 500 dòng.(Clean Code)
- Một hàm không nên vượt quá 5 tham số. Nên giữ số lượng <= 3
- Một hàm chỉ nên làm một việc duy nhất. Trong trường hợp đặc biệt có thể làm 2 việc nhưng phải viết rõ tên hàm để nói lên điều này. Ví dụ: increaseDownloadCounterAndSaveToDatabase
- Khi khai báo biến 1 dòng chỉ chứa 1 biến
- Một dòng không nên chứa 80 kí tự. (Oracle)
- Các câu lệnh lồng nhau tối đa không được quá **4 cấp**.
- Ví dụ:

<table><tbody><tr><th><p><strong>Nên</strong></p></th><th><p><strong>Không nên</strong></p></th></tr><tr><td colspan="2"><ul><li>Mỗi câu lệnh riêng rẽ trên một dòng.</li></ul></td></tr><tr><td><p>private int x = 3;</p><p>private int y = 5;</p><p>if (a &gt; b)</p><p>a++;</p><p>else</p><p>b++;</p></td><td><p>private int x = 3, y = 5;</p><p>if (a &gt; b) a++;</p><p>Else b++;</p></td></tr><tr><td colspan="2"><ul><li>Đối với biến kiểu bool, tránh dùng phép so sánh với true hoặc false</li></ul></td></tr><tr><td><p>if (isValidFirst &amp;&amp; isValidSecond)</p><p>DoSomeThing();</p><p></p><p>if (!item.IsValid())</p><p>item.Remove();</p></td><td><p>if (isValidFirst == true &amp;&amp; isValidSecond == true)</p><p>DoSomeThing();</p><p></p><p>if (item.IsValid() == false)</p><p>item.Remove();</p></td></tr></tbody></table>

# 6. Khối mã lệnh

<table><tbody><tr><th><p><strong>Nên</strong></p></th><th><p><strong>Không nên</strong></p></th></tr><tr><td colspan="2"><ul><li>Sử dụng cặp dấu { } để đánh dấu một khối mã nguồn.</li><li>Mỗi dấu ngoặc nằm trên một dòng (Ngoại lệ, kiểu enum, thuộc tính gọn hoặc khởi tạo giá trị cho mảng có thể không cần).</li><li>Trong các lệnh if, for, foreach, ... nếu chỉ có một lệnh thì có thể không cần đánh dấu khối mã nguồn</li></ul></td></tr><tr><td><p>void Swap(ref int a, ref int b)</p><p>{</p><p>int c = a;</p><p>a = b;</p><p>b = c;</p><p>}</p></td><td><p>void Swap(ref int a, ref int b)</p><p>{ int c = a;</p><p>a = b;</p><p>b = c;</p><p>}</p><p></p><p>void Swap(ref int a, ref int b) {</p><p>int c = a;</p><p>a = b;</p><p>b = c;</p><p>}</p></td></tr></tbody></table>

# 7. Quy tắc xuống hàng

- Tài liệu: [**Link here**](https://www.oracle.com/java/technologies/javase/codeconventions-indentation.html#313)
- Nếu có dấu "," thì xuống hàng sau dấu ",".

someMethod(longExpression1, longExpression2, longExpression3,

longExpression4, longExpression5);

var = someMethod1(longExpression1,

someMethod2(longExpression2,

longExpression3));

- Xuống hàng trước toán tử + - ...

longName1 = longName2 \* (longName3 + longName4 - longName5)

\+ 4 \* longname6; // PREFER

longName1 = longName2 \* (longName3 + longName4

\- longName5) + 4 \* longname6;

- Nếu có nhiều cấp lồng nhau, thì xuống hàng theo từng cấp.
- Dòng xuống hàng mới thì được bắt đầu ở cùng cột với đoạn lệnh cùng cấp ở trên.

# 8. Thụt đầu dòng và khoảng cách

- Viết cách vào một khoảng tab đối với các lệnh nằm trong khối lệnh { }.
- Viết cách vào một khoảng tab đối với lệnh ngay sau if, else, while, for, foreach.
- Viết cách một khoảng trắng xung quanh các toán tử 2 ngôi và 3 ngôi.
- Viết cách một khoảng trắng sau dấu “,” và “;”

# 9. Chú thích (comments)

- Hạn chế dùng comment để giải thích code, thay vào đó hãy cải thiện đoạn code của bạn.
- Chỉ nên dùng comment khi viết documentation cho thư viện, thông tin đính kèm cho class.
- Nếu phải dùng comment: Nên comment trên những đoạn code khó hiểu hoặc chức năng đặc biệt. Ngôn ngữ sử dụng để chú thích phải đồng bộ xuyên suốt chương trình. Chọn một trong hai ngôn ngữ: tiếng Việt Unicode có dấu hoặc tiếng Anh.
- Quy định chú thích:

\+ Chỉ sử dụng // và /// để chú thích. Không dùng /\* \*/.

\+ Có chú thích trên đầu mỗi file source code mô tả chương trình, chức năng của chương trình, tác giả, v.v...

\+ Khối xử lý dữ liệu: Có chú thích trên mỗi class, mỗi phương thức, mỗi thuộc tính của class mô tả chức năng, tham số, v.v...

\+ Khối xử lý giao diện: Có chú thích mô tả chức năng trên mỗi phương thức không phải event, hàm Main.

- Chú thích đơn giản dùng cho:

\+ Đoạn code phức tạp

\+ Mô tả trong thân hàm

\+ Mô tả field

\+ Đoạn code được người không phải tác giả sửa đổi.

# 10. Ngôn ngữ sử dụng.

- Luôn luôn sử dụng kiểu dữ liệu C# thay vì kiểu dữ liệu .NET.

| **Nên** | **Không nên** |
| --- | --- |
| int month;<br><br>double real;<br><br>string name;<br><br>ulong fact; | Int32 month;<br><br>Double real;<br><br>String name;<br><br>UInt64 fact; |