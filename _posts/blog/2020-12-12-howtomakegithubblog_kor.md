---
title: "Github Blog 만들기 ( 리눅스/ 윈도우 git-bash )"
category:
  - git
tag:
  - github
  - git
  - blog
  - github.io
use_math: true
header:
  overlay_image: https://github.com/ihyeonseung/ihyeonseung.github.io/blob/master/assets/img/start/github_logo.png
  overlay_filter: 0.5
published: true
author_profile: true
---

# 사용 도구
---
![git-bash](https://github.com/ihyeonseung/ihyeonseung.github.io/blob/master/assets/img/start/git_hpg/git_bash.png?raw=true)

- GIT-BASH를 이용하여 설치를 진행하였습니다.

&nbsp;
# GIT - Clone 하기
---

- 입문자용 깃허브 블로그 테마인 `minimal-mistakes`를 이용할 것이다.

```python
mkdir blog_blog
cd blog_blog  # 블로그 파일을 저장할 폴더
git clone https://github.com/mmistakes/minimal-mistakes .  # 쩜 중요
```
&nbsp;
&nbsp;
# Repository 만들기

---

- `계정명.github.io` 라는 repository 만들기

![git-io](https://github.com/ihyeonseung/ihyeonseung.github.io/blob/master/assets/img/start/git_hpg/git_io.png?raw=true)
&nbsp;
&nbsp;
- git-clone 를 했던 master-directory에 들어가서 `보기-숨김파일 보기`로 설정을 변경한 뒤,  `.git` 폴더를 삭제해 준다.
- 리눅스의 경우 다음 명령어를 실행한다.

```docker
sudo rm -r .git
```
&nbsp;

- `.git` 폴더를 지웠으므로 다시 `git` 에 연결하기 위해 다음 명령어를 실행한다.

```python
git init
```
&nbsp;
- 본인의 블로그와 현재 `git-master` 폴더를 연결하기 위해 다음 명령어를 실행한다.

```python
git remote add origin https://github.com/ihyeonseung/ihyeonseung.github.io
```
&nbsp;
- 연결여부를 확인하기 위해 다음 명령어를 실행할 수 있다.

```python
git remote -v 

origin  https://github.com/ihyeonseung/ihyeonseung.github.io (fetch)
origin  https://github.com/ihyeonseung/ihyeonseung.github.io (push)
```
&nbsp;
- 현 디렉토리의 내용을 `github`에 반영한다.

```python
git add .
```
&nbsp;

- 변경내용을 `commit` 한다.

```python
git commit -m 'blog-start'
```
&nbsp;
- `commit`한 내용을 repository에 반영한다.

```python
git push origin master
```
&nbsp;
&nbsp;

### fatal: protocol '??https' is not supported 에러가 난 경우

---

- github 주소를 복사 붙여넣기 하면서 `https` 앞에 잘못된 값이 전달된 경우이므로, `.git`파일을 삭제한 뒤, 주소를 직접 타이핑하며 위 과정을 다시 진행한다.

&nbsp;
# 이제 블로그에 접속해보자

---

- `<username>.github.io` 로 들어가보자.
- 다음과 같은 화면을 만날 수 있다.

![fst-page](https://github.com/ihyeonseung/ihyeonseung.github.io/blob/master/assets/img/start/git_hpg/fst_page.png?raw=true)

&nbsp;
# 블로그의 기본 파일들

---

- _config.yml : 설정 파일
- _posts : 블로그 포스팅
- _pages : 개별 페이지
- _includes : 글에 포함되는 개별요소
- _layouts : 글의 양식
- assets : image, css 등
- index.html : 표시
&nbsp;
- 없는 요소들은 `local` 에서 폴더를 생성해주면 된다.

&nbsp;
&nbsp;
# _ Config.yml 설정하기

---

- 블로그의 기본 틀을 잡아주려면 `_config.yml` 을 설정해주어야 한다.
- 각 요소가 무엇을 의미하는지는 읽어보면 아실테니 생략한다.

![cfg-img](https://github.com/ihyeonseung/ihyeonseung.github.io/blob/master/assets/img/start/git_hpg/cfg_img.png?raw=true)
&nbsp;
# 블로그 설정 마친 뒤 다시 commit

---

- 이것저것 설정을 마치고, `_post`에서 글을 작성했다면 다시 git 에 `commit`을 한 뒤, `push` 를 해준다.

```python
git commit -m 'first blog commit'
git push origin master
```



&nbsp;
# 마치며..
---
- **Github 블로그**가 익숙해질 때 쯤, 블로그 작성하기로 돌아오겠습니다.

- 감사합니다 -