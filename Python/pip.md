## pip 간단요약

##### pip는 파이썬 패키지를 쉽게 관리할 수 있도록 도와준다. 예를 들면 A라이브러리가 B라이브러리를
의존하고 있을경우 B라이브러리를 따로 설치하거나 관리하지 않아도 알아서 해결해준다. 또한 버전 관리도 도와준다.

##### pip 업그레이드(Windows)
```bash
python -m pip install -U pip
```

##### installing Packages

* 최신버전 패키지 설치
```bash
pip install Package
```
* 해당버전 패키지 설치
```bash
pip install Package==1.0.4
```
* 최소사양 패키지 설치
```bash
pip install 'Package>=1.0.4
```
* 파일에 나열되어있는 패키지들 설치
```bash
pip install -r requirements.txt requirements.txt
```

##### Listing Packages(설치 목록 조회)
```bash
pip list
```

##### Uninstalling Packages(패키지 삭제)
```bash
pip uninstall SomePackage
```
