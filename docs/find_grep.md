# find, grep, ripgrep
개발을 하다보면 파일을 찾거나 코드에서 특정문자를 검색하는 경우가 많이 발생합니다.
위 형태의 업무를 도와주는 3종 명령어를 알아보겠습니다.

## find
홈디렉토리 소스 폴더에서 python 파일을 출력하는 예제
```
$ find ~/source -name "*.py"
```

`/work/path/test.nk` 파일보다 이후에 생성된 파일을 출력하는 예제
```bash
$ find /work/path -newer /work/path/test.nk
```

## grep
grep은 파이프와 자주 사용하는 명령어입니다.
결과에서 필터링 할 때 자주 사용되는 명령어 입니다.
위 결과에서 `test` 문자가 들어간 경로만 출력합니다.

```
$ find ~/source -name "*.py" | grep test
```

## ripgrep
수많은 파일내부에서 문자를 검색할 때 자주 사용합니다.
grep 보다 속도가 굉장히 빠릅니다.

소스코드 : https://github.com/BurntSushi/ripgrep

설치방법

```bash
$ su
# yum-config-manager --add-repo=https://copr.fedorainfracloud.org/coprs/carlwgeorge/ripgrep/repo/epel-7/carlwgeorge-ripgrep-epel-7.repo
# yum install ripgrep
# exit
```

기본 사용법
```bash
$ rg 검색어
```

파이썬 파일에서만 검색하는 방법
```bash
$ rg -g '*.py' 검색어
```