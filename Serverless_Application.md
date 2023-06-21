# aws 를 이용한 서버리스


-서버리스(serverless)란 개발자가 서버를 관리할 필요 없이 애플리케이션을 빌드하고 실행할 수 있도록 하는 클라우드 네이티브 개발 모델입니다.

- 서버리스 모델에도 서버가 존재하긴 하지만, 애플리케이션 개발에서와 달리 추상화되어 있습니다.


![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/1e3f3b40-0a02-49a6-ad06-6d9b3cf34b54)


![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/7dc39da5-a0d4-43af-90ad-d407bbcbc4af)


## aws를 이용한, credentials 만들기


- aws 콘솔에 로그인후
- IAM 대시보드를 검색해서 들어갑니다.
- 
![20230621_094529](https://github.com/ijd1236/Serverless_Application/assets/130967884/94dff875-96a1-4d36-bf7f-c6a8cad8c676)

![20230621_094547](https://github.com/ijd1236/Serverless_Application/assets/130967884/3ef3e5b5-3176-4a2a-b63e-d823ad29e62d)

- 그후 좌측에서 사용자를 클릭후 사용자 추가 클릭

![20230621_094817](https://github.com/ijd1236/Serverless_Application/assets/130967884/2e89de22-04ed-4319-a03f-dbd31cc3039c)

- 사용자 이름 입력후 다음 클릭

![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/9ad7d3ad-01ac-4053-93d2-9eb4fb67a2f6)


![20230621_095227](https://github.com/ijd1236/Serverless_Application/assets/130967884/8f40ffcc-1b9f-4c0f-b38f-6ff9a2b27366)

- 직접 정책 연결을 선택후 음 권한을 검색한후 체크하고 다음을 클릭해서 넘어갑니다

![20230621_095419](https://github.com/ijd1236/Serverless_Application/assets/130967884/7711de84-09b1-4842-af51-6e2edac7814f)


- 체크 완료 리스트를 확인하고 사용자생성 클릭

![20230621_095430](https://github.com/ijd1236/Serverless_Application/assets/130967884/249e2432-199c-41a9-84a6-1808e0c152e1)


- 생성이 완료된 내용을 확인후 해당 credentials을 클릭해서 들어갑니다.

![20230621_100827](https://github.com/ijd1236/Serverless_Application/assets/130967884/862d226f-744e-4b17-8659-9f0fed0071b1)


![20230621_100948](https://github.com/ijd1236/Serverless_Application/assets/130967884/215bda91-f176-4d0c-b7b7-6deeaa15db0c)

- 보안 자격 증명에서 엑세스키 만들기 클릭 -> 로컬코드를 (큰 상관은 없다)선택한후 다음을 클릭해서 넘어갑니다

![20230621_101006](https://github.com/ijd1236/Serverless_Application/assets/130967884/edaa6083-6802-4639-8635-dbe6ed3d88af)

- 엑세스 키 만들기를 클릭하여 키를 만듭니다 (설명 태그 값음 안넣어도됩니다)

![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/bd93d886-a1a2-43e0-bca8-95e41e3f95f4)


- 키가 생성되었습니다 생성된키를  csv 파일 다운로드를 눌러 다운받습니다.


## AWS에 배포하기 위한 Serverless framework 설치

https://www.serverless.com/framework/docs/getting-started

- 위 링크의 사이트에 들어갑니다

![20230621_101810](https://github.com/ijd1236/Serverless_Application/assets/130967884/5054138f-6a3d-4b3a-a8e7-841e6098fb02)

- 먼저 서버리스 프로그렘을 설치해야합니다  install first를 누릅니다


![20230621_101832](https://github.com/ijd1236/Serverless_Application/assets/130967884/24bebfe0-ffc3-4672-8a00-1151db99ccac)

- 18.16.1 LTS 를 클릭하여 다운로드 받습니다.


![20230621_103320](https://github.com/ijd1236/Serverless_Application/assets/130967884/a39af734-6299-4617-85a4-0f1920bab621)


- 다운로드가 완료되면 Anaconda Prompt에서 npm install -g serverless 를 입력해 서버리스 프로그렘을 설치합니다.

- 이제 Serverless framework 에 로그인하여 key 와환경을 app을 등록하겠습니다

![20230621_103603](https://github.com/ijd1236/Serverless_Application/assets/130967884/a35ad696-4788-4f3c-92e1-8cdfb0b8c189)
![20230621_105640](https://github.com/ijd1236/Serverless_Application/assets/130967884/971d216c-1d42-413d-9640-d5b8b7b06900)

- 먼저 로그인 화면에서 org를 클릭 providers에서  add를 눌러 키를 추가합니다.
- 
![20230621_110247](https://github.com/ijd1236/Serverless_Application/assets/130967884/2f2728af-21fa-4e5f-802d-4541d8724474)

- 여기서 이름은 위 aws  credentials 에서 입력한 이름 Access , Secret Key 는 위에서 csv파일에 받았던 Key를 입력해줍니다.


- 다음은 app을 만들어줍니다.
- 
![20230621_103725](https://github.com/ijd1236/Serverless_Application/assets/130967884/b397f9da-3bea-45cb-9dc5-02fe59e9562d)

- apps 에서 create  app을 클릭,

![20230621_104028](https://github.com/ijd1236/Serverless_Application/assets/130967884/093457df-1ad3-4486-a472-e83c03ca9c8a)

- python flask API 를 선택합니다

![20230621_104222](https://github.com/ijd1236/Serverless_Application/assets/130967884/4af6a4bf-a383-4f4f-b5d6-e6298aec6bbc)


- app 제목을 입력하고 create를 누릅니다

![20230621_104651](https://github.com/ijd1236/Serverless_Application/assets/130967884/72211d2c-d780-4675-8ed9-b6dbf2867713)

- 그럼 이런 코드들이 나오는데 이걸 그대로 사용하면 윈도우에서 적용되지 않으므로 해당 코드를 복사후 수정하는 과정을 거칩니다

![20230621_105005](https://github.com/ijd1236/Serverless_Application/assets/130967884/d184c6ad-3036-45f6-8ff1-68b31de7445e)

- 다음과 같이 #(백슬레쉬)를 지우고 한줄이 되게 붙입니다.

![20230621_105006](https://github.com/ijd1236/Serverless_Application/assets/130967884/0988ee34-eb34-46dc-a546-1df01bc022cd)

![20230621_105512](https://github.com/ijd1236/Serverless_Application/assets/130967884/6b59b36f-fffe-4d23-90d3-3acef0148158)
![20230621_112316](https://github.com/ijd1236/Serverless_Application/assets/130967884/5adfa3fd-e252-48b5-9067-1258e349c19e)


- 이후 anaconda prompt 에서 GitHub 경로로 들어간 후 위에서 만들어둔 코드를 입력하여 serverless 를 설치합니다. (app의 제목의 폴더가 GitHub 폴더에 만들어집니다)

![20230621_112332](https://github.com/ijd1236/Serverless_Application/assets/130967884/ac46faff-dc89-4278-b341-b16c3a47c57f)


- 그 다음 만들어진 폴더의 경로로 들어가 sls deploy 를 입력해 배포합니다.

![20230621_112339](https://github.com/ijd1236/Serverless_Application/assets/130967884/e205978a-81dc-4b39-ae61-a176cbc81580)

![20230621_112340](https://github.com/ijd1236/Serverless_Application/assets/130967884/300b252a-221c-4d8f-8570-7fd08d41c734)


- 배포가 완료되면 엔드포인트에 주소가 나오는데 해당 주소를 검색창에 입력하여 들어가고 성공적으로 입력된지 확인합니다.

## vs코드 작업과

- 먼저 vs코드에서 Severless 로 실행하기 위한 작업을 합니다.

- 기존에 만들었던 recipe 데이터베이스를 사용합니다.

- vs코드에서 폴더 열기로 위에서 만든 aws-recipe-app을 엽니다

![20230621_145705](https://github.com/ijd1236/Serverless_Application/assets/130967884/9fdad360-7aa0-4392-b406-3437660056a9)

- requirements.txt 에서 기존 recipe API 에서 사용했던 라이브러리들을 입력합니다.


![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/bf7f906b-c092-4b5d-acc8-d4fb41bb0000)

- 기존 recipe vs코드의 파일들을  aws-recipe-app에 복사해서 옮겨줍니다

![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/e82b7b58-5fe1-4c44-9a5b-4a42f0fdf144)

- gitignoere에는 다음과 같이node_modules를 입력해줍니다


![20230621_150539](https://github.com/ijd1236/Serverless_Application/assets/130967884/fea4753f-194a-44b4-b884-89d202c03e69)

![20230621_152649](https://github.com/ijd1236/Serverless_Application/assets/130967884/b5bdfa4d-7217-4099-94e0-d07919405a22)

- 이후 가상환경에서 sls deploy 를 입력해 배포한 다음 주소가 나오고 완료된걸 확인합니다.

![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/7881bd41-174b-4cc0-a6ab-f4ade3b9c7e6)

- 포스트맨에서 vs코드에서 나온 엔드포인트를 주소를 입력하고 정상적으로 작동하는지 확인합니다.


## 깃허브 연동하기


![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/39bfa058-a8ab-4c07-8923-45bf893fa402)

- 깃허브 레파지토리를 프라이빗으로 설정하고 만들어줍니다.


![20230621_164030](https://github.com/ijd1236/Serverless_Application/assets/130967884/c561b892-4649-4180-a23e-c8cf11fa2a03)

- 그럼 위와 같이 나오는데 vs코드에서 command line 에 나온 코드들을 입력해 클론할 수 있습니다

![20230621_164722](https://github.com/ijd1236/Serverless_Application/assets/130967884/f9cb5422-74e1-46c5-b49c-a0a277fc15db)

- 먼저 git init 를 입력하면 위와 같이 커밋 할 수 있게 나옵니다. 파일들을 커밋해줍니다.
- 이후 git branch -M main(푸시할 경로 만들기)  ,  git remote add origin https://github.com/ijd1236/aws-recipe-app.git(커밋할 주소랑 연결) 을 순서대로 입력하고
- vs코드에서 푸시를 누르거나  터미널에서 git push -u origin main를 입력합니다.

![image](https://github.com/ijd1236/Serverless_Application/assets/130967884/e3ba797a-c609-4338-8d01-cd9cb8b0847c)

- 푸시가 완료되면 잘되었는지 확인합니다









- 

