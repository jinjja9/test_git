 # Danh mục danh mục
- [Danh mục](#danh-mục)
- [***\[BUỔI 3\] CÁCH JAVA LƯU TRỮ DỮ LIỆU***](#buổi-3-cách-java-lưu-trữ-dữ-liệu)
  - [1. Cách  Java lưu trữ dữ liệu](#1-cách--java-lưu-trữ-dữ-liệu)
    - [1.1. Kiểu dữ liệu nguyên thủy](#11-kiểu-dữ-liệu-nguyên-thủy)
    - [1.2. Kiểu dữ liệu đối tượng](#12-kiểu-dữ-liệu-đối-tượng)
    - [1.3. Class Object](#13-class-object)
      - [***1.3.1. public final Class getClass()***](#131-public-final-class-getclass)
      - [***1.3.2. int hashCode()***](#132-int-hashcode)
      - [***1.3.3. boolean equals(Object obj)***](#133-boolean-equalsobject-obj)
      - [***1.3.4. Object clone()***](#134-object-clone)
      - [***1.3.5. String toString()***](#135-string-tostring)
    - [1.4 Lớp Wrapper, Boxing, Unboxing](#14-lớp-wrapper-boxing-unboxing)
      - [***1.4.1. Chuyển  đổi kiểu nguyên thủy sang kiểu Wrapper***](#141-chuyển--đổi-kiểu-nguyên-thủy-sang-kiểu-wrapper)
      - [***1.4.2. Chuyển đổi kiểu Wrapper thành kiểu dữ liệu nguyên thủy***](#142-chuyển-đổi-kiểu-wrapper-thành-kiểu-dữ-liệu-nguyên-thủy)
      - [***1.4.3. Các phương thức hữu ích của lớp Wrapper***](#143-các-phương-thức-hữu-ích-của-lớp-wrapper)
  - [2. Các phương thức khởi tạo](#2-các-phương-thức-khởi-tạo)
    - [2.1 Từ khóa this](#21-từ-khóa-this)
      - [***2.1.1 Tham chiếu tới biến của lớp hiện tại***](#211-tham-chiếu-tới-biến-của-lớp-hiện-tại)
      - [***2.1.2 Dùng this() gọi Constructor của lớp hiện tại***](#212-dùng-this-gọi-constructor-của-lớp-hiện-tại)
      - [***2.1.3 Gọi phương thức của lớp hiện tại***](#213-gọi-phương-thức-của-lớp-hiện-tại)
      - [***2.1.4 Sử dụng từ khóa this như 1 tham số của phương thức/Constructor***](#214-sử-dụng-từ-khóa-this-như-1-tham-số-của-phương-thứcconstructor)
      - [***2.1.5 Sử dụng từ khóa this để trả về kết quả của lớp hiện tại***](#215-sử-dụng-từ-khóa-this-để-trả-về-kết-quả-của-lớp-hiện-tại)
    - [**2.2 Từ khóa super**](#22-từ-khóa-super)
      - [***2.2.1 Tham chiếu đến biến trực tiếp của lớp cha***](#221-tham-chiếu-đến-biến-trực-tiếp-của-lớp-cha)
      - [***2.2.2 Truy xuất đến phương thức của lớp cha gần nhất***](#222-truy-xuất-đến-phương-thức-của-lớp-cha-gần-nhất)
      - [***2.2.3 Gọi trực tiếp Constructor của lớp cha***](#223-gọi-trực-tiếp-constructor-của-lớp-cha)
  - [3. Garbage Collection trong Java](#3-garbage-collection-trong-java)
  - [4. Pass by value trong Java là gì?](#4-pass-by-value-trong-java-là-gì)

*** 

# ***[BUỔI 3] CÁCH JAVA LƯU TRỮ DỮ LIỆU***

***

## 1. Cách  Java lưu trữ dữ liệu

Trong Java, kiểu dữ liệu được chia làm 2 loại: 
* Kiểu dữ liệu nguyên thủy
* Kiểu đối tượng

>Để phân biệt 2 kiểu này ta dựa vào tên của nó. Kiểu nguyên thủy bắt đầu bằng **chữ thường**, kiểu đối tượng bắt đầu bằng **chữ hoa**.
### 1.1. Kiểu dữ liệu nguyên thủy
- int
- long
- float
- double
- char
- ...

hoàng hiếu
### 1.2. Kiểu dữ liệu đối tượng
- Array
- String
- class: Dữ liệu kiểu lớp đối tượng.
- interface: Dữ liệu kiểu lớp giao tiếp.

>Lưu trữ của các kiểu dữ liệu:
> - Kiểu dữ liệu nguyên thủy: Giá trị là các kiểu dữ liệu cơ sở .
> - Kiểu dữ liệu đối tượng: Giá trị là địa chỉ của đối tượng

### 1.3. Class Object

>*Tài liệu tham khảo*:  [Class Object](https://yellowcodebooks.com/2017/08/02/java-bai-24-lop-object/)

Mặc định lớp Object là lớp cha của tất cả các lớp trong Java.

![Alt text](image-1.png)

Sử dụng lớp Object là hữu ích nếu bạn muốn tham chiếu bất kỳ đối tượng nào mà bạn chưa biết kiểu dữ liệu của đối tượng đó.

**Ví dụ**: Giả sử phương thức getObject() trả về một đối tượng nhưng nó có thể là bất kỳ kiểu nào như Employee,Student, ... chúng ta có thể sử dụng biến tham chiếu của lớp Object để tham chiếu tới đối tượng đó.
```Java
Object obj = getObject();
```
#### ***1.3.1. public final Class getClass()***
\- Phương thức này trả về lớp ` Class`. Từ lớp Class đó có thể lấy được các thông tin metadata của class hiện tại.
```Java
public class Hinhtron {
    public static void main(String[] args) {
        Object hinhTron = new Object();
        System.out.println("Thông tin đối tượng HinhTron: " + hinhTron.getClass());
        System.out.println("Thông tin đối tượng HinhTron: " + hinhTron.getClass().getName());
        System.out.println("Thông tin đối tượng HinhTron: " + hinhTron.getClass().getSimpleName());
    }
}
```
![Alt text](image-2.png)

#### ***1.3.2. int hashCode()***

\- Trả về số hashcode cho đối tượng hiện tại.

```Java
public class Hinhtron {
    public static void main(String[] args) {
        Object hinhTron1 = new Object();
        Object hinhTron2 = new Object();

        System.out.println("Hashcode của HinhTron 1: " + hinhTron1.hashCode());
        System.out.println("Hashcode của HinhTron 2: " + hinhTron2.hashCode());
    }
}
```
![Alt text](image-3.png)

#### ***1.3.3. boolean equals(Object obj)***
\- So sánh đối tượng đã cho với đối tượng hiện tại.
```Java
public class Hinhtron {
    public static void main(String[] args) {
        Object hinhTron1 = new Object();
        Object hinhTron2 = hinhTron1;

        System.out.println(hinhTron1.equals(hinhTron2));
    }
}
```
![Alt text](image-4.png)

#### ***1.3.4. Object clone()***
\- Phương thức này giúp khởi tạo và trả về một bản sao của đối tượng được gọi. 

#### ***1.3.5. String toString()***
\- Trả về chuỗi ký tự đại diện của đối tượng hiện tại. Nó là sự kết hợp của chuỗi **getClass().getName() + "@" + hashCode()**

```Java
public class Hinhtron {
    public static void main(String[] args) {
        Object hinhTron1 = new Object();

        System.out.println(hinhTron1.toString());
    }
}
```
![Alt text](image-5.png)

### 1.4 Lớp Wrapper, Boxing, Unboxing

>Tài liệu tham khảo: [Lớp Wrapper](https://yellowcodebooks.com/2018/01/19/java-bai-36-lop-wrapper/)


\- Lớp Wrapper trong java cung cấp cơ chế để chuyển đổi kiểu dữ liệu nguyên thủy thành kiểu đối tượng và từ đối tượng thành kiểu dữ liệu nguyên thủy.
| **Kiểu nguyên thủy** | **Kiểu Wrapper** |
| -------------------- | ---------------- |
| boolean              | Boolean          |
| char                 | Character        |
| byte                 | Byte             |
| short                | Short            |
| int                  | Integer          |
| long                 | Long             |
| float                | Float            |
| double               | Double           |

#### ***1.4.1. Chuyển  đổi kiểu nguyên thủy sang kiểu Wrapper***
\- Việc chuyển đổi một kiểu nguyên thủy sang kiểu Wrapper của nó người ta gọi là **Boxing** (đóng hộp).

```Java
//Các dạng Boxing
int a=100;
Integer i = new Integer(a);
Float f = new Float(4.5);
Charater ch = new Character('a');
Boolean b = new Boolean(true);
```

```Java
// Các dạng Autoboxing
int a = 500;
Integer i = a;
Float f = 4.5f;
Character ch = 'a';
```

#### ***1.4.2. Chuyển đổi kiểu Wrapper thành kiểu dữ liệu nguyên thủy***
\- khi bạn chuyển từ một kiểu Wrapper sang kiểu nguyên thủy của nó người ta gọi là Unboxing (Mở hộp).

```Java
//Cách viết 1
int a = 500;
Integer i = a;
int i2 = i.intValue();
Float f = 4.5f;
float f2 = f.floatValue();
Character ch = 'a';
char ch1 = a.charValue();
```

```Java
// Cách viết 2
int a = 500;
Integer i = a;
int i2 = i;
Float f = 4.5f;
float f2 = f;
Character ch = 'a';
char ch2 = ch;
```

#### ***1.4.3. Các phương thức hữu ích của lớp Wrapper***
>**parseXxx()**

Tham số truyền vào cho phương thức này là 1 chuỗi, kết quả nhận được là một giá trị nguyên thủy của chuỗi truyền vào.
```Java
int i = Integer.parseInt("10");
float f = Float.parseFloat("4.5");

System.out.println(i);
System.out.println(f);
```
![Alt text](image-7.png)

>**toString()**
```Java
String s = Integer.toString(10);
System.out.printfln(s);
```
>**xxxValue()**

>**compareTo()**

Với việc bạn gọi **lopWrapper1.compareTo(lopWrapper2)**, thì kết quả sẽ như sau.

– Nếu kết quả của phương thức trả về một số âm, thì lopWrapper1 sẽ có giá trị `nhỏ hơn` lopWrapper2.

– Nếu kết quả của phương thức trả về số 0, thì lopWrapper1 sẽ có giá trị `bằng` với lopWrapper2.

– Nếu kết quả của phương thức trả về một số dương, thì lopWrapper1 sẽ có giá trị `lớn hơn` lopWrapper2.

```Java
Integer i = 50;
Integer i1 = Integer.parseInt("50");
Integer i2 = 52;
Integer i3=30;
System.out.println(i.compareTo(i1));
System.out.println(i.compareTo(i2));
System.out.println(i.compareTo(i3));

```

```Java
0
-1
1
```

>**equals()**

## 2. Các phương thức khởi tạo
Cú pháp:
```Java
[khả_năng_truy_cập] tên_phương_thức (){
  //Các dòng code
}
```
### 2.1 Từ khóa this

#### ***2.1.1 Tham chiếu tới biến của lớp hiện tại***
Nếu biến toàn cục và tham số trùng tên nhau thì `this` để phân biệt 2 cái này:
```Java
public class Student{
  int id;
  String name;
  Student(int id,String name){
    this.id=id;
    this.name=name;
  }
  void in(){
    System.out.println(id + " " + name);
  }
  public static void main(String args[]){
    Student s1 = new Student(111, "Phan");
    Student s2 = new Student(222,"Thắm");
    s1.in();
    s2.in();
  }
}
```
![Alt text](image-8.png)

#### ***2.1.2 Dùng this() gọi Constructor của lớp hiện tại***
```Java
public class Student{
    int id;
    String name;
    Student (){
        System.out.println("gọi Student");
    }
    Student(int id, String name) {
        this();
        this.id = id;
        this.name = name;
    }
    void in(){
        System.out.println(id + " " + name);
    }
    public static void main(String args[]) {
        Student s1 = new Student(111, "Phan");
        Student s2 = new Student(222, "Thắm");
        s1.in();
        s2.in();
    }
}
```
![Alt text](image-9.png)

#### ***2.1.3 Gọi phương thức của lớp hiện tại***
Bạn có thể sử dụng từ khóa this để gọi phương thức của lớp hiện tại. Nếu bạn không sử dụng từ khóa this, trình biên dịch sẽ tự động thêm từ khóa this cho việc gọi phương thức.

```Java
public class Student{
    void m(){
        System.out.print("Gọi phương thức bằng từ khóa this");
    }
    void in() {
        m();
    }
    public static void main(String args[]){
        Student s = new Student();
        s.in();
    }
}
```
![Alt text](image-10.png)

 #### ***2.1.4 Sử dụng từ khóa this như 1 tham số của phương thức/Constructor***

 ```Java
 public class Example4 {
    void m(Example4 obj) {
        System.out.println("Hello Java");
    }
 
    void p() {
        m(this);
    }
 
    public static void main(String args[]) {
        Example4 o1 = new Example4();
        o1.p();
    }
}
 ```
 >Kết quả : Hello Java

#### ***2.1.5 Sử dụng từ khóa this để trả về kết quả của lớp hiện tại***

Ví dụ 1:
```Java
Class A{
  A getA(){
    return this;
  }
  void msg(){
    System.out.println("Hello Java");
  }
}
Class Test1{
  public static void main(String args[]){
    new A().getA().msg();
  }
}
```
> Hello Java

Ví dụ 2:
```Java
public class Student{
    String name;
    String age;
    public Student(String name, String age){
        this.name=name;
        this.age=age;
    }
    public Student getStudent(){
        return this;
    }
    public static void main(String args[]){
        Student s = new Student("Green","18");
        System.out.println(s.getStudent().name);
        System.out.println(s.getStudent().age);
    }
}
```

```Java
Green
18
```
### **2.2 Từ khóa super**

#### ***2.2.1 Tham chiếu đến biến trực tiếp của lớp cha***
Phân biệt đâu là giá trị của lớp cin và đâu là giá trị của lớp cha gần nhất khi chúng bị trùng tên

```Java
class Vehicle{
    int speed = 50;
}

public class Bike extends Vehicle{
    int speed = 100;
    void in(){
        System.out.println(super.speed);
    }
    public static void main(String args[]){
        Bike b = new Bike();
        b.in();
    }
}
```
> 50

#### ***2.2.2 Truy xuất đến phương thức của lớp cha gần nhất***

```Java
class Hinhhoc{
    String ten;
    public void xuatTen(){
        System.out.println(ten);
    }
}

public class HinhTron extends Hinhhoc{
    public HinhTron(){
        ten = "Hình Tròn";
    }
    public void xuatTen(){
        super.xuatTen();
        System.out.println("Đã xuất");
    }
    public static void main(String args[]){
        HinhTron ht = new HinhTron();
        ht.xuatTen();
    }
}
```

```Java
Hình Tròn
Đã xuất
```

#### ***2.2.3 Gọi trực tiếp Constructor của lớp cha***

```Java
class Vehicle {
    Vehicle() {
        System.out.println("Vehicle is created");
    }
}
 
class Bike2 extends Vehicle {
    Bike2() {
        super();//gọi Constructor của lớp cha  
        System.out.println("Bike is created");
    }
 
    public static void main(String args[]) {
        Bike2 b = new Bike2();
    }
}
```

```Java
Vehicle is created
Bike is created
```
## 3. Garbage Collection trong Java
Được sử dụng để thực hiện quá trình tự động khôi phục lại bộ nhớ không được sử dụng tại runtime một cách tự động. Nói cách khác, đó là một cách để phá hủy các đối tượng không sử dụng nữa.

**Ưu điểm của Garbage Collection**
- Nó làm cho việc sử dụng bộ nhớ java hiệu quả bởi vì bộ thu gom rác loại bỏ các đối tượng không được tham chiếu.
- Nó được thực hiện tự động bởi trình thu gom rác (một phần của JVM) vì vậy chúng ta không cần phải nỗ lực nhiều để giải phóng bộ nhớ.

**Cách để có một đối tượng không được tham chiếu?**
- Gán giá trị null
- Gán đối tượng đến một tham chiếu khác
- Bởi 1 đối tượng annonymous

**Phương thức finalize()**

Được gọi mỗi lần đối tượng thu gom rác.
> protected void finalize(){}

**Phương thức gc()**

Đc dùng để thu gom rác để thực hiện quá trình dọn dẹp

## 4. Pass by value trong Java là gì?

>Tài liệu tham khảo: [Truyền giá trị và tham chiếu](https://viettuts.vn/java/truyen-gia-tri-va-tham-chieu-pass-value-va-pass-reference-trong-java)

- Nếu chúng ta gọi 1 phương thức và truyền giá trị cho một giá trị cho phương thức đó được gọi là truyền giá trị (Pass by value).
- Việc thay đổi giá trị chỉ có hiệu lực trong phương thức được gọi, không có hiệu lực bên ngoài phương thức.

**Ví dụ**
```Java
public class Operation1 {
    int data = 50;
 
    void change(int data) {
        data = data + 100;
    }
 
    public static void main(String args[]) {
        Operation1 op = new Operation1();
 
        System.out.println("Trước khi thay đổi: " + op.data);
        op.change(500);
        System.out.println("Sau khi thay đổi: " + op.data);
    }
}
```

```Java
Trước khi thay đổi: 50
Sau khi thay đổi: 50
```