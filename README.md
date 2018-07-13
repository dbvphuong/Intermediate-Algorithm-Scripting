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
