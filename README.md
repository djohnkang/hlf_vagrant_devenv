# Hyperledger Fabric 개발환경 설정
Vagrant VM을 활용한 Hyperledger Fabric 개발환경 설정

## I. Vagrant
경량형 hypervisor

### (1) Vagrant 명령어들
주로 사용하게 되는 `vagrant` 명령어들

1. `vagrant up` : 실행
  - Vagrantfile 파일에 명시된 설정으로 가상환경을 만들고

2. `vagrant ssh` : 접속
  - 가상환경에 접속

3. `vagrant halt` : 중지

4. `vagrant destroy` : 삭제


---
### **중요!**  
#### **호스트**(windows)와 **가상머신**(vagrant)에서 실행해야하는 커맨드를 구분
#### 호스트 : `>`로 시작되는 커맨드
```shell
> vagrant ssh
```
#### 가상머신 : `$`로 시작되는 커맨드
```shell
$ ./install/install-prereqs
```
---

## II. HLF과 Composer 환경 구성을 위한 사전 설치(prerequisites)
참고 : https://hyperledger.github.io/composer/v0.19/installing/installing-prereqs

### (1) 가상환경 접속
```shell
> vagrant up
> vagrant ssh
```

### (2) 사전 설치 프로그램(prerequisites) 설치 스크립트 실행

1. 설치 스크립트 실행,

`install` 디렉토리에 들어 있는 `install-prereqs.sh` 실행 후 재접속

```shell
$ ./install/install-prereqs.sh

# 가상 머신으로부터 로그아웃
$ logout
```

2. 재접속

```shell
> vagrant ssh
```

### (3) Fabric 도구 및 Composer 설치
1. Fabric 도구들 설치

```shell
$ ./scripts/install-fabric-tools.sh
```

2. Composer 설치

```shell
$ ./scripts/install-composer.sh

# 설치 후 재접속
$ logout
```

### (4) Fabric 다운로드
1. 재접속

```shell
> vagrant ssh
```

2. Fabric 다운로드

```shell
$ ./downloadFabric.sh
```
