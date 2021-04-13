# JSON

## JSON là gì?

JSON viết tắt của **J**ava**S**cript **O**bject **N**otation.

JSON là một cú pháp dùng để lưu và trao đổi dữ liệu

JSON là văn bản được viết bởi JavaScript object notation.

Cú pháp JSON:

```yaml
{
    key1: value1,
    key2: value2,
    ...
    keyn: valuen
}
```

## Vì sao sử dụng JSON?

JSON là chuỗi và server chỉ có thể trả về dữ liệu dạng chuỗi

JSON rất nhẹ và có tính dễ hiểu cao hơn so với các kiểu dữ liệu khác

JSON được JS xây dựng các hàm xử lý đi kèm rất mạnh 

## Kiểu dữ liệu hợp lệ của JSON

JSON chấp nhận 1 trong các kiểu dữ liệu dưới đây:

* a string
* a number
* an object \(JSON object\)
* an array
* a boolean
* _null_

> Lưu ý: JSON có thể gán giá trị là 1 hàm\(function\) nhưng khi sử dụng hàm JSON.stringify, JSON.parse giá trị chứa hàm sẽ mất

Ví dụ:

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR',
  myCar: {
    name: 'toyota',
    age: '2',
  },
  hasPhone: true,
  children: [
    {
      name: 'Khôi1',
      age: '1',
      gender: 'MR',
      myCar: null,
      hasPhone: false,

    },
    {
      name: 'Khôi2',
      age: '2',
      gender: 'MS',
      myCar: {
        name: 'toyota',
        age: '2',
      }
    }
  ]
}
```

## Các thao tác liên quan

### Cú pháp truy xuất giá trị chung 

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR',
  myCar: {
    name: 'toyota',
    age: '2',
  },
  children: [
    {
      name: 'Khôi1',
      age: '1',
    },
    {
      name: 'Khôi2',
      age: '2',
    }
  ]
}

//truy xuất key đơn
//cú pháp 1: json['key']
var myName = json['name'];
console.log('my name: ' + myName);
// my name: Khôi

//cú pháp 2: json.key
var myAge = json.age;
console.log('my age: ' + myAge);
// my age: 23


//truy xuất array
var children = json.children[0];
console.log(children);
// {name: "Khôi1", age: "1"}


//truy xuất xếp chồng
var children1Name = json.children[0].name
console.log(children1Name);
// Khôi1
```

### Lấy dữ liệu

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR',
 
}

//cú pháp 1: json['key']
var myName = json['name'];
console.log('my name: ' + myName);

//cú pháp 2: json.key
var myAge = json.age;
console.log('my age: ' + myAge);


// my name: Khôi
// my age: 23
```

### Thêm/sửa dữ liệu

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR'
}

//cú pháp 1: json['key']
json['name'] = 'Trần';
var myName = json['name'];
console.log('my name: ' + myName);

//cú pháp 2: json.key
json.age = '10';
var myAge = json.age;
console.log('my age: ' + myAge);


// my name: Trần
// my age: 10
```

### Xóa dữ liệu

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR'
}

delete json['age']
console.log(json);
// {name: "Khôi", gender: "MR"}


delete json.gender;
console.log(json);
// {name: "Khôi"}
```

### Chuyển JSON sang chuỗi

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR'
}

// dùng hàm JSON.stringify
JSON.stringify(json);


//"{"name":"Khôi","age":"23","gender":"MR"}"
```

### Chuyển chuỗi sang JSON

```javascript
var jsonString = '{"name":"Khôi","age":"23","gender":"MR"}';

//dùng hàm JSON.parse
var json = JSON.parse(jsonString);

console.log(json)

//{name: "Khôi", age: "23", gender: "MR"}
```

### Gán hàm\(function\) vào JSON

Hàm không được chấp nhận trong JSON, nhưng nếu cần chứa hàm hãy viết nó sang dạng String và parse lại hàm sau.

```javascript
var text = '{ "name":"John", "age":"function () {return 30;}", "city":"New York"}';
var obj = JSON.parse(text);
obj.age = eval("(" + obj.age + ")");
console.log(obj.name + ", " + obj.age());
//John, 30
```

> Hàm eval dùng để thực thi 1 đoạn code JS

Cú pháp:

```javascript
eval(statement)(parameter)
```

