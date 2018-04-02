## pip 간단요약

**pip**는 파이썬 패키지를 쉽게 관리할 수 있도록 도와준다. 예를 들면 A라이브러리가 B라이브러리를
의존하고 있을경우 B라이브러리를 따로 설치하거나 관리하지 않아도 알아서 해결해준다. 또한 버전 관리도 도와준다.

**pip 설치**
python 설치시 자동으로 `C:\Python36\Scripts` 에 위치한다.
(python 2.7.9 이상일 경우이다, 그렇지 않다면 직접 설치해야한다)

**pip 업그레이드(Windows)**<br>
`python -m pip install -U pip`

**installing Packages**<br>
`pip install Package` 최신버전 패키지 설치 <br>
`pip install Package==1.0.4` 해당버전 패키지 설치<br>
`pip install 'Package>=1.0.4` 최소사양 패키지 설치<br>
`pip install -r requirements.txt requirements.txt` 파일에 나열되어있는 패키지들 설치

**Listing Packages**<br>
`pip list` 설치목록 조회<br>

**Uninstalling Packages**<br>
 `pip uninstall SomePackage` 패키지 삭제
