
- 이미지: sonatype/nexus3 공식 이미지를 사용합니다.
- 포트 매핑: Nexus의 기본 포트인 8081을 호스트의 8081 포트에 매핑합니다.
- 볼륨: Nexus 데이터를 영구적으로 저장하기 위해 nexus-data 볼륨을 생성하고 컨테이너의 /nexus-data 디렉토리에 마운트합니다.
- 환경 변수: NEXUS_CONTEXT를 설정하여 df-repo의 컨텍스트 경로를 지정합니다.

Docker Compose를 실행합니다:
```shell
docker-compose up -d
```


Nexus가 시작되면 브라우저에서 [http://localhost:8081/nexus/](http://localhost:8081/nexus/) 로 접속할 수 있습니다.
초기 관리자 비밀번호는 다음 명령으로 확인할 수 있습니다:
```shell
docker exec -it nexus cat /nexus-data/admin.password
```

이 구성으로 Nexus를 쉽게 실행하고 관리할 수 있습니다. 필요에 따라 포트나 볼륨 설정을 조정할 수 있습니다