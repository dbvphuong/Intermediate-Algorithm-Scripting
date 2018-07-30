```
function translatePigLatin(str) {
  var text;
  var arr = str.split("");
  var arr1=["a","e","o","i","u"];// nguyen am
  if(arr1.indexOf(arr[0]) != -1){
    text = str.concat("way");
    return text;
  }
  for (let i = 1; i < arr.length; i++){
    if (arr1.indexOf(arr[i]) !== -1){
      var a = arr.splice(0,i).join("");
      arr.push(a,"ay");
      console.log(arr);
      text = arr.join("");
      return text;
    }
  }
  if(text == undefined){
    text = str + "ay";
  }

  return text;
  }
  
  console.log(translatePigLatin("clkp"));
```
