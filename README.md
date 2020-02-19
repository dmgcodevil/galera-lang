# galera-lang
A simple programming language for those who don't give a f**k



# The Galera Programming Language Specification

## Packages


Each Galera source file must have `galera` extension and package. The package must be defined at the top of the source file. Package might be documented using `/* */` comment style.


```
PackageClause  = "package" PackageName .
PackageName    = identifier .
```

Example:

```
package 'foo'
```

```
/*
This package contains tools for network programming.
*/
package 'net'
```




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
_a_ is set to 15, _c_ set to 1, _b_ remained uninitialized and value equals to zero



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

## Comments
Comments serve as program documentation. There are two forms:

1. Line comments start with the character sequence // and stop at the end of the line.
2. General comments start with the character sequence /* and stop with the first subsequent character sequence */.
