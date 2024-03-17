---
title: SwiftUI 画面が表示されてからn秒後に処理を実行
date: 2024-03-17 15:20:40
tags:
---

### コード


```swift
  View{}
    .onAppear {
      Timer.scheduledTimer(withTimeInterval: 1.0, repeats: false) { _ in
          // some code
      }
    }
```

