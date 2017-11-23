# easyadb

adb 를 편하게 쓰고자 만든 스크립트 입니다.
현재 mac에서만 동작합니다.(Linux는 테스트 안해봤습니다.)

## 기능(function)

 - Signing
 - Install
 - Update(keep data)
 - Run (screen wakeup)
 - Logcat (device가 2개 이상인 경우 선택 화면 출력)
 - Uninstall
 - Exit
 - All funcitons support multi-device

## 설정(Settings)
### 권한 설정(executable permission)

```
$chmod +x adbinstall
```

### adb, aapt path 설정되어 있는경우 > 바로 사용

```
$adb version
  Android Debug Bridge version 1.0.39
  Revision 3db08f2c6889-android
  Installed as /Users/user/Library/Android/sdk/platform-tools/adb

$aapt version
  Android Asset Packaging Tool, v0.2-4355572
```
> 바로 사용 가능 합니다.


### adb, aapt path 설정이 안되어 있는 경우(if you can't found path)

```
$adb
 command not found: adb
$aapt
 command not found: aapt
```
 > path 지정 또는 파일내 경로 수정

#### a) adb, aapt path setup

```
$export PATH=$PATH:adb_path
```
#### b) adb, aapt 경로 수정
adbinstall file을 에디터로 열러 아래 두 부분을 
```
AAPT_PATH=`which aapt`
ADB_PATH=`which adb`
```
아래와 같이 변경해줍니다. 
```
AAPT_PATH="/Users/user/android/tools/"
ADB_PATH="/Users/user/android/tools/"
```


## 기본 사용(basic usage)

 - install + run + logcat 
```
$adbinstall -a test.apk
```

 - sign + install + run + logcat 
```
$adbinstall -a -s test.apk
```

 - install + run
```
$adbinstall -i -r test.apk
```

 - uninstall 
```
$adbinstall -u test.apk
```

 - install + run + logcat 
```
$adbinstall -a test.apk
```

 - update install(keep data) + run
```
$adbinstall -k -r test.apk
```

> 저작권 따위는 없습니다.  막쓰시고..업데이트도 해주시고..
> 
> 업데이트 되면 저에게도 공유해주시고 push 해주시면 베리 감사합니다.
