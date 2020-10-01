# Environments in Android
## 1. Termux
플레이 스토어에서 termux 설치 후 실행.

이후 다음 명령어를 실행하여, 스토리지 권한을 획득한 후, 재 실행 할 것

```bash
termux-setup-storage
```




## 2. Ubuntu
먼저 다음 프로그램들을 설치해준다.

```bash
apt-get update
pkg install wget -y
pkg install openssl-tool -y
pkg install proot -y
```

그리고 다음 경로로 이동하여, 우분투를 설치한 후, 그것을 실행해준다.

```bash
cd storage
mkdir ubuntu && cd ubuntu

bash -r
wget https://raw.githubusercontent.com/EXALAB/AnLinux-Resources/master/Scripts/Installer/Ubuntu/ubuntu.sh
bash ubuntu.sh

./start-ubuntu.sh
```




## 3. Code Server
다음 명령어를 실행, `code-server` 를 설치해준다.

이후에 암호를 설정해주고, `code-server` 커맨드를 입력, 그것을 실행해주면 된다.

```bash
apt-get update
apt-get install -y curl

curl -fsSL https://code-server.dev/install.sh | sh

export PASSWORD="1231"
code-server
```

이후 http://localhost:8080 에 접속하여, `vscode` 를 사용할 수 있다. 

다만, 원활한 `vscode` 개발을 위하여, 몇 가지 필수 패키지들을 설치하고, 예제들을 구성해보자.

```bash
apt-get update
apt-get install -y git
apt-get install -y nodejs
apt-get install -y npm

git config --global credential.helper store

mkdir github && cd github
mkdir samchon && cd samchon

git clone https://github.com/samchon/tstl
git clone https://github.com/samchon/tgrid
git clone https://github.com/samchon/mutex-server
```