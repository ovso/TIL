# SSH keys

## 확인하기

터미널을 열고 명령어를 실행한다:

```
$ ls -al ~/.ssh
```

```
drwx------   7 jaeho  staff   224  9  3 03:05 .
drwxr-xr-x+ 21 jaeho  staff   672  9  3 03:13 ..
-rw-------   1 jaeho  staff  3247  8 18 15:03 id_rsa
-rw-r--r--   1 jaeho  staff   750  8 18 15:03 id_rsa.pub
-rw-------   1 jaeho  staff  2602  9  3 03:05 id_rsa_personal
-rw-r--r--   1 jaeho  staff   570  9  3 03:05 id_rsa_personal.pub
-rw-r--r--   1 jaeho  staff  1600  8 20 11:48 known_hosts
```

## 생성하기

```
ssh-keygen -t rsa -b 4096 -C your_email@example.com

or

ssh-keygen -t rsa -C your_email@example.com
```



Gtihub의 경우 `이미 사용하고 있는 ssh` 는 본인의 타 계정에 등록되지 않을 수 있다. 그러므로 추가로 생성하여 사용해야 한다. 추가로 생성하는 것은 ssh를 생성할때 `파일명과 이메일`을 다르게 입력하면 된다.