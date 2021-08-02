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

```Where <property> -like '<value>' ```
> Gets properties that are like described

```–Filter "<property> LIKE '<value>%'" ```
> Can be used instead of Where-Object directly after the command without pipeline

``` select @{N=’ComputerName’; E={$_.PSComputerName}} ```
> Renames the name of a property to any string

### **Remote connection**
```$s = New-CimSession -ComputerName <computername>```
> Starts a new persistent CIM session to a remote computer.

```Get-WmiObject –namespace root\cimv2 –list | Where Name –like '*keywordhere*' | Sort Name```
> Finds repository classes

``` Invoke-CimMethod -class <repositoryclass> -methodname <method> ```
> Invokes a CIM method

```Enter-PSSession -ComputerName <computername> ```
```Invoke-Command –ComputerName name1,name2 –ScriptBlock { command }```
> Enables a one-to-one remote connection similiar to SSH session. Used like in the example above.

### **Scripting**
```[type(int,string)]$varname = value```
> Creates a variable with a value. Can be assigned a type if wanted.

```$varname = @(value1,value2,value3)```
> Creates an array

```foreach ($<item> in $<collection>) {statement list}```
> Loops through a collection. Array is a collection for example. $item is the name you give to the current item.

### **Miscellaneous:**
``` $PSItem OR $_```
> Contains the current object of the pipeline

```-WhatIf ```
> Gives a demonstration of what would happen

``` '' and "" ```
> Single quotes are literal and wont be processed even if a cmdlet or $ is inside. Double quotes allow processing

``` Get-Random ```
> Gets random numbers. more info https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1 OR Help Get-Random

``` [char]<number> ```
> Makes a number into a letter. Does not accept pipeline input.
