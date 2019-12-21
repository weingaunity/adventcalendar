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


# Day 9 (2019-12-09) - HTTP Request using fetch()
[Show Story Image](./media2019/day09.jpeg)
```javascript
// ====================================
// Day 9 (2019-12-09) - HTTP Request
// using fetch() and promises
// ====================================
var url="https://raw.githubusercontent.com/"+
        "weingaunity/adventcalendar/master/"+
        "media2019/data.json";

fetch(url,{
  cache: "no-cache",
  mode: "cors"
})
.then(function (response) {
  // parse response to JSON
  // returns promise again
  return response.json();
}).then(function(json){
  // process JSON response
  console.log("I'm late because of async");
  console.log(json);
}).catch(function(e){
  // an error ocurred
});

console.log("I'm first");

// = Output ===========================
```

# Day 10 (2019-12-10) - HTTP Request with query parameters
[Show Story Image](./media2019/day10.jpeg)
```javascript
// ====================================
// Day 10 (2019-12-10) - HTTP Request
// with query parameters
// ====================================

//               .....?<Query String>
// http://test.org/api?a=123&b=asd&...
// use encodeURI to insert escape sequences
// for special characters
console.log("encodeURI-Result:");
console.log(encodeURI('"[Hello World&{}]"'));

var url="https://iot.makerspace-amstetten.at/"+
        "thing/adventcalender/echo";
        
data={a: 123, b:"adfer", c:[1,2,3]};
var query="value="+encodeURI(JSON.stringify(data));
console.log(url+"?"+query);

fetch(url+"?"+query,
  {cache: "no-cache", mode: "cors" }
).then(function (response) {
  return response.json();
}).then(function(json){
  // process JSON response
  console.log("Echo Response");
  console.log(json);
}).catch(function(e){
  // an error ocurred
});

console.log("Output");

// = Output ===========================
```

# Day 11 (2019-12-11) - HTTP Post-Request
[Show Story Image](./media2019/day11.jpeg)
```javascript
// =======================================
// Day 11 (2019-12-11) - HTTP Post-Request
// =======================================
var url="https://iot.makerspace-amstetten.at/"+
        "thing/adventcalender/echo";
data={a: 123, b:"adfer", c:[1,2,3]};

// encodeURI done by fetch
fetch(url,{
  method:"POST",
  cache: "no-cache",
  mode: "cors",
  // send data in message-body of request
  body:JSON.stringify(data)
}).then(function (response) {
  return response.json();
}).then(function(json){
  // process JSON response
  console.log("Echo Response");
  console.log(json);
}).catch(function(e){
  // an error ocurred
});

console.log("Output");

// = Output ===========================
```

# Day 12 (2019-12-12) - Create an Object
[Show Story Image](./media2019/day12.png)
```javascript
// =======================================
// Day 12 (2019-12-12) - Create an Object
// =======================================
var animal=function(type, name, sound)
{
  var age=0; // local/private variable

  var obj={};

  obj.sound=sound; // public variable
  obj.state=function(){
    // type and name can be used without
    // storing them separate in the object
    console.log(type+" "+name+" makes "+
    obj.sound+" and is "+age+" years old.");
  };
  obj.birthday=function(){
    age++; // change private variable
  };

  return obj; // return created object
}

var dog=animal("Dog","Snoopy","WauWau");
var cat=animal("Cat","Kitty","Miau");
dog.sound="Wauuuu Wauuuu";
dog.birthday();
dog.birthday();
dog.birthday();

cat.birthday();
cat.birthday();

dog.state();
cat.state();

// = Output ===========================
```

# Day 13 (2019-12-13) - Using class
[Show Story Image](./media2019/day13.png)
```javascript
// =======================================
// Day 13 (2019-12-13) - Using class
//   I prefer the version used in Day 12
// =======================================

class Animal{
  // #age=0 // new feature for private, not supported
            // up to now
  constructor(type, name, sound) {
    this._age=0;
    this.type=type;
    this.name=name;
    this.sound=sound;
  }
  
  birthday=function(){
    this._age++;
  }

  state=function()
  {
    console.log(this.type+" "+this.name+" makes "+
    this.sound+" and is "+this._age+" years old.");
  }

};

var dog=new Animal("Dog","Snoopy","WauWau");
var cat=new Animal("Cat","Kitty","Miau");
dog.sound="Wauuuu Wauuuu";
dog.birthday();
dog.birthday();
dog.birthday();

cat.birthday();
cat.birthday();

dog.state();
cat.state();

// = Output ===========================
```


# Day 14 (2019-12-14) - Getter and Setter Part 1
[Show Story Image](./media2019/day14.png)
```javascript
// =======================================
// Day 14 (2019-12-14) - Getter and Setter
// =======================================

var myObject=function()
{
  var localvariable=44; // initial value
  obj={
    get v(){
      console.log("Getter called");
      return localvariable;
    },
    set v(value) {
      console.log("Setter called");
      localvariable=value;
    }
  };
  return obj;
};

var o=myObject();

console.log(o.v);
o.v=123;
console.log(o.v);

// no chance to access localvariable
console.log(o.localvariable);

// = Output ===========================
```

# Day 15 (2019-12-15) - Getter and Setter Part 2
[Show Story Image](./media2019/day15.jpeg)
```javascript
// =======================================
// Day 15 (2019-12-15) - Getter and Setter
// Part 2
// =======================================

var myObject=function(name)
{
  var localvariable=0; // initial value
  obj={
    get [name](){
      console.log("Getter called");
      return localvariable;
    },
    set [name](value) {
      console.log("Setter called");
      localvariable=value;
    }
  };
  return obj;
};

var o=myObject("test");

console.log(o.test);
o.test=123;
console.log(o.test);

// = Output ===========================
```

# Day 16 (2019-12-16) - Checking for properties
[Show Story Image](./media2019/day16.jpeg)
```javascript
// ==================================
// Day 16 (2019-12-16) - Checking for
//                       properties
// ==================================

var obj={a:"asb",b:false,c:[]};

if (obj.a) console.log("Prop a exists");
  else console.log("Prop a does not exist");
// if property is boolean, this way to check
// will fail
if (obj.b) console.log("Prop b exists");
  else console.log("Prop b does not exist");

// hasOwnProperty will be more secure
if (obj.hasOwnProperty("b"))
  console.log("Prop b exists");
  else console.log("Prop b does not exist");

// if value or param does not exist, use a
// default value using || operator.
// Again: be aware of booleans here
var test=obj.d || {default: "object"};
console.log(test);

// = Output ===========================
```

# Day 17 (2019-12-17) - Operators Part 1
[Show Story Image](./media2019/day17.jpeg)
```javascript
// ======================================
// Day 17 (2019-12-17) - Operators Part 1
//   Spread Operator: ...
//   allows to expand array or string to
//   be expanded as arguments
// ======================================

var list=[1,5,3,2,1,5,6];

console.log(Math.max(1,5,3,2,1,5,6));
// Math.max(list); // this does not work
console.log(Math.max(...list));

var obj1={a:123, b:432, c:231};
var obj2={...obj1, d:222};
var list2=[...list,100,200];
console.log(obj2);
console.log(list2);

// = Output ===========================
```

# Day 18 (2019-12-18) - Operators Part 2
[Show Story Image 1](./media2019/day18-1.jpeg) [Show Story Image 2](./media2019/day18-2.jpeg)
```javascript
// ======================================
// Day 18 (2019-12-18) - Operators Part 2
//   Ternary conditional: a ? b : c
//   returns b, if condition a is true,
//   else it returns c
// ======================================

var fun=function(i)
{
  console.log("### i = "+i);
  a=((i===1)?(true):((i===true)?true:false));
  console.log("a = "+a);
  if (a) {
    console.log("a is true (IF way)");
  } else {
    console.log("a is false (IF way)");
  }
  console.log("a is "+(a?"true":"false")+"(? way)");
  var b=(a==false)?53:"df";
  console.log("b="+b);
}

fun(false);
fun(true);
fun(1);
fun(0.5);

// = Output ===========================
```

# Day 19 (2019-12-19) - Operators Part 3
[Show Story Image](./media2019/day19.jpeg)
```javascript
// ======================================
// Day 19 (2019-12-19) - Operators Part 3
//   "=" vs "==" vs "==="
// ======================================

// Assignment "=" that will return the
// assigned value.
console.log("'=' Examples");
var a=b=3;
var c=(d=4)+3;
console.log([a,b,c,d]);

// Abstract comparison "==" converts the operands
// to the same type before compare them
console.log("'==' Examples");
console.log([ 5=="5" , true==1   ,  true==0  ]);
console.log([ 5=="6" ,  "6"=='6' , false==-1 ]);
console.log([ 0==[]  ,    0=={}  ,    []=={} ]);
console.log([ null == undefined ]);

// Strict comparison "===" compares type and content
console.log("'===' Examples");
console.log([ 5==="5" , true === 1 ]);
console.log([ 0===[]  , null === undefined ]);
console.log([ null === null  , undefined===undefined ]);

// = Output ===========================
```

# Day 20 (2019-12-20) - Operators Part 4
[Show Story Image](./media2019/day20.png)
```javascript
// ======================================
// Day 20 (2019-12-20) - Operators Part 4
//   Rest operator "..."
// ======================================

var fun=function(first,second,...rest)
{
  console.log("~~~~~~~~~~~~~~~~~~~");
  console.log(first);
  console.log(second);
  console.log("Rest-Length: "+rest.length);
  console.log(rest);
}

fun(1,5,"Hallo",43,{a:2,b:3});
fun("A",[1,2,3]);

// = Output ===========================
```

# Day 21 (2019-12-21) - Operators Part 5
[Show Story Image](./media2019/day21.png)
```javascript
// ======================================
// Day 21 (2019-12-21) - Operators Part 5
//   typeof operand
//   typeof (operand)
// returns a string of the operand
// ======================================

var lst=[undefined,
         null,
         true,
         1.34,
         900719923412340991n,
         "abcd",
         [1,2,3],
         function(){return 1;},
         {a:3, b:32} ];

for(var i=0;i<lst.length;i++)
{
  console.log(typeof lst[i])
}
// = Output ===========================
```

# Day 22 (2019-12-22)
# Day 23 (2019-12-23)
# Day 24 (2019-12-24)
