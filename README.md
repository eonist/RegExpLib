# **RegExpLib** 

<img width="100" alt="img" src="https://rawgit.com/stylekit/img/master/RegExpLib.svg">

- Makes parsing and modifying with RegEx easier  

```swift
"My name is Taylor Swift".match("My name is Taylor (.*)")//Swift
"yeah yeah".replace("(\\b\\w+\\b)", "bla")//bla bla
"hello world".test("o.*o")//true
/*RegExp Exec:*/
let str = "blue:0000FF green:00FF00 red:FF0000"
RegExp.matches(str, "(\\w+?)\\:([A-Z0-9]+?)(?: |$)").forEach {
    Swift.print("match.numberOfRanges: " + "\($0.numberOfRanges)")/*The first item is the entire match*/
    let content = (str as NSString).substringWithRange($0.rangeAtIndex(0))/*the entire match*/
    let name = $0.value(str, 1)/*capturing group 1*/
    let value = $0.value(str, 2)/*capturing group 2*/
}//Outputs: name: green, value: 00FF00...and so on
```
