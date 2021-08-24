# Git Cheat Sheet

### Git commit patch

현재 commit 부터 입력한 commit 이전까지의 각 commit마다 패치 생성

commit 개수만큼 결과가 나오고, commit message 제목으로 patch 명이 생성된다.

```shell
$ git format-patch [commit-id]
```

만들어진 패치를 적용하려면 git am 을 쓰면 된다. 옵션은 -3 을 추천

```shell
$ git am -3 [patch file]
```



### Git diff patch

commit이 만들어지지 않은 수정 사항으로도 패치를 생성할 수 있다.

```shell
$ git diff > [patch file]
```

해당 패치 파일을 git apply를 통해 적용하면 된다.

```shell
$ git apply [patch file]
```



### Git Commit Messages Style

다음과 같이 commit message 앞의 카테고리 명은 chore, docs, feat, fix, refactor, style, test가 가능하다. [링크](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)

```shell
feat: add hat wobble
^--^  ^------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: chore, docs, feat, fix, refactor, style, or test.
```

- `feat`: (new feature for the user, not a new feature for build script)
- `fix`: (bug fix for the user, not a fix to a build script)
- `docs`: (changes to the documentation)
- `style`: (formatting, missing semi colons, etc; no production code change)
- `refactor`: (refactoring production code, eg. renaming a variable)
- `test`: (adding missing tests, refactoring tests; no production code change)
- `chore`: (updating grunt tasks etc; no production code change)

