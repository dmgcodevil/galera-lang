# galera-lang
A simple programming language for those who don't give a f**k



# Galera Lang Specification


## Types

Type defintion:  `galera <Type_Name> {  <Name1>, <Name2>, ...  : <Type>  }`

Example:

```
galera Foo {} // empty class / map
galera Foo {a,b,c:int, atoi:(string)int}
```


Function type : `<Name> ([<Type>]) <Type>`

Example:

```
galera  atoi (string) int
```

  
  

Inheritance :  `<Type_Defintion> <Type1> <Type2> ... `

Example:

```
Bar {a:int}
Foo{b:int} Bar

foo = Foo{a:1, b:2}

```
  
