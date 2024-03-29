---
title: 소프트웨어 형상관리(Software Configuration Management, SCM)
date: 2022-01-04
tags: github 
category:
---

**소프트웨어 형상관리(Software Configuration Management, SCM)**란?

코딩할 때 유용한 기능 중 하나는 이전에 작성했던 코드를 되돌리는 UNDO일 것이다.
근데 UNDO는 텍스트를 쌓아놓는 스택(stack) 공간이 제한되기 때문에 간혹 이전으로 되돌리지 못해 낭패를 겪는 경우가 왕왕 있다.
이런 상황을 개인적으로는 ㅈ됨...이 아니라 '버전 소멸'라고 하는데, SCM은 버전 소멸을 막기 위한 유용한 수단이다.
원격지에 이전 코드가 항상 보존되어 있으므로, 스택의 제한 때문에 코드를 되돌리지 못하더라도 원격지에서 다시 받거나 버전을 되돌리면 그만이다.
개인적으로는 버전 소멸을 막기 위한 용도로 주로 이용하지만, SCM의 대표적인 또 다른 장점은 소스 공유이다.
멋모르고 코딩했던 학생 때는 USB나 메신저, 이메일 등으로 소스를 공유했었지만, 이게 얼마나 비효율적이었는지 취직하고 나서는 땅을 치며(?) 후회했다.
아무튼 SCM은 소프트웨어를 개발하고 유지관리 할 때 발생하는 소스 코드나 각종 문서들의 변경을 효과적으로 관리할 수 있다.

SCM은 중앙 집중식 혹은 분산하여 버전을 관리할 수 있다. 
중앙 집중식은 중앙 서버에 모든 파일들을 모아놓고, 여기에 모든 클라이언트가 접근하여 파일을 수정한다.
SVN이 대표적인 중앙 집중식 버전 관리 시스템이고 Git이 분산 버전 관리 시스템이라고 하는데,
구조적 차이로 인해 두 시스템 간의 사용 방법에 차이점이 있다.
SVN은 커밋(commit) 한 방에 원격지에 소스코드가 바로 반영되어 버리는 반면,
Git은 먼저 원격지에 수정된 파일을 받고(pull), 충돌(conflict) 파일의 합병(merge) 후에 커밋할 수 있고, 원격지에 반영하기 위해서는 별도로 업로드(push)를 해줘야 한다.

SVN을 이용할 당시에 충돌 중재를 위해 사수와 마찰이 일어났던 적이 많았던 경험이 있으므로, 개인적으로는 충돌을 미연에 방지할 수 있는 Git을 더 선호한다.
물론 그렇다고 Git을 이용한다고 충돌을 원천적으로 방지할 수 있는 건 아니다.
수정한 소스코드를 push해야 하는데, 내가 수정한 소스 코드 때문에 pull 단계에서부터 진행이 안 되는 경우가 꽤 많기 때문이다.

