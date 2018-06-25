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
