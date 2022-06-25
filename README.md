# TTS-example
WebOS TTS 예제

----setting----
1. Google cloud 계정에 로그인/회원가입(학교 카드 사용 가능 -> 돈 안듦)
2. 새 프로젝트 만들기 혹은 기존 프로젝트 사용
3. API 및 서비스 -> 라이브러리 에 들어가서 Cloud Text-to-Speech API 사용설정
4. IAM 및 관리자 -> 서비스 계정 에 들어가서 서비스 계정 만들기
5. 서비스 계정 세부정보의 서비스 계정 ID는 중요하지 않은듯 보임 -> 아무렇게나 해도 될듯?
6. 이 서비스 계정에 프로젝트에 대한 엑세스 권한 부여에서 소유자 역할 부여
7. 서비스 계정 만들기 완료
8. 서비스 계정 -> 작업 -> 키 관리 -> 키 추가 -> 새 키 만들기 -> JSON -> 만들기
9. ares-shell -d <디바이스>를 통해 webos에 접속
10. mkdir /etc/google 을 통해서 파일 생성 (sudo 필요 없고, 심지어 없음 ㅎ)
11. cd /etc/google을 통해서 파일에 들어간 후 vi google_tts_credentials.json 를 통해서 파일을 생성함과 동시에 JSON파일에 있던 내용을 복사하여 그대로 붙여넣어준다.(참고로 제대로 복사가 안되는 경우가 많으니, 타이핑이 필요합니다., 그리고 nano 없어요)

----appinfo.json----
우리는 com.webos.service.tts를 사용할 것이기 때문에 requiredPermissions에 tts.operation을 추가해줘야합니다. (혹은 all을 통해서 모든 권한을 활성화할 수 있는 것으로 보여집니다.)

----index.html----
speak()라는 사용자 지정함수를 만들어줘서 tt
