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

![20230621_104028](https://github.com/ijd1236/Serverless_Application/assets/130967884/e62a0455-b9e6-4d44-89c9-3ad768fc15b2)





- 

