---
title: Git_First
date: 2021-01-27 12:13:20
tags:
---


# Git 시작하기

## Git 설치하기

sudo apt-get install git

설치 후

git --version 으로 설치 확인

## 설정하기

git config --gloval user.name "{github ID}"
git config --gloval user.email "{github email}"
git config --global core.editor "vim" <-- 사용하는 편집기로 수정
git config --global core.pager "cat"

## Github에 commit해보기(첫번째 방법)

1. 디렉토리를 만들고 폴더로 이동한다.
  
   mkdir 폴더이름 && cd 폴더이름

2. Git으로 연결하기.

   git init

3. Git remote 하기.

   git remote add origin http://github.com/{username}/{폴더이름}.git

4. commit할 파일 만들기.

   touch 파일이름.md (md:markdown)

5. 파일을 vim으로 수정하기

   vi 파일이름 으로 vim 으로 들어가서 i 를 누르게 되면 수정가능한 화면으로 전환되고 내용을 적는다.
   
   내용 작성이 끝나면 esc를 누르고 :wq 를 눌러 저장한다.

6. 확인하기.

   git status 로 확인하기

7. Git에 add하기.

   git add 파일이름

   vim이 뜨는데 첫줄에는 일종의 제목으로 글의 type을 적어준다.

   아래줄부터는 글 작성 또는 변경사항을 적어준다.

8. 확인하기

   6번과 동일

9. commit하기

   git commit -m "파일이름"

10. 확인하기

   6번과 동일

11. push하기

   git push -u origin master

## commit 하기 (2번째 방법)

1. Github 홈페이지에서 저장소를 생성합니다.

   저장소 주소를 복사합니다.

2. Github clone 하기

   git clone 복사한 저장소 주소

3. 작성한 파일 add하기

   git add 파일이름

4. 확인하기

5. commit 하기

   git commit

6. push하기

   git push

