# How_To_MetaLense2_Build
## 메타렌즈2 빌드 방법 및 에러로그

✅ (해결함) 
❌ (실패함)

Error List 
###  1. 키 등록 에러

![image](https://github.com/user-attachments/assets/9761c054-808f-456b-bd49-b268fb40e1f8)

     사진처럼 나오거나 콘솔에 Key Store 관련 에러가 나온다면
     Project Settings -> Player -> Publishing Settings의 Project Keysoter 가 있음
     기존 키가 존재하면 비밀번호를 입력하고 빌드하면 해결.
     (비밀번호를 모르겠으면 Keystore Manager...에서 새로운 키를 생성하면 OK

![image](https://github.com/user-attachments/assets/2a45c49f-5758-4c54-a1c6-c3deb893aa07)

     First and Last Name 부터 입력하지 않아도 상관없으며 실제 앱 배포 시 신경써야할 부분인거같음

 ### 2. Build And Run Error ✅

![image](https://github.com/user-attachments/assets/1c2ba1da-40af-4571-8fdb-4b74362aa7aa)

     해당 에러는 build.gradle 파일의 설정값이 잘못되었다는 의미인거같음.

     경로 : 내 프로젝트 폴더 -> Library/Bee/Android/Prj/IL2CPP/Gradle/unityLibrary/src/main/AndroidManifest.xml

     - 초기값
       
![image](https://github.com/user-attachments/assets/ff996cd1-194a-463f-b625-2c3be932349f)

     - 수정값
    
![image](https://github.com/user-attachments/assets/0af3f936-1545-4329-b557-91d013c6dd5b)

      이렇게 하면 에러를 해결할 수있음. plugins 코드의 위치와 classpath를 적용하려면 buildscript에 집어넣어줄것
      근데 왜 기본 빌드값이 저렇게 나오는지는 모르겠음

     

     
 ### 4. CommandInvokationFailure: Gradle build failed. ✅ (2번 문제가 해결될 시 같이 없어짐)

![image](https://github.com/user-attachments/assets/047400f7-69ca-4811-9bc7-00172e7ab063)


 ### 5. UnityEditor.BuildPlayerWindow+BuildMethodException ✅ (2번 문제가 해결될 시 같이 없어짐)

![image](https://github.com/user-attachments/assets/588afd30-f880-4083-ad84-e78c311074a4)


 ### 6. DeploymentOperationFailedException: No activity in the manifest with action MAIN and category LAUNCHER. ✅

     프로젝트 폴더 -> Plugins -> Android 폴더 내부 AndroidManifest.xml 수정 파일이 없으면 새로 생성할것.

     새로운 Intent-filter에 사진에 보이는 MAIN과 LAUNCHER를 넣으면 해결
![image](https://github.com/user-attachments/assets/ddf219d3-67f4-458e-a1a5-b096cbf522b9)



 ### 7. 메타렌즈 빌드 후 실행 시 검은화면 현상 ✅
      -  Snapdragon은 OpenXR 플러그인의 항상 1.10.0버전을 권장하고있음. 다른 버전을 사용하면 검은화면이 나올 가능성이 있다고함.
                (해당 Docs를 잘 뒤져보면 팁들을 올려놓음) 
          Snapdragon 링크 : https://docs.spaces.qualcomm.com/unity/setup/setup-guide

      -  반드시 Snapdragon에서 권장하는 버전을 지켜라! 
          OpenXR설정에서 기능 선택 부분에 기존 MRTK2 설정 이름과 같은 경우가 있음 그래서 어느 라이브러리의 기능인지 확인 잘 하고 선택!

      -  그래도 검은화면이 나온다면 ADB AppControl에서 앱을 우클릭 후 Set Permissions 클릭 거기서 카메라 권한 추가해주면 해결
![image](https://github.com/user-attachments/assets/f1ba11b3-8d26-4a21-8e89-43143540d643)
   
 
 ### 8. 렌즈 테스트 할때 유용한 툴 ✅
      -  ADB Control을 다운받으면 렌즈 APK파일을 추가하거나 삭제할때 아주 편함
      -  유니티의 Anodroid Logcat : 렌즈 내부 동작을 디버깅할 수 있다.

 ### 9. 빌드는 잘 했는데 렌즈에서 API요청 반응 없을때
      -  Project Settings -> Player -> Other Settings -> Configuration -> Allow downloads over HTTP 옵션 설정
![image](https://github.com/user-attachments/assets/4910172a-e4b8-49de-81e9-678cb0662f93)

     -  해당 옵션을 Always allowed로 설정하면 모든 HTTP요청을 허용할 수 있음
      




