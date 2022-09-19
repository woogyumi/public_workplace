# RHEL/CentOS 에 git 2 설치하기


## 2.x 설치

2.x 이상을 사용할 경우 Wandisco 사의 repository 를 설치한 후에 yum 으로 설치하면 된다.

### CentOS 7 에서 설치하기
#### yum repository 설정

```shell
yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-2.noarch.rpm
```

##### or 

yum repository 파일 추가 : /etc/yum.repos.d/wandisco-git.repo

```shell
[WANdisco-git]
name=WANdisco Distribution of git
baseurl=http://opensource.wandisco.com/rhel/$releasever/git/$basearch
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-WANdisco
```


#### git 검색

정상 설치 여부를 확인하기 위해 WANdisco 저장소에서 git 검색

```bash
yum --enablerepo=WANdisco-git --disablerepo=base,updates info git
```

#### git 설치
repository 설치를 마쳤으면 아래 명령어로 git 을 설치(*git-svn* 은 subversion 저장소 이관하지 않을 경우 불필요)

```bash
yum --enablerepo=WANdisco-git --disablerepo=base,updates install git
```


### offline 설치용 local repository 만들기
위의 설명중 인터넷이 연결된 서버에서 git 검색  부분까지 실행후 아래 안내에 따라 실행

#### 설치파일 다운로드
```bash
yum --enablerepo=WANdisco-git --disablerepo=base,updates install git --downloadonly --downloaddir=.

```

#### 해당파일을 기존 local_repository에 추가후 갱신
