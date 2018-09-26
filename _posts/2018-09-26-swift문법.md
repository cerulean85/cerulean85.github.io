---
title: Github Blog 첫글!!
date: 2018-01-02
tags: github 
category: github
---

Github 블로그를 만들고 처음으 글을 써본다.

```swift
class HTMLElement {
    let name: String
    let text: String?
    
    lazy var asHTML: Void -> String = {
        [unowned self] in
        if let text = self.text {
            return "<\(self.name)>\(text)</\(self.name)>"
        } else {
            return "<\(self.name) />"
        }
    }
    
    init(name: String, text: String? = nil) {
        self.name = name
        self.text = text
    }
    
    deinit {
        print("\(name) is being deinitialized")
    }
}
```

우와!! 좋구만

## Reference

- https://junhobaik.github.io/jekyll-apply-theme/
