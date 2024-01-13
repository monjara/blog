---
title: SwiftUIでmultilineなTextFieldを作成する
date: 2024-01-13 10:58:25
tags:
---

### .lineLimit(_ limit: Int, reserveSpace: Bool)を利用する

[ドキュメント](https://developer.apple.com/documentation/swiftui/view/linelimit(_:reservesspace:))

例ではTextFieldの高さが20行分固定で表示される

```swift
struct Input: View {
    @State var text: String = ""
    var body: some View {
        TextField("", text: $text, axis: .vertical)
            .textFieldStyle(.roundedBorder)
            .lineLimit(20, reservesSpace: true)
            .padding()
    }
}
```


### .lineLimit(_ limit: ClosedRange<Int>)を利用する

[ドキュメント](https://developer.apple.com/documentation/swiftui/view/linelimit(_:)-4hzfa)

例ではTextFieldの高さが初期表示で3行、3行を超える高さの文字が入力されると10行までスケールされる

```swift
struct Input: View {
    @State var text: String = ""
    var body: some View {
        TextField("", text: $text, axis: .vertical)
            .textFieldStyle(.roundedBorder)
            .lineLimit(3...10)
            .padding()
    }
}
```

### .lineLimit(_ limit: PartialRangeFrom<Int>)を利用する

[ドキュメント](https://developer.apple.com/documentation/swiftui/view/linelimit(_:)-251ko)

例ではTextFieldの高さが初期表示で3行、3行を超える高さの文字が入力されると入力された高さに合わせてスケールされる

```swift
struct Input: View {
    @State var text: String = ""
    var body: some View {
        TextField("", text: $text, axis: .vertical)
            .textFieldStyle(.roundedBorder)
            .lineLimit(3...)
            .padding()
    }
}
```


### .lineLimit(_ limit: PartialRangeThrough<Int>)を利用する

[ドキュメント](https://developer.apple.com/documentation/swiftui/view/linelimit(_:)-251ko)

例ではTextFieldの高さが初期表示で1行、文字が入力されると3行分の高さまで入力された高さに合わせてスケールされる

```swift
struct Input: View {
    @State var text: String = ""
    var body: some View {
        TextField("", text: $text, axis: .vertical)
            .textFieldStyle(.roundedBorder)
            .lineLimit(...3)
            .padding()
    }
}
```

