# Loops & BinaryGap
![jsHW](https://user-images.githubusercontent.com/80118008/142408257-30804650-3a60-450c-b0b2-9dfa0b0a000c.gif)


## Get All Prime Numbers from 0 to x
● **script.js:**
```
 function getAnswer(x)
 {
    if(x !== parseInt(x)) {return 'numbers only'}    
    
    var number = [];
    
     var prime = [];
     
 for (i =2; i <= x; ++i)
 {

   if(!number [i])   
   { 
       prime.push(i);
       
       for (j = i << 1; j <= x; j += i)
       {number[j] = true;}                                 
   }  
   
 }
 return prime;
 }
```

● **index.html:**
```
var x = prompt('Enter a number and get all prime numbers in range');
alert(getAnswer(parseInt(x)));
```

## Are We There Yet ?
> In this exercise I need to display the message 'Are we there yet ?' until user input is yes or yeah.

● **script.js:**
```
function thereYet(y)
{
    if (y === 'yes' || y === 'yeah')  // if input is yes or yeah alert yayy
    {
    alert('yayy'); 
    }
    else       //if not return 'are we there yet ?' until input is yes/yeah
    { 
        while(true)
        {
        var j =   prompt('are we there yet ?');  

         if (j === "yes" || j === 'yeah')
         {
             alert('yayy');
             break;
         }  
         
        }   
    }
}
```

● **index.html:**
```
var y = prompt('Are we there yet ?');
thereYet(y);
```

## Get The Longest Binary Gap of a Certain Value
> In this exercise I need to find the longest binary gap of a given number,
> 
> Finding the binary gap meaning I need to find the most zero values between two 1's and return the longest binary gap of a certain value.
> 
> For example, 1041 in binary is 10000010001. the "gap" is the zero values between the two 1's. count the longest "gap" between the 1's and its 5.
> 

● **script.js:**
```
function binGap(num)
{
    if(num !== parseInt(num)) {return 'numbers only'}
  
    const binNum = num.toString(2);      // toString(2) converts the number to binary format, when used on a number return the binary equivalent of the numeric value.
  
    const array = binNum.split('1').map((binGap, index, binArr) => { // split the binary string we obtained using 1 creating an array of empty strings.iterate through                                                                      //the array with .map() and subject each item to a condition.
    
   return binArr[index + 1] != undefined ? binGap.length : 0; }); //return length of empty string or zeros if the value at the next index (index + 1) within the array                                                                   //is not undefined. if the value of the next index is undefined return 0.
     
    return Math.max.apply(Math, array);    // return the number of the longest binary gap. as if user input was 1040 the longest binary gap in 1040 is 5, so return 5.
  }
```

● **index.html:**
```
var z = prompt('Enter a number and get its binary gap');
alert(binGap(parseInt(z)));
```
