---
title: 'Lync Server 2013: XMPP 페더레이션 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497525"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 페더레이션 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-03_

에지 서버에 XMPP 프록시를 배포하려면 XMPP 페더레이션의 에지 서버를 구성해야 합니다. 이렇게 하려면 다음 단계를 수행합니다.

<div>

## <a name="setting-up-xmpp-federation"></a>XMPP 페더레이션 설정

1.  Lync Server 배포 마법사가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  프런트 엔드 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭한 후 Lync Server 구성 요소 설치 또는 제거를 클릭합니다. 다시 실행을 클릭합니다.

3.  Lync Server 구성 요소 설치에서 다음을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 로그 보기를 클릭하여 사용 가능한 로그 파일을 확인합니다. 마침을 클릭하여 배포를 완료합니다.

4.  에지 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭한 후 Lync Server 구성 요소 설치 또는 제거를 클릭합니다. 다시 실행을 클릭합니다.

5.  Lync Server 구성 요소 설치에서 다음을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 로그 보기를 클릭하여 사용 가능한 로그 파일을 확인합니다. 마침을 클릭하여 배포를 완료합니다.

6.  에지 서버의 배포 마법사에서 3단계: 인증서 요청, 설치 또는 지정 옆에 있는 다시 실행을 클릭합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > 에지 서버를 처음 배포하는 경우 다시 실행 대신 실행이 표시됩니다.

    
    </div>

7.  사용할 수 있는 인증서 작업 페이지에서 새 인증서 요청 만들기를 클릭합니다.

8.  인증서 요청 페이지에서 외부에 지 인증서를 클릭 합니다.

9.  지연 또는 즉시 요청 페이지에서 지금 요청을 준비하고 나중에 보냅니다 확인란을 선택합니다.

10. 인증서 요청 파일 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예를 들어, c: \\ cert 외부에 있는 \_ \_ .cer).

11. 대체 인증서 템플릿 지정 페이지에서 기본 WebServer 템플릿이 아닌 다른 템플릿을 사용하려면 선택한 인증 기관에 대체 인증서 템플릿 사용 확인란을 선택합니다.

12. 이름 및 보안 설정 페이지에서 다음을 수행합니다.
    
    1.  이름에 인증서 표시 이름을 입력합니다.
    
    2.  비트 길이에서 비트 길이(일반적으로 기본값은 2048)를 지정합니다.
    
    3.  인증서의 개인 키를 내보낼 수 있는 것으로 표시 확인란이 선택되어 있는지 확인합니다.

13. 조직 정보 페이지에 조직 및 조직 구성 단위의 이름(예: 사업부 또는 부서)을 입력합니다.

14. 지역 정보 페이지에서 위치 정보를 지정합니다.

15. 주체 이름/주체 대체 이름 페이지에 마법사에서 자동으로 채울 정보가 표시됩니다. 추가 주체 대체 이름이 필요한 경우 다음 두 단계에서 지정합니다.

16. 주체 대체 이름 (San)에 대 한 SIP 도메인 설정 페이지에서 sip를 추가 하려면 도메인 확인란을 선택 합니다.\<sipdomain\> 주체 대체 이름 목록에 항목을 입력 합니다.

17. 추가 주체 대체 이름 구성 페이지에서 필요한 추가 주체 대체 이름을 지정합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > XMPP 프록시가 설치된 경우 기본적으로 도메인 이름(예: contoso.com)이 SAN 항목에 채워집니다. 추가 항목이 필요하면 이 단계에서 추가합니다.

    
    </div>

18. 요청 요약 페이지에서 요청을 생성하는 데 사용할 인증서 정보를 검토합니다.

19. 명령 실행이 완료되면 로그를 보거나 다음을 클릭하여 계속할 수 있습니다.

20. 인증서 요청 파일 페이지에서 보기를 클릭하여 생성된 CSR(인증서 서명 요청) 파일을 보거나 마침을 클릭하여 인증서 마법사를 종료할 수 있습니다.

21. 요청 파일을 복사하고 공용 인증 기관에 제출합니다.

22. 공용 인증서를 받아 가져오고 할당한 후 에지 서버 서비스를 중지한 다음 다시 시작해야 합니다. 이는 Lync Server 관리 콘솔에서 다음을 입력해서 수행할 수도 있습니다.
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. XMPP 페더레이션을 사용 하도록 DNS를 구성 하려면 외부 DNS: \_ xmpp-server에 다음 SRV 레코드를 추가 합니다. \_ rdp-tcp.\<domain name\> SRV 레코드는 포트 값이 5269 인에 지 서버의 액세스에 지 FQDN을 확인 합니다. 또한 액세스에 지 서버의 IP 주소를 가리키는 ' A ' 호스트 레코드 (예: xmpp.contoso.com)를 구성 합니다.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 여러 사이트에 에지 풀이 있는 경우 XMPP 페더레이션에 대해 여러 SRV 레코드를 추가하는 것이 좋습니다. 조직 내 모든 에지 풀에 대해 SRV 레코드를 추가하고 이러한 각 SRV 레코드에 서로 다른 우선 순위를 지정합니다. 모든 에지 풀이 실행될 때 XMPP 요청은 우선 순위가 가장 높은 에지 풀에서 처리됩니다. 하지만 해당 에지 풀이 다운된 경우 XMPP 페더레이션 기능을 다시 확보하기 위해 새로운 SRV 레코드를 추가할 필요가 없습니다.

    
    </div>

24. 프런트 엔드에서 Lync Server 관리 셸을 열고 다음을 입력하여 모든 사용자를 사용하도록 설정하기 위해 새로운 외부 액세스 정책을 구성합니다.
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    다음을 입력하여 외부 사용자에 대해 XMPP 액세스를 사용하도록 설정합니다.
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. XMPP 프록시가 배포 되는에 지 서버에서 명령 프롬프트나 Windows PowerShell™ 명령줄 인터페이스를 열고 다음을 입력 합니다.
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    **Netstat – ano** 명령은 네트워크 통계 명령, netstat가 모든 연결 및 수신 대기 포트, 주소 및 포트를 숫자 형식으로 표시 하 고 소유 프로세스 ID가 각 연결과 연결 되도록 하는 매개 변수 **-ano** 요청입니다. 문자는 **|** 다음 command, **findstr**또는 find 문자열에 대 한 파이프를 정의 합니다. Findstr에 매개 변수로 전달 되는 번호 5269 및 23456는 findstr이 문자열 5269 및 23456에 대 한 netstat의 출력을 검색 하도록 지시 합니다. XMPP가 올바르게 구성 되어 있으면 명령 결과에에 지 서버의 외부 (포트 5269) 및 내부 (포트 23456) 인터페이스를 통해 수신 대기 및 설정 된 연결이 생성 됩니다.
    
    명령이 5269 및 23456에서 설정되었거나 수신 대기 중인 포트를 반환하지 않으면 다음을 확인합니다.

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP 페더레이션 문제 해결

1.  XMPP 프록시가 실행 중인지 확인하려면 다음을 수행합니다.

2.  XMPP 프록시 서비스를 실행 중인 에지 서버에 로컬 관리자 그룹의 구성원으로 로그온합니다.

3.  **시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 클릭한 다음 **서비스**를 클릭합니다.

4.  서비스에서 Lync Server XMPP Translating Gateway Proxy를 찾습니다. 이 서비스는 **시작됨** 상태여야 합니다. 시작되지 않았으면 도구 모음에서 **시작** 아이콘을 클릭합니다. 아이콘은 녹색 오른쪽 화살표로 표시됩니다.

5.  서비스가 **시작됨**으로 변경되었는지 확인합니다. 성공적으로 시작되었으면 **서비스**를 닫고 계속합니다.
    
    서비스가 성공적으로 시작되지 않았으면 관리 도구에서 이벤트 뷰어를 열고 **응용 프로그램 및 서비스 로그** 아래의 **Lync Server** 부분에서 오류 및 경로를 확인합니다.

6.  **Lync Server XMPP Translating Gateway** 서비스가 실행되면 이전에 사용한 netstat 명령을 다시 확인합니다. 설정 또는 수신 대기 세션이 표시 되지 않는 경우 토폴로지 작성기에서 **Xmpp 페더레이션 경로가** 올바르게 구성 되어 있는지 확인 하세요.

7.  토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

8.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

9.  토폴로지 작성기에서 XMPP 페더레이션 경로의 사이트를 선택 하 고 검토를 통해 **Xmpp** 페더레이션에 대 한 **사이트 페더레이션 경로** 지정이 선택한 xmpp 페더레이션 경로 할당으로 표시 되는지 확인 합니다.
    
    경로 지정이 잘못되었거나 설정되지 않았으면 사이트를 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭합니다. XMPP 페더레이션 확인란을 선택 하 고 올바른에 지 서버 또는에 지 풀을 선택 합니다.

10. 토폴로지를 게시합니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 를 참조 하세요.
    
    <div class=" ">
    

    > [!TIP]  
    > 필수는 아니지만 일반적으로 필요 하지는 않지만에 지 서버를 다시 시작 해야 할 수 있습니다.

    
    </div>

11. 이전에 사용 된 netstat 프로세스를 사용 하 여 이제에 지 서버가 포트 5269 및 포트 23456의 세션을 수신 대기 중이거나 설정 했는지 확인 합니다.

12. 여전히 예상한 세션이 표시되지 않으면 이벤트 뷰어에서 통신 관련 문제가 있는지 확인합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

