---
title: SwiftUI Floating Button
date: 2024-01-12 17:21:20
tags:
---

### SwiftUI でフローティングボタンを実装する

```swift
import SwiftUI

struct FloatingButton: View {
    var systemName: String
    var action: () -> Void
    
    var body: some View {
        VStack {
            Spacer()
            HStack {
                Spacer()
                Button {
                    action()
                } label: {
                    Image(systemName: systemName)
                        .foregroundColor(.white)
                        .font(.system(size: 24))
                }
                .frame(width: 60, height: 60)
                .background(.blue)
                .cornerRadius(30.0)
                .shadow(color: .gray, radius: 3, x: 3, y: 3)
                .padding(EdgeInsets(top: 0, leading: 0, bottom: 16.0, trailing: 16.0))
            }
        }
    }
}

```
