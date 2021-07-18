# Powershell

### **Find and get help:**
```Get-Command –Name * keyword *``` 
> finds commands with keywords

```Get-Service -Displayname "*keyword*" ``` 
> finds services with keywords

```Get-help keyword ``` 
> finds commands with said keyword

``` Get-Command -Verb <verb> -Noun <noun> ``` 
>search with a verb and a noun

```help <cmdlet> -ShowWindow -Examples```
> gives a manual of wanted command with 2 possible options

### **Formatting and output manipulation**
```Format-Table```
> formatting

```Select-Object x,y,z```
> Gets only the specified properties of objects

```Where-Object {$_.<property> <operator> <value>}```
> Gets properties that have a set value

```Where-Object {-not $_.<property> -notlike '<value>'}```
> Exclude objects based on filters. 

### **Miscellaneous:**
``` $PSItem OR $_```
> contains the current object of the pipeline

```-WhatIf ```
> gives a demonstration of what would happen


