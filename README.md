# galera-lang
A simple programming language for those who don't give a f**k



# Galera Lang Specification


## Types

**Type defintion** :  `galera <Type_Name> {  <Name1>, <Name2>, ...  : <Type>  }`

Example:

```
galera Foo {} // empty class / map / or whatever you want
galera Foo {a,b,c:int, atoi:(string) -> int}
```

*Initialization* : `<Type> { <field>:<val>, ... } `

```
Foo {a:15, c:1}
```
_a_ is set to 15, _c- set to 1, _b_ remained initizlied and value equals to zero



**Function type** : `<Name> ([<Type>]) -> <Type>`

Example:

```
galera  atoi (string) -> int
```

  
  

Inheritance :  `<Type_Defintion> <Type1> <Type2> ... `

Example:

```
Bar {a:int}
Foo Bar {b:int}

foo = Foo{a:1, b:2}

```
  
**Namespaces** : `<Name_Space1> { <Name_Space2> { <Type> } }`

Example:

```
galera App {
  Foo {
    Bar {
      a: int
    }
  }
}

bar = App.Foo.Bar{a:1}
```

## Flow control

Should be obvious; no need to explain.

**Branch** : `(cond) ? { when true } : { else }`

Example: 

```
( a < b ) ? { a + 1 } : { b - 1 }
```

**Loop** : `(cond) :: {}`

```
i:int = 0
(i < 10) :: {
  i++
}
```

**Foreach** : `(val : arr[]) :: {} `

```
arr:int[] = { 1, 2, 3, 4, 5 }
(i : arr) :: { print(i) }
```
