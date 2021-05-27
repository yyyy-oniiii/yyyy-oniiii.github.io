---
title: 💻 [Computer Basic] 😎개발자를 위한 Windows 개발환경 세팅
author: Yon Kim
date: 2021-05-18 10:00:00 +0900
categories: [💻Computer, Computer_Basic]
tags: [Computer_Basic]
---

# 😎 개발자를 위한 Windows 개발환경 세팅

<br><br>

## #**1 기본 셋업**

---

<br>

### 1.0 PC 포맷 후 드라이버 잡기 (3DP chip 이용)

### 1.1 Chocolatey 설치 후 필요 패키지 다운로드(Windows PowerShell 설치)

```markdown
#1.1.1
패키지: Chrome, VSC, Python, Windows Terminal, Git

#1.1.2
VSC Extensions: Prettier, Material Theme(+icons), Java Extensions, Python, Tab Out

#1.1.3
그외: Java SE(JDK)- 오라클 공홈 / WSL-MS / Ubuntu- MS Store
```

### 1.2 WSL (Windows Subsystems for Linux) 셋업

```markdown
#1.2.1
<https://docs.microsoft.com/ko-kr/windows/wsl/install-win10>

#1.2.2
WSL 기본 설치 + 커널 업데이트 + WSL 2 업데이트
```

### 1.3 메인보드 가상화(Virtual Machine) 셋업

```markdown
#1.3.1
Asus Prime X470 기준 BIOS 세팅 진입 후 Advanced 모드

#1.3.2
Advanced - CPU Configuration - SVM - Enabled로 변경
```

### 1.4 Ubuntu 셋업

```markdown
#1.4.1
Ubuntu 인스톨 후 유저 이름, 패스워드 설정

#1.4.2
wsl --set-version Ubuntu버전 2 입력(우분투에서 wsl2를 기본으로 사용하도록 설정)

#1.4.3
Windows Terminal 에서 기본 터미널을 Ubuntu로 설정 후 리붓
```

<br><br>

## **#2 커스터마이징**

---

<br>

### 2.1 oh my zsh

```markdown
#2.1.1
[http://github.com/ohmyzsh/ohmyzsh](http://github.com/ohmyzsh/ohmyzsh) 에서 zsh 다운로드>> sudo apt install zsh 쉘입력

#2.1.2 sh -c
"$(wget -O- [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))" 쉘입력

#2.1.3
설치 완료 후 code 입력하여 Ubuntu에 VSC 서버 연결

#2.1.4
이제 Ubuntu 에서 바로 VSC를 연결할 수 있다!
```

### 2.2 color scheme setup

```markdown
#2.2.1
[msdocs 안내](https://docs.microsoft.com/ko-kr/windows/terminal/customize-settings/color-schemes) 테마를 쓰거나

#2.2.2
[terminalsplash.com/?ref=producthunt](http://terminalsplash.com/?ref=producthunt) 에서 Terminal Splash를 사용할 수 있음

#2.2.3
.JSON 파일의 color scheme 값을 직접 수정하여 커스터마이징 할 것

> > 모든 쉘에 같은 테마를 쓰고 싶은 경우

     "profiles"의 "defaults"에 "colorschome": "테마", 를 넣어줄 것
```

### 2.3 powerlevel10k

```markdown
#2.3.1
더 쾌적한 환경을 위해 powerlevel10k 사용 (oh my zsh 써서 설치)

#2.3.2
[https://github.com/romkatv/powerlevel10k#oh-my-zsh](https://github.com/romkatv/powerlevel10k#oh-my-zsh) 에서 git clone 복사 후 붙여넣기

#2.3.3
.zshrc 파일 수정 (명령어: code ~/.zshrc)>> 디폴트를 powerlevel10k/powerlevel10k 로 변경

#2.3.4
터미널 재시작 후 Powerlevel10 Configuration wizard 진행

#2.3.5
MesloLGS NF 폰트 설치(Regualr, Bold, Italic, Bold Italic)

#2.3.6
폰트가 깨져보이는 경우, 터미널 세팅(.JSON) 에서
"defaults" 값에 "fontFace": "MesloLGS NF" 추가

#2.3.7
VSC Preferences > Terminal > Integrated - Font Family 찾아 MesloLGS NF 기본폰트로 설정

#2.3.8
Powelevel10k 설정 마무리
```

### 2.4 ls color change

```markdown
#2.4.1
쉘에서 code ~./zshrc 로 설정파일 열어주기

#2.4.2
마지막 라인에 LS_COLORS="ow=01;36;40" && export LS_COLORS 추가 (wsl 기본 ls 컬러를 변경)

#2.4.3
VSC settings > intergrated terminal > automationsShell Windows Edit.JSON 열고

#2.4.4
"terminal.integrated.automationShell.windows": "C:\\Windows\\System32\\wsl.exe" 추가

#2.4.5
저장 후 터미널 창 연 뒤 powershell로 선택되어있는 터미널을 🔽 눌러서 Ubuntu(WSL)로 변경
```

[https://nomadcoders.co/windows-setup-for-developers/lectures/1836](https://nomadcoders.co/windows-setup-for-developers/lectures/1836)

<br><br>

## **#3 설치**

---

<br>

### 3.1 리눅스 명령어

```java

$ ls
// 디렉토리 출력(list)

$ cd ..
// 상위폴더로 이동

$ cd
// 디렉토리 이동

$ touch helloworld.java
// .java 파일 생성

$ touch something/else.java
// 현재 위치에 something 디렉토리 생성 후 그 안에 else.java 생성

$ mkdir new_project
// 현재 위치에 new_project 디렉토리 생성

$ mv file.java to_new_file.java
// file.java의 이름을 new_file.java 로 변경

$ mv /foldername /home/yon/java
// fordername 디렉토리를 /home/yon/java 로 옮기기

$ rm something/file.java
// something 디렉토리 내의 file.java 삭제

$ rm -rf something
// something 디렉토리를 삭제하기

$ exit()
// 프로그램 종료

$ sudo
// root 권한 부여(admin)

$ 프로그램명 -v
// 프로그램 버전 확인

$ code ~/.zshrc
// 우분투 콘솔 설정
// .zshrc 파일에 alias python=python3.8 명령어를 추가하면
// 파이썬을 실행할 때 기본적으로 3.8 버전을 실행한다

$ sudo tar xvf /파일명.tar.gz
// .tar 파일의 압축을 풀어주는 명령어 -오라클 Java 설치할 때 사용했음

$ sudo vi /etc/profile
// 환경설정 진행

$ mkdir new_project
// 현재 위치에 new_project 디렉토리 생성

```

### 💙 윈도우에서 WSL를 이용하는 경우, 유저는 작업 방식을 선택할 수 있다.

        1. 프로젝트와 모든 소스코드를 윈도우 하드드라이브에 저장하거나(Window side)
        2. 프로젝트와 모든 소스코드를 리눅스 Home 디렉토리에 저장하거나(Linux side)

### 💙 주의할 점

        Linux 에서는 윈도우 파일에 접근하여 무언가를 건드려볼 수 있지만,
        반대로 윈도우에서 Linux에 보관해둔 파일에 접근하여 무언가를 건드리려는 순간 각종 충돌을 만나게 된다.
        따라서 윈도우에서는 그 어떤 리눅스 파일도 건드리지 않는 것이 좋다.
        따라서 되도록 프로젝트와 소스코드 파일은 윈도우에 보관하고 Linux에서 접근하여 사용하는 방식으로 작업을 진행하는 것을 권장한다.

<br><br>

### 3.2 apt(apt 명령어는 패키지를 다운로드 할 데이터베이스를 검색해보게 만든다.)

<br>

```java

$ apt-get install 프로그램명
// 프로그램 설치하기 (ubuntu install 로 구글링하여 필요한 프로그램 다운)
// apt 는 패키지를 다운로드 할 수 있게 만들어준다(DB를 찾음)

$ apt-get upgrade
// 패키지 업그레이드

$ apt-get update
// apt-get 이 찾아볼 수 있는 프로그램들의 DB를 업데이트 하는 명령어
```

<br><br>

## **#4 Java 설치**

---

<br>

### 4.1 리눅스 서버에 Java 설치하기

```java
$ sudo apt-get update
// (1) apt 업데이트

$ sudo apt-get install openjdk-11-jdk
// (2) openjdk 11 설치

$ java -version
// (3) 설치여부 확인

$ sudo update-alternatives --config java
// (4) 업데이트

$ which javac
// (5) 자바 설치폴더 위치 리턴

$ readlink -f $(which javac)
// (6) javac의 실제 파일 경로를 리턴 - 이 경로를 기준으로 환경변수를 설정(컴파일러 경로 설정)
// ex) /usr/lib/jvm/java-11-openjdk-amd64

$ sudo nano /etc/profile
// (7) 나노 편집기를 이용하여 컴파일러 경로를 설정해준다.

(8) 나노 편집기의 마지막 줄에 JAVA_HOME,PATH,CLASS_PATH 경로를 추가해준다

$ export JAVA_HOME=(6) 에서 리턴된 경로 ex)  /usr/lib/jvm/java-11-openjdk-amd64
$ export PATH=$JAVA_HOME/bin/:$PATH
$ export CLASS_PATH=$JAVA_HOME/lib:$CLASS_PATH

(9) ctrl + o 로 세이브하고 ctrl + x 로 편집기를 빠져나온 뒤 우분투 재실행

(10) $ java -version 및 $ javac -version 으로 버전 출력이 제대로 되는지 확인

(11) 이제 VSC-WSL 환경에서 Java를 컴파일 할 수 있다!

// ref: https://www.youtube.com/watch?v=-ea_gSFJ4Tg
```

<br><br>

## **#5 Git 설치**

---

<br>

### 5.1 리눅스 서버에 Git 설치하기

```java
$ sudo apt-get install git
$ sudo apt install git
// (1) git 설치

$ git --version
// (2) 설치된 git 버전 확인(버전명이 뜨면 정상)

$ git config --global user.name "깃허브 계정"
$ git config --global user.email "이메일"
// (3) 유저 설정

$ git clone (원하는 리포지토리 주소)
// (4) 현재 위치에 리포지토리 복제
```

<br>

### 5.2 리눅스 서버에 Git CLI 설치하기

```java
링크: https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian-ubuntu-linux-apt

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key C99B11DEB97541F0
sudo apt-add-repository https://cli.github.com/packages
sudo apt update
sudo apt install gh

이후 버전 업그레이드는
sudo apt update
sudo apt install gh

```
