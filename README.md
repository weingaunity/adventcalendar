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



# Day 3 (2019-12-03)
# Day 4 (2019-12-04)
# Day 5 (2019-12-05)
# Day 6 (2019-12-06)
# Day 7 (2019-12-07)
# Day 8 (2019-12-08)
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
