
1. UI에서 업데이트 된 구성을 옵션을 표시 하려면 IIS 관리 콘솔을 닫았다가 다시 합니다.

1. IIS에서 마우스 오른쪽 단추로 클릭 합니다 **기본 웹 사이트**, 선택 **배포** > **구성 웹 배포 게시**합니다.

    ![웹 배포 구성](../../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. 에 **구성할 웹 배포 게시** 대화 상자에서 설정을 검토 합니다.

1. 클릭 **설치**합니다.

    에 **결과** 패널 권한이 되었음이 출력에 표시 하 고 지정된 된 사용자에 부여 됩니다 인 파일을 *.publishsettings* 대화 상자에 표시 된 위치에 생성 된 파일 확장명 상자입니다.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    Windows Server 및 IIS 구성에 따라 XML 파일에 다른 값이 표시 됩니다. 표시 되는 값에 대 한 몇 가지 세부 정보는 다음과 같습니다.

    * 합니다 *msdeploy.axd* 파일에서 참조 되는 `publishUrl` 특성은 웹 배포에 대 한 동적으로 생성 된 HTTP 처리기 파일. (테스트 목적으로 `http://myhostname:8172` 일반적으로 잘 작동 합니다.)
    * `publishUrl` 웹 배포에 대 한 기본값인 포트, 8172 포트 설정 됩니다.
    * `destinationAppUrl` 포트 IIS에 대 한 기본값인 포트 80로 설정 됩니다.
    * 호스트 이름 (이후 단계)을 사용 하는 Visual Studio에서 원격 호스트에 연결할 수 없는 경우 호스트 이름 대신 IP 주소를 테스트 합니다.

    > [!NOTE]
    > Azure VM에서 실행 되는 IIS에 게시 하는 경우 웹 배포 및 IIS 포트에서에서 열어야 네트워크 보안 그룹입니다. 자세한 내용은 [설치 및 실행된 IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic)합니다.

1. Visual Studio를 실행 중인 컴퓨터에이 파일을 복사 합니다.
