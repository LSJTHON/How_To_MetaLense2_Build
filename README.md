# How_To_MetaLense2_Build
 메타렌즈2 빌드 방법 및 에러로그

Error List 
  1. 키 등록 에러

      ![image](https://github.com/user-attachments/assets/9761c054-808f-456b-bd49-b268fb40e1f8)

     사진처럼 나오거나 콘솔에 Key Store 관련 에러가 나온다면
     Project Settings -> Player -> Publishing Settings의 Project Keysoter 가 있음
     기존 키가 존재하면 비밀번호를 입력하고 빌드하면 해결.
     (비밀번호를 모르겠으면 Keystore Manager...에서 새로운 키를 생성하면 OK

     ![image](https://github.com/user-attachments/assets/2a45c49f-5758-4c54-a1c6-c3deb893aa07)

     First and Last Name 부터 입력하지 않아도 상관없으며 실제 앱 배포 시 신경써야할 부분인거같음

  2. Build And Run Error (미해결)

     ![image](https://github.com/user-attachments/assets/1c2ba1da-40af-4571-8fdb-4b74362aa7aa)

     해당 에러는 build.gradle 파일의 설정값이 잘못되었다는 의미인거같음.

     경로 : 내 프로젝트 폴더 -> Library/Bee/Android/Prj/IL2CPP/Gradle/unityLibrary/src/main/AndroidManifest.xml

     - 초기값
       
        ![image](https://github.com/user-attachments/assets/ff996cd1-194a-463f-b625-2c3be932349f)

     - 수정값
    
        ![image](https://github.com/user-attachments/assets/0af3f936-1545-4329-b557-91d013c6dd5b)

      이렇게 하면 에러를 해결할 수있음. plugins 코드의 위치와 classpath를 적용하려면 buildscript에 집어넣어줄것
      근데 왜 기본 빌드값이 저렇게 나오는지는 모르겠음

     

     
  4. CommandInvokationFailure: Gradle build failed. (미해결)

     ![image](https://github.com/user-attachments/assets/047400f7-69ca-4811-9bc7-00172e7ab063)


  5. UnityEditor.BuildPlayerWindow+BuildMethodException (미해결)

     ![image](https://github.com/user-attachments/assets/588afd30-f880-4083-ad84-e78c311074a4)




     
