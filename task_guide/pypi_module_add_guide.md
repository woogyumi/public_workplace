# private pypi 서버에 python 모듈 추가하기

### 인터넷이 가능한 리눅스 서버에서 모듈 다운로드

  1. 모듈 다운로드
    - 임시 폴더생성 및 이동
    - pip 명령어로 모듈 다운로드
    - 다운받은 모듈 압축
  ```
  mkdir python_tmp
  pip download -d . 모듈명
  tar -zcvf python-packages-생성일.tar.gz *
  ```

  2. 모듈을 private pypi 서버로 이동
    - 압축한 파일을 pypi 서버로 이동
    - 압축해제하여 pypi서버의 모듈 경로에 복사
