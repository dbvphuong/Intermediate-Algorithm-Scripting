# Intermediate-Algorithm-Scripting  
# Sum All Numbers in a Range  
```
function sumAll(arr) {
  var a = 0;
var x= arr[0];
var y= arr[1];
  if (x > y) {
    for(var i=y; i <= x; i++){
  a += i;}}
  else if (x < y) {
    for(var i=x; i <= y; i++){
  a += i;}}
  return a;
}
sumAll([1, 4]);
```
# Missing letters  
```
function fearNotLetter(str) {
var text = "";
var all = "abcdefghijklmnopqrstuvwxyz";
var arr = all.split("");
var arr1 = str.split("");
var a = arr.indexOf(arr1[0]);
var b = arr.indexOf(arr1[arr1.length - 1]);
var arr3 = arr.slice(a, b+1);
for(let i = 0; i< arr3.length; i++){
    if(arr1.indexOf(arr3[i]) == -1 ){
      text = arr3[i];
      break;
    }
    else{text =  undefined}
  
}
  return text;
}

fearNotLetter("abce");
```

# Search and Replace  
```
function myReplace(...arr) {
var x = "";
if(arr[1].charAt(0) === arr[1].charAt(0).toUpperCase()){
  x = arr[2].charAt(0).toUpperCase() + arr[2].slice(1)
}
else{ x = arr[2]
}

var a = arr[0].replace(arr[1],x);
  return a;
}
myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```
# Convert HTML Entities  
```
function convertHTML(str) {
var str1 = str.replace(/&/g,"&​amp;");
var str2 = str1.replace(/</g,"&lt;");
var str3 = str2.replace(/>/g,"&gt;");
var str4 = str3.replace(/"/g,"&quot;");
var str5 = str4.replace(/'/g,"&apos;");
  return str5;
}

convertHTML("Dolce & Gabbana");
```
# Sum All Odd Fibonacci Numbers  
```
function sumFibs(num) {
  var arr = [1,1];
    for (let i = 2; i < num; i++){
        arr[i] = arr[i-1] + arr[i-2];
        arr.push(arr[i]);
    } // số thứ i bằng số trước nó cộng với số trước trước nó rồi thêm số đó vào arr
    arr.pop();
    arr = arr.filter(x => x <= num && x%2 != 0);
    var sum = arr.reduce ((a,b) => a+b);
    return sum;
  }
  
sumFibs(4);
```
#  Sum All Primes  
```
function sumPrimes(num) {
    function test(n) {
        for (let i = 2; i < n; i++){
            if (n%i === 0) return false;
        }
        return true;
    }

    var arr = [2];
    for (let i = 3; i <= num; i+=2){
        if (test(i) === true) arr.push(i);
    }
    var sum = arr.reduce((a,b) => a+b);
    return sum;
  }

sumPrimes(10);
```
# Smallest Common Multiple  
```
function smallestCommons(arr) {
    var max = Math.max(...arr);
    var min = Math.min(...arr);

    var arr1 = [];
    for (let i = min; i <= max; i++){
        arr1.push(i);
    }

    function BCNN(x,y){
        var TICH = x*y;
        while (x != y) {
            if(x>y){
                x = x-y;
            }
            else y = y-x;
        }
        return TICH/x;
    }

    for (let i = 1; i < arr1.length; i++){
        [arr1[i-1], arr1[i]] = [BCNN(arr1[i-1], arr1[i]), BCNN(arr1[i-1], arr1[i])];
    }

    return arr1[arr1.length -1];
  }
  
console.log(smallestCommons([1,100]));
```
# Drop it  
```
function dropElements(arr, func) {
  var arr1 = arr.filter(func);
  var arr2 = [];
  for (let i = 0; i < arr.length; i++){
    if(arr[i] === arr1[0]){
      arr2 = arr.slice(i);
      break;
    }
  }

  return arr2;
}

dropElements([1, 2, 3], function(n) {return n < 3; });
```
# Binary Agents  
```
function binaryAgent(str) {
    var arr = str.split(" ");
    var arr1 = [];
    for (let i = 0; i < arr.length; i++){
        arr1.push(arr[i][0]*Math.pow(2,7) + arr[i][1]*Math.pow(2,6) + arr[i][2]*Math.pow(2,5) + arr[i][3]*Math.pow(2,4) + arr[i][4]*Math.pow(2,3) + arr[i][5]*Math.pow(2,2) + arr[i][6]*Math.pow(2,1) + arr[i][7]*Math.pow(2,0))
    }
    return String.fromCharCode(...arr1); // công thức chuyển số thường thành chữ
  }
  
console.log(binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111"));
```
Cách làm:  
-xét phần tử đầu của arr: số đầu * 2^7 + số thứ 2 * 2^6...= a.  
-String.fromCharCode(a); dùng để chuyển số thành chữ.  

# Everything Be True  
```
function truthCheck(collection, pre) {
    var a;
    for (let i = 0; i < collection.length; i++){
        if (Boolean(collection[i][pre]) === false){
            return false;
        }
    }
    return true;
}

console.log(truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex"));
```
Lưu ý: duyệt object là string dùng object[] chứ không đc dùng object.  
