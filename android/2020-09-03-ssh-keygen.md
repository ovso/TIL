# SSH keys

## 확인하기

터미널을 열고 명령어를 실행한다:

```
$ ls -al ~/.ssh
```

```
-rw-------   1 jaeho  staff  3247  8 18 15:03 id_rsa
-rw-r--r--   1 jaeho  staff   750  8 18 15:03 id_rsa.pub
-rw-------   1 jaeho  staff  2602  9  3 03:05 id_rsa_personal
-rw-r--r--   1 jaeho  staff   570  9  3 03:05 id_rsa_personal.pub
```

## 생성하기

```
ssh-keygen -t rsa -b 4096 -C your_email@example.com

or

ssh-keygen -t rsa -C your_email@example.com
```



Gtihub의 경우 `이미 사용하고 있는 ssh` 는 본인의 타 계정에 등록되지 않을 수 있다.(가물가물..)  추가로 생성하는 것은 ssh를 생성할때 `파일명과 이메일`을 다르게 입력하면 된다.

## 참고

[https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

[https://xho95.github.io/macos/security/openssh/ssh/gitlab/2017/02/22/Using-SSH-on-Mac.html](https://xho95.github.io/macos/security/openssh/ssh/gitlab/2017/02/22/Using-SSH-on-Mac.html)

[https://git-scm.com/book/ko/v2/Git-%EC%84%9C%EB%B2%84-SSH-%EA%B3%B5%EA%B0%9C%ED%82%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0](https://git-scm.com/book/ko/v2/Git-%EC%84%9C%EB%B2%84-SSH-%EA%B3%B5%EA%B0%9C%ED%82%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0)

