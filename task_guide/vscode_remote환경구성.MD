# 사설망 환경에서 vscode ssh개발환경 구성하기

## 필요한 파일 다운로드 하기
- vscode 설치 파일과 해당 버전의 commitid와 일치하는 vscode-server 설치파일이 필요함

## vscode 설치 파일을 받아 설치한다.
- 2022.09.28일 기준 최신버전으로 환경구성
- version : 1.71.2
- https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user
- commitid : 74b1f979648cc44d385a2286793c226e611f59e7

#### vscode-server 파일을 다운로드
https://update.code.visualstudio.com/commit:74b1f979648cc44d385a2286793c226e611f59e7/server-linux-x64/stable

#### 다운로드된 파일 명 : vscode-server-linux-x64.tar.gz

## vscode 설치하기
### 다운로드한 vscode 설치파일을 개발용 PC(윈도우)에 설치

## vscode-server설치
### ssh로 개발서버에 접속
```
cd ~/
mkdir -p .vscode-server/bin/74b1f979648cc44d385a2286793c226e611f59e7
cd .vscode-server/bin/74b1f979648cc44d385a2286793c226e611f59e7
### vscode-server 파일 업로드
tar -xvzf ~/vscode-server-linux-x64.tar.gz --strip-components 1

```
## vscode extension 설치
### 아래 링크의 파일을 다운로드 받아 로컬파일 설치 형태로 vscode와 vscode-server에 설치


https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/GrapeCity/vsextensions/gc-excelviewer/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/MS-CEINTL/vsextensions/vscode-language-pack-ko/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/PKief/vsextensions/material-icon-theme/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/VisualStudioExptTeam/vsextensions/vscodeintellicode/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/alexcvzz/vsextensions/vscode-sqlite/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/donjayamanne/vsextensions/githistory/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/eamodio/vsextensions/gitlens/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/esbenp/vsextensions/prettier-vscode/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/humao/vsextensions/rest-client/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/janisdd/vsextensions/vscode-edit-csv/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/mhutchie/vsextensions/git-graph/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-python/vsextensions/python/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-python/vsextensions/vscode-pylance/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-toolsai/vsextensions/jupyter/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-vscode-remote/vsextensions/remote-ssh/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-vscode-remote/vsextensions/remote-ssh-edit/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-vscode/vsextensions/atom-keybindings/latest/vspackage
https://marketplace.visualstudio.com/_apis/public/gallery/publishers/shd101wyy/vsextensions/markdown-preview-enhanced/latest/vspackage


## vscode ssh 연결 환경 구성
### ssh 공개키 생성
### ssh 접속 정보 구성
```
Host [계정명]@[IP 주소]:[포트번호]
    HostName [IP 주소]
    User [계정명]
    Port [포트 번호]
    IdentityFile ~/.ssh/id_rsa
```
### 원격서버에 공개키 배포
