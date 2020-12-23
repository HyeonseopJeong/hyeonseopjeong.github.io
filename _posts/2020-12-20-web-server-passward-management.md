---
layout: post
title: 웹 서버의 패스워드 관리 법
description: Hash, Salting
tags: [웹 서버]
author: Hyeonseop Jeong
comments : True
---

# 웹 서버가 유저의 비밀번호를 관리하는 방식
- 서버가 db에 유저의 비밀번호를 그냥 쑤셔 넣으면 당연히 문제가 생길 것이다.
- 서버 db를 해킹당하면 유저의 비밀번호가 다 털리게 된다. 근데 그 전에 db관리자가 유저의 패스워드를 그냥 열어 볼 수도 있다. 

- 그래서 서버는 유저의 비밀번호를 `해시`해서 저장한다.
해시는 해시 함수를 이용해서 값을 단방향으로 암호화 시켜준다. (단방향이라는 말은 복호화가 안된다는 뜻이다.)

- 근데 이 해시를 그냥 사용하면 두 유저가 비밀번호가 같으면 digest(해시 함수로 나온 값)도 같아서 비밀번호가 유추 가능해진다.

- 그래서 사용자의 패스워드에다가 임의의 값을 붙여서 Hash funtion에 넣는 방식인 `Salting`을 이용해 두 유저의 비밀번호가 같더라도 나오는 digest가 다르게 하고 또한 db가 털려서 유저들의 비밀번호 digest가 털려도 rainbow attack 등을 할 수 없게 된다. 

> rainbow attack은 rainbow table에 해킹해온 유저의 digest를 대입해서 passward를 알아내는 방식이다.

> salt는 최소 128bit 정도는 돼야 안전하다고 한다.

- 이 정도 (hash + salting)하면 웹 서버에서 비밀번호를 안전하게 저장하고 있다고 말할 수 있다.


## 결론
그냥 구글, 카카오, 네이버의 로그인 API를 달자.
