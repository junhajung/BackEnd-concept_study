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
