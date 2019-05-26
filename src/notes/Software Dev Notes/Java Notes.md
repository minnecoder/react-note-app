## For loop

```java
for(int i = 0; i <10; i++)
{
	...code...
}
```

shorthand version
for(...data type... ...variable name... : ...array name...)
for(char c: charArray)

```java
Date today = new Date();
```
* will display the current date and time  
sets the calendar to the given (year,month,day,hh,mm,ss)
```
Calendar cal = Calendar.getInstance();
cal.set(2017,9,9,17,15,0)
```


## While loop
```
while(...condition...)
{

}
```
`Thread.sleep(1000)` --makes the program wait(in milliseconds(1000 ms = 1 sec)) 

`char[] charArray = new char[5];` -  creates a new array that has 5 elements named charArray  
`charArray[0] = "H"` - sets the first element of the array to H
can use .length in a for loop when using arrays

## Array List
```
List<...data type...> ...arrayName... = new ArrayList<....data type...>();
```


```
List<String> arrayList = new ArrayList();
arrayList.add("H");
arrayList.add("E");
arrayList.add("L");
arrayList.add("L");
arrayList.add("O");
```


`arrayList.remove(5);` -- uses the index to remove the item
* can't use a primitive data type within an array list
integerArrayList.get(0); --gets the data in the first index of an array list

## Map
```
Map<String, List<String>> makeModel = new HashMap<String, List<String>>();
```

```
List<String> hondaList = new ArrayList<String>();
hondaList.add("Civic");
hondaList.add("Prelude");
```
```
makeModel.put("Honda", hondaList);
System.out.println(makeModel.get("Honda");
```
`boolean userValid = isValidUser("tpage");` -- stores the returned value of the method to the userValid variable 