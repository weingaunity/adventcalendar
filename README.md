# Instagram Adventcalendar - Stories 2019
A quick JavaScript introduction in 24 days
created by DI Klaus Weichinger  snaky.1@gmx.at  

License: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

Each day the new lines of code are inserted here. Maybe in worst case 1-2 days delayed.


# Day 0 (2019-11-30) - Short Introduction
[Show Story Image](./media2019/day00.png)
- Git-Repository of the code snippets:
  [https://github.com/weingaunity/adventcalendar](https://github.com/weingaunity/adventcalendar)

- Required: A browser Firefox or Chrome
- Press F12 and switch to the console


# Day 1 (2019-12-01) - Variables, Datatypes, Console Output
[Show Story Image](./media2019/day01.png)

```javascript
// Day 1 (2019-12-01)
// Variables, Datatypes, Console Output

var width=10; // New line with Shift+Enter
var height=4;
var area=width*height;
console.log("Area = "+area);

var calc=width+" * "+height+" = "+area;
console.log(calc);

var x=43.23;      // Number
x=true;           // Boolean (true, false)
x="Tür 1";        // String (Text)
x=[1,2,3,"abc"];  // Arrays (Listen)
x={a: 4, b:3.2,   // Object
   instagram: " @__wg__",
   c:{x:1, y:true}
  };
console.log(x);

x=function(a,b){return a+b;};
console.log("Function call result="
 + x(4,12));
alert("Finished :-)");
```

# Day 2 (2019-12-02) - IF / WHILE / FOR
[Show Story Image](./media2019/day02.png)

```javascript
// =====================================
// Day 2 (2019-12-02) - IF / WHILE / FOR
// =====================================

for(var i=0;i<=10;i++) // just looping
{
  if ((i % 5)==0)
  {
    console.log(i +" is a multiple of 5");
  }
  else
  {
    // if ... else ... else if ....
  }
}

var data=[4,5,3];
// iterate over content of array
for(var e of data) console.log(e);
// iterate over properties of array/object
for(var e in data)
  console.log("data["+e+"]="+data[e]);
for(var e in {a:1,hallo:43,df:32}) console.log(e);

var i=0;
while(i<3)
{
  i++;
  console.log(i)
}
```

# Day 3 (2019-12-03) - Functions
[Show Story Image](./media2019/day03.jpeg)
```javascript
// ==============================
// Day 3 (2019-12-03) - Functions
// ==============================
function myFun1(a,b)
{
  return a+b;
}

var myFun2=function(a,b)
{ // anonymous function
  // assigned to variable
  return a*b;
};

var myFun3=(a,b=2)=>{
  // arrow function with default
  // parameter value for b
  return a/b;
};

console.log(myFun1(5,3));
console.log(myFun2(5,3));
console.log(myFun3(5));

var funarray=[ // Array of functions
  function(){ return "Advent"; },
  function(){ return "Calendar"; },
  function(){ return "2019"; }
];
// Add a function to the array
funarray.push( ()=>"@__wg__");

// Call all functions in the array
for(var fn of funarray)
  console.log(fn());
```


# Day 4 (2019-12-04) - Lists
[Show Story Image](./media2019/day04.jpeg)
```javascript
// ====================================
// Day 4 (2019-12-04) - Lists
// ====================================

var lst=[3,2,10,1,5];
lst.push(7); // append at end
lst.unshift(-1); // append at begin
console.log(lst);

// remove first element and plot it
console.log(lst.shift());

// apply a function (or arrow function
// to each element) and return the
// result as new list
lst2=lst.map(
  (x)=>{console.log(x); return x*x;}
);
console.log(lst2);

// filter elements. Function returns
// true if element is valid. Else false
lst3=lst.filter((x)=>((x%5)==0));
console.log(lst3);

// sorting. Comparison function
// can be passed too
console.log(lst.sort())
```


# Day 5 (2019-12-05) - Objects
[Show Story Image](./media2019/day05.jpeg)
```javascript
// ====================================
// Day 5 (2019-12-05) - Objects
// ====================================
var o={
  a: 123,
  b:"asd",
  test:[1,2,3],
  fun:function(){console.log("Hello")}
};
if (o.hasOwnProperty("foo")==false)
{
  console.log("foo does not exists");
}
o.foo=444;
if (o.hasOwnProperty("foo"))
{
  console.log("foo does now exists");
}

// different ways to access members
o.fun(); // call the member function
console.log(o.foo);
console.log(o["foo"]);
var n="foo";
console.log(o[n]);
```

# Day 6 (2019-12-06) - Cyclic Tasks
[Show Story Image](./media2019/day06.png)

Source code highlighted with [https://carbon.now.sh](https://carbon.now.sh)

```javascript
// ====================================
// Day 6 (2019-12-06) - Cyclic Tasks
// ====================================
var counter=0;
var task1=function(){
  counter++;
  console.log("Task 1 ("+counter+")");
  setTimeout(task1,1000); // run in 1000ms
}

var task2=function(){
  counter++;
  console.log("Task 2 ("+counter+")");
  setTimeout(task2,300); // run in 300ms
}

task1(); // start task 1
task2(); // start task 2

// Hint: have a look to setInterval() too
```

# Day 7 (2019-12-07) - JSON Part 1/2
[Show Story Image](./media2019/day07.jpeg)

```javascript
// ====================================
// Day 7 (2019-12-07) - JSON Part 1/2
// JavaScript Object Notation
// ====================================

var wg={
  instagram: "@__wg__",
  followers: 258,
  hashtags:["#profweichinger","#wgproj"]
};

// convert object to JSON string
var s=JSON.stringify(wg);
console.log(s);
// s can be transmitted or stored to file or database
//   Hint: JSON string is valid JavaScript!
//   Do not use eval(...) to convert JSON to object
//   due to security issues (code injection)!
// r is received or read from file or database
var r=s;
// convert JSON string back to object
var instagramuser=JSON.parse(r);
console.log("Instagram: "+instagramuser.instagram);
```

# Day 8 (2019-12-08) - JSON Part 2/2
[Show Story Image](./media2019/day08.jpeg)
```javascript
// ====================================
// Day 8 (2019-12-08) - JSON Part 2/2
// JavaScript Object Notation
// ====================================

// JSON is valid JavaScript!
// Object created with JSON syntax
var wg={"instagram":"@__wg__","followers":258,
"hashtags":["#profweichinger","#wgproj"]};

wg.meta={bool: false, number: NaN, obj:null,
unixtime:Date.now(), date:new Date()};
// Date.now() returns milliseconds
// since 1.1.1917 00:00

var prittystring=JSON.stringify(wg, null, 2); 
console.log(prittystring);
```


# Day 9 (2019-12-09)
# Day 10 (2019-12-10)
# Day 11 (2019-12-11)
# Day 12 (2019-12-12)
# Day 13 (2019-12-13)
# Day 14 (2019-12-14)
# Day 15 (2019-12-15)
# Day 16 (2019-12-16)
# Day 17 (2019-12-17)
# Day 18 (2019-12-18)
# Day 19 (2019-12-19)
# Day 20 (2019-12-20)
# Day 21 (2019-12-21)
# Day 22 (2019-12-22)
# Day 23 (2019-12-23)
# Day 24 (2019-12-24)
