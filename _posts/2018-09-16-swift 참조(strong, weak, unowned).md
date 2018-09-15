---
title: swift 참조(strong, weak, unowned)
date: 2018-09-15
tags: swift 참조, strong, weak, unowned 
category: swift
---

스위프트에서는 strong, weak, unowned으로 참조를 결정할 수 있다.

strong은 강한 참조이다. 
일반적을 한쪽 객체가 다른 객체를 참조한다면, 어느 한쪽의 객체가 메모리에서 해제될 때 다른 쪽도 자동으로 메모리에서 해제되어야 한다.
그러나 iOS는 ARC(Automatic Reference Counting, 자동 레퍼런스 카운팅)를 통해 객체 메모리 해제에 참조횟수(refrence count)를 이용한다.
다시 말해, 참조횟수가 0번이 된 객체를 운영체제가 메모리에서 해제한다.

`strong`
은 철저하게 참조횟수를 따른다. 
철저하게 운영체제가 참조횟수에 따라 메모리를 해제하도록 한다. 때문에 객체들이 순환참조 관계에 있다면 메모리를 해제하지 못한다. 즉, 메모리 누수가 발생한다.

반면 ```swift weak```와 ```swfit unowned```는 참조횟수를 준수하지 않는다. 따라서 운영체제는 무조건 메모리 해제를 수행하지만, ```swift weak```로 서언된 객체는 ```swift nil```로 참조주소가 초기화되지만, ```swift unowned```로 선언된 객체에는 참조주소가 그대로 남아있다.

순환참조 관계에서 strong이 메무리 누수를 발생시켜서 위험하다면, 
unowned는 nil이 허용되지 않는 탓에 잘못된 주소 접근으로 인한 fatal error를 발생시키기 때문에 위험하다.



## Reference

- https://outofbedlam.github.io/swift/2016/01/31/Swift-ARC-Closure-weakself/
