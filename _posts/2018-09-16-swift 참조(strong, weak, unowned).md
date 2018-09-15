---
title: swift 참조(strong, weak, unowned)
date: 2018-09-15
tags: swift 참조, strong, weak, unowned 
category: swift
---

iOS는 ARC(Automatic Reference Counting, 자동 레퍼런스 카운팅)를 통해 객체 메모리 해제에 참조횟수(refrence count)를 이용한다.
즉, 운영체제는 참조횟수가 0번이 된 객체를 메모리에서 해제한다.

`strong`은 철저하게 참조횟수를 준수한다.
그러나 순환참조 관계에 있는 객체들은 참조횟수가 0이 될 수 없기 때문에 운영체제는 이들을 메모리에서 해제하지 못하여 메모리 누수가 발생한다.

반면 `weak`와 `unowned`는 참조횟수를 준수하지 않는다. 운영체제는 무조건 메모리 해제를 수행하지만, 
`weak`로 선언된 객체는 `swift nil`로 참조주소가 초기화되지만, `unowned`로 선언된 객체에는 참조주소가 그대로 남는다.

`strong`이 순환참조 관계에서 메무리 누수를 발생시켜서 위험하다면, 
`unowned`는 `nil`이 허용되지 않아 잘못된 주소 접근으로 `fatal error`를 발생시키므로 위험하다.



## Reference

- https://outofbedlam.github.io/swift/2016/01/31/Swift-ARC-Closure-weakself/
