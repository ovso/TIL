### .bash_profile이 동작하지 않을때

.bash_profile를 작성후 source .bash_profile 했지만, 새로운 터미널을 열면 커맨드가 동작하지 않을때가 있다.

새로운 터미널을 시작할때 .bash_profile이 실행되도록 해야 한다. .zshrc 파일을 열어 아래와 같이 작성해주면 된다. 파일이 없다면 만들면 된다.

```
if [ -f ~/.bash_profile ]; then
  . ~/.bash_profile
fi
```

물론, .bash_profile이 항상 동작하지 않는건 아니다. 이미 .zshrc 파일이 존재하고, 아래와 같이 실행되고 있다면 .bash_profile에 작성한 코드가 잘 실행되고 있을 것이다.

```
[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"
```

