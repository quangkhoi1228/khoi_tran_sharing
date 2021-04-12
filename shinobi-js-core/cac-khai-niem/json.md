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

### Lấy dữ liệu

```javascript
var json = {
  name: 'Khôi',
  age: '23',
  gender: 'MR'
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

### Gán dữ liệu

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



















