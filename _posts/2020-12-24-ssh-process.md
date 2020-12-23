---
layout: post
title: ssh의 작동과정
description: 비대칭키를 이용한 ssh 작동과정
tags: [용어, ssh]
author: Hyeonseop Jeong
comments : True
---

# asymmetric crypto algorithm 
`비대칭 키`를 생성하는 알고리즘이다. 

비대칭 키는 `public key`와 `private key`로 구성되고 `public key`는 `암호화`, `private key`는 public key로 암호화된 데이터를 `복호화` 하는 용도다.

- RSA
- DSA
- ECDSA 

ssh는 이 중에 하나를 이용하여 server authentication과 client authentication을 진행한다.
![shell](/assets/post_images/SSH/shell-message.png)
- 사진에서는 `ECDSA`를 쓴 모습니다.
- 근데 저 `fingerprint`는 뭘까.. 서버의 공개키를 `SHA(hash funtion)`에 돌린 값이라는데 왜 공개키 자체를 안받고 SHA로 돌려서 fingerprint로 받는지 잘 이해가 안간다.

----
# SSH의 작동과정
우선 remote server에 ssh로 접속하고자 할 때 다양한 방식이 있다.
1. `비밀번호`로 접속하는 방식
2. `key (비대칭 키)`로 접속하는 방식

- 두 방식 다 client가 `server authentication`은 해야한다.
- key로 접속하는 방식을 사용하려면 client에서 key를 만들어서 public키를 server의 접속할 계정에 넣어놔야한다. 
> 서버의 `(~/.ssh/authorized_keys)` 에 client의 public key가 저장 됨.


## server authentication
1. client가 server에게 접속을 한다고 함.
2. server는 자신의 `public key`를 client에게 보낸다.
3. client는 난수 데이터를 생성해서
    - 난수 데이터를 server로 부터 온 `public key`로 암호화하여 server에게 전송하고
    - 동시에 난수 데이터를 `SHA`로 돌려서 가지고 있는다.

4. server는 client로부터 온 데이터를 자신의 `private key`로 복호화하고 `SHA`로 돌려서 client에게 보낸다.

5. client는 server로 부터 온 값이 3번 과정에서 생성했던 SHA digest와 동일한 것을 보고 해당 server가 진짜임을 확인한다.

6. client의 `~/.ssh/known_hosts`에 해당 server를 추가하여 다음 번에는 굳이 server authentication과정을 거치지 않고 그냥 


## client authentication
`client authentication`도 과정이 똑같다.

client authentication 과정은 client에서 key방식으로 접속할 때 하는 과정이므로 미리 server쪽에 client의 `public key`를 넣어놔야한다.

>비밀번호 방식의 접속은 client에서 server authentication 만 하고 client authentication은 사용자가 비밀번호를 치는 것으로 대체하는 것 같음. 
> 근데 비밀번호 치는 방식의 접속보다 key 방식의 접속이 더 안전하다고 알려져있음.


1. server에서 난수 데이터를 생성해서 client의 `public key`로 암호화 후 client에게 보낸다. 
    - 이때 난수데이터를 SHA로 돌린 digest도 가지고 있는다.
2. client는 server로부터 받은 data를 `private key`로 복호화하고 SHA로 돌려서 server에게 보낸다.
3. server는 받은 데이터와 아까 만든 digest가 동일하다는 것을 보고 client가 진짜임을 확인한다.


## 이후 과정
이후에는 상대방을 `인증(authentication)`도 했고 상대방의 public key도 가지고 있으니 각자가 메시지를 암호화 할 `대칭키`를 상대방의 public 키로 암호화 하여 전송한 다음 그 대칭키로 암호화 된 데이터를 주고받는다.


> 위 과정을 디피-헬먼 키교환(DH Key Exchange)이라고 한다.

## 사진으로 보는 ssh 과정

![ssh process](/assets/post_images/SSH/ssh-process.png)


[자세한 과정 설명 링크](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process#negotiating-encryption-for-the-session)


