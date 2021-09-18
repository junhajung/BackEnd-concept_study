- Ubuntu
  - [Ubuntu 설치](#Ubuntu-설치)
  - [Ubuntu github 연동 및 사용](#Ubuntu-github-사용법)  

# Ubuntu 설치

1. 우분투 사이트에서 설치용 iso 파일 다운로드   
<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133873957-9c7bd443-3faa-4999-b449-655b52560b79.png" width="80%" height="80%"/>
</p>

<p align="center">
- 설치 사이트 : https://ubuntu.com/#download  <br/>
- 다운로드 파일 정보 : 2.8G  
</p>

2. USB installer를 다운로드한 후 설치 파일을 실행  
<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133874092-96f7fc3c-0fe6-48a4-ae63-e13984025cf1.png" width="50%" height="50%"/>
</p>

<p align="center">
- Step1 : Ubuntu 선택   <br/>
- Step2 : iso 파일 다운로드 받은 경로 선택   <br/>
- Step3 : 다운로드 받은 USB 위치 선택   <br/> <br/>
- 설치 사이트 : https://universal-usb-installer.kr.uptodown.com/windows   <br/>
다운로드한 리눅스 설치용 iso 파일을 usb에 구성하여 설치할 수 있도록 도와주는 파일  
</p>

3. 리눅스 설치할 디스크 드라이브 구성 및 용량 할당  
<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133876812-5ef4297e-9502-42a7-b560-3d0eab356911.png" width="80%" height="80%" />
</p>
<p align="center">
  제어판 - 시스템 및 보안 - 관리 도구 - 하드 디스크 파티션 만들기
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877445-f0a104ab-2c78-473f-bb94-22d60027813e.png" width="600px" height="500px"/>
</p>
<p align="center">
- 할당 할 공간에 마우스 우클릭 후 볼륨 축소 클릭 <br/>
- 축소할 공간 : 60000
</p>

4. 윈도우 OS 종료 설정 및 BIOS에서 Secure Boot 옵션 변경
<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877519-13633312-8385-429d-add3-4c1c967f96be.png" width="80%" height="80%"/>
</p>
<p align="center">
제어판 - 하드웨어 및 소리 - 전원 옵션 - 전원 단추 동작 변경 - 빠른 시작 켜기 해제  
</p>

5. 윈도우 다시 시작  
<p align="center">
- BIOS 진입을 위해 F2키를 누른다. <br/>
- Security 메뉴의 Secure Boot Configuration Disabled로 설정 <br/>
- Boot에서 우선운위를 Window에서 리눅스 설치용 USB가 먼저오도록 1순위를 변경 <br/>
- 저장 후 다시 시작 <br/>
</p>

6. BIOS에서 Ubutu 설정 후 재실행 설정  
<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877628-33157698-ea60-4467-b0bb-f46fbe93f255.png" width="80%" height="80%"/>
</p>
<p align="center">
언어 한국어 설정, 우분투 설치 선택  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877654-b06478fa-ba8b-44ca-97cb-742036159181.png" width="80%" height="80%"/>
</p>
<p align="center">
키보드 한국어 설정  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877692-97114ea1-af9d-47c2-9989-870285d6c11d.png" width="80%" height="80%"/>
</p>
<p align="center">
설치 유형 일반 설치  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877705-a2504884-a79b-46e6-be01-6c2da39a65d3.png" width="80%" height="80%"/>
</p>
<p align="center">
 우분투가 사용할 파티션을 만들고 크기 옵션을 지정할 것이기 때문에 '기타' 유형을 선택  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877725-44e5ef27-d196-4eec-91a2-ea4195017ed0.png" width="80%" height="80%"/>
</p>
<p align="center">
 - 리눅스 OS 설치를 위해 할당한 공간인 '남은 공간'을 선택한 후 + 버튼을 클릭   <br/>
 - 스왑 영역의 공간을 할당 ( 가상 메모리로 사용되는 부분 )  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877783-7245050e-8ccd-46aa-bc63-9c89b5031ef8.png" width="80%" height="80%"/>
</p>
<p align="center">
저널링 파일 시스템 파티션 할당  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877801-a16e6e7b-aca0-4ba1-b647-a30875522ca4.png" width="80%" height="80%"/>
</p>
<p align="center">
 /home 영역 할당  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877817-f1a5cf15-ce0e-4c79-bc17-f7a3757fb175.png" width="80%" height="80%"/>
</p>
<p align="center">
 파티션 세팅된 최종 모습  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877827-a4b0fdc6-96b6-4f10-bb64-40bb8f58d5e8.png" width="80%" height="80%"/>
</p>
<p align="center">
 변경할 파티션의 초종 정보를 보여준다. 계속하기 클릭  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877847-fd6fff61-5513-4bdc-95e6-f7356b61a6c2.png" width="80%" height="80%"/>
</p>
<p align="center">
 OS계정 및 패스워드를 입력  
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/48474613/133877857-1e46bc0e-650f-40ca-9c8b-36aa45f7adbb.png" width="80%" height="80%"/>
</p>
<p align="center">
 설치 완료  
</p>

++ 출처 및 참고 사이트
https://dreamdeveloper403.tistory.com/28

# Ubuntu github 사용법

1. github 설치  
![스크린샷, 2021-09-18 13-36-58](https://user-images.githubusercontent.com/48474613/133872615-156419fa-f0bb-4535-a2d6-a28bd891ea93.png)  
-> sudo apt-get install git-core  

2. github 개인 정보 등록  
![스크린샷, 2021-09-18 13-38-40](https://user-images.githubusercontent.com/48474613/133872660-8e8e6679-1385-4577-a4e4-192608a67c9d.png)  
-> sudo git config --global user.name "본인 계정 이름"  
-> sudo git config --global user.email "본인 계정 이메일"

3. Git 작업 폴더 생성  
![스크린샷, 2021-09-18 13-41-25](https://user-images.githubusercontent.com/48474613/133872732-0d70dd20-2055-4f4e-a623-7e95bf3f0a0e.png)  
-> sudo mkdir 만들폴더이름  

4. 만든 폴더로 이동  
cd Ubuntu  

5. 만든 폴더 속에서 파일 생성  
![스크린샷, 2021-09-18 13-43-49](https://user-images.githubusercontent.com/48474613/133872788-1492a342-33a6-4594-8f28-8d6f675e2157.png)  
-> gedit README.md  

6. 변경 파일 add  
![스크린샷, 2021-09-18 13-45-12](https://user-images.githubusercontent.com/48474613/133872850-209dc441-7af2-413f-bff9-ee63127781d3.png)  

7. 커밋 메세지 작성 후 commit  
![스크린샷, 2021-09-18 13-46-56](https://user-images.githubusercontent.com/48474613/133872882-81fc23df-6a55-4c36-8113-38183a7fcf34.png)  
-m 뒤에 커밋 메세지 작성

8. git push  
![스크린샷, 2021-09-18 13-49-17](https://user-images.githubusercontent.com/48474613/133872924-4e1d7a97-be8b-4808-bb93-111002936433.png)  
저장소로 push


## git push시 인증 실패 에러 발생 해결법 (엑세스 토큰 발급)  
1. 깃허브 접속 후 프로필 영역에 접근한 후에 Settings로 진입  
![스크린샷, 2021-09-18 13-51-00](https://user-images.githubusercontent.com/48474613/133872964-3aa0cab4-af6f-42ba-8ba8-a2a06abc7e52.png)    

2. 왼쪽 하단에 Developer settings 메뉴로 진입  
![스크린샷, 2021-09-18 13-52-24](https://user-images.githubusercontent.com/48474613/133872986-ce5e08ec-7f92-47d3-8b12-c90af02605c9.png)  

3. Personal access tokens에 들어간 후 생성  
![스크린샷, 2021-09-18 13-53-27](https://user-images.githubusercontent.com/48474613/133873033-61e805f3-d4bd-4304-9b65-a8cb19d6ab09.png)  
- Note : 토큰의 사용 용도에 맞게 이름 입력  
- Expiration : 토큰의 만료 일자  
- Select scopes : 부여할 권한 설정!  


![스크린샷, 2021-09-18 14-01-17](https://user-images.githubusercontent.com/48474613/133873261-74d39ecd-894e-416f-9b42-3b8ad65fb171.png)


### 해당 발급된 키를 인증 암호에 입력시 엑세스 가능
