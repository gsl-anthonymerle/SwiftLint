https://swift-ast-explorer.com/

```swift
enum Suit {
  case spades
  case hearts
}

let enm = Suit.spades

let value = switch enm {
  case spades: 1
  case hearts: 2
}

func foo() -> String {
  switch enm {
    case spades: "hello"
    case hearts: "world"
  }
}

var bar: String {
  switch enm {
    case spades: "hello"
    case hearts: "world"
  }
}

var toto: String {
  switch enm {
    case spades: print("hello")
    case hearts: print("world")
  }
}
```

Pour switch dans une computed var ou function:
- switch is in _CodeBlockItem_ -> _CodeBlockItemList_ and is the only block item (see *index1*)
- switch case is on single line
- switch case -> CodeBlockItem is not _FunctionCallExpr_
- Regarding last point


*index1*
AccessorBlock -> {
  -> CodeBlockItemList
    -> CodeBlockItem
      -> ExpressionStmt
        (SwitchExpr)
