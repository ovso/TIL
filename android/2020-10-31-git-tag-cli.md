# Git Tag 명령어

### Tag 조회

```
> git tag
v0.0.1
v0.0.2
v0.1.2
v1.0.0
```

### Tag 조건 조회

```
> git tag -l "v0.0.*"
v0.0.1
v0.0.2
```

### Tag 정보 보회

```
> git show v1.0.0
tag v1.0.0
Tagger: jaeho <ovsoce@gmail.com>
Date:   Sat Oct 31 17:02:16 2020 +0900

- Bugfix
...
```

### Tag 만들기

```
> git tag -a v1.0.1 -m "message"
> git tag v1.0.1
```

### Tag 지우기

```
> git tag -d v1.0.0
Deleted tag 'v1.0.0' (was ~~)
```

### Tag 조회(Remote)

```
> git ls-remote --tags
From https://github.com/ovso/Blackbox.git
fe969e2f5b93b96f7fc76c66014486061416f93d        refs/tags/v0.0.1
206932277c28b43acab6085264c380d7b20f2cff        refs/tags/v0.0.1^{}
c21cfbde597b18a06c448d150d5c959fc53e26dd        refs/tags/v0.0.2
```

### Tag push(Remote)

```
> git push origin v1.0.0
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 150 bytes | 75.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0)
...
```

### Tag push(Remote - 전체)

```
> git push origin --tags
Enumerating objects: 2, done.
Counting objects: 100% (2/2), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 277 bytes | 277.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0)
...
```

### Tag 지우기(Remote)

```
> git push origin :refs/tags/v1.0.0
> git push origin :v1.0.0
> git push origin -d v1.0.0
> git push origin --delete v1.0.0
```



[https://seizze.github.io/2019/12/24/Git-Tag-%EA%B4%80%EB%A0%A8-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC.html](https://seizze.github.io/2019/12/24/Git-Tag-%EA%B4%80%EB%A0%A8-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC.html)

[https://git-scm.com/book/en/v2/Git-Basics-Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)

[https://git-scm.com/docs/git-tag](https://git-scm.com/docs/git-tag)

[https://git-scm.com/docs/git-show-ref](https://git-scm.com/docs/git-show-ref)

