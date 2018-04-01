## 안드로이드 성능 측정방법

1. `platform-tools` 다운로드 받는다([URL 참고](https://developer.android.com/studio/releases/platform-tools.html#revisions))

2. 안드로이드와 PC를 연결한다.

3. 안드로이드 **설정 > 휴대정화정보 > 소프트웨어 정보 > 빌드번호**를 여러번 클릭하여 개발자 모드를 실행시킨다.

4. 개발자모드가 활성화되면 개발자 옵션에서 USB 디버깅 모드 실행한다.

5. cmd창을 실행하고 `platform-tools`를 설치한 곳으로 이동한다.

6. 아래의 명령어를 실행하면 PC와 연결된 장치가 검색됨을 확인한다.

```bash
$ adb devices
```

7. 아래의 명령어를 실행하면 1초단위로 가상 메모리 통계를 수집하여 test.txt 파일로 저장된다.

```bash
$ adb shell vmstat 1 > test.txt
```