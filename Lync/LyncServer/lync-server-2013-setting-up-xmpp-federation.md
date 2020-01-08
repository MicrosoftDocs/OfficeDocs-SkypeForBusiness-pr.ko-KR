---
title: 'Lync Server 2013: XMPP 페더레이션 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013에서 XMPP 페더레이션 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-03_

Edge 서버에서 XMPP 프록시를 배포 하려면 XMPP 페더레이션에 대 한 Edge 서버를 구성 해야 합니다. 이 작업을 수행 하려면 다음 단계를 수행 합니다.

<div>

## <a name="setting-up-xmpp-federation"></a>XMPP 페더레이션 설정

1.  Lync Server 배포 마법사가 설치 되어 있는 컴퓨터에 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.

2.  프런트 엔드 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다. 다시 실행을 클릭 합니다.

3.  Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다. 마침을 클릭 하 여 배포를 완료 합니다.

4.  Edge 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다. 다시 실행을 클릭 합니다.

5.  Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다. 마침을 클릭 하 여 배포를 완료 합니다.

6.  Edge 서버에서 배포 마법사의 3 단계: 인증서 요청, 설치 또는 할당에서 다음을 다시 실행을 클릭 합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > Edge 서버를 처음 배포 하는 경우에는가 다시 실행 되는 대신 실행이 표시 됩니다.

    
    </div>

7.  사용 가능한 인증서 작업 페이지에서 새 인증서 요청 만들기를 클릭 합니다.

8.  인증서 요청 페이지에서 외부에 지 인증서를 클릭 합니다.

9.  지연 또는 즉시 요청 페이지에서 지금 요청 준비, 나중에 보내기 확인란을 선택 합니다.

10. 인증서 요청 파일 페이지에서 요청을 저장할 파일의 전체 경로와 파일 이름을 입력 합니다 (예: c:\\cert\_외부\_가장자리만).

11. 대체 인증서 템플릿 지정 페이지에서 기본 WebServer 템플릿 이외의 서식 파일을 사용 하려면 선택한 인증 기관에 대체 인증서 서식 파일 사용 확인란을 선택 합니다.

12. 이름 및 보안 설정 페이지에서 다음을 수행 합니다.
    
    1.  대화명에 인증서의 표시 이름을 입력 합니다.
    
    2.  비트 길이에서 비트 길이를 지정 합니다 (일반적으로 2048의 기본값).
    
    3.  인증서 개인 키를 내보낼 수 있도록 표시 확인란을 선택 했는지 확인

13. 조직 정보 페이지에서 조직과 조직 구성 단위 이름 (예: 부서 또는 부서)을 입력 합니다.

14. 지역 정보 페이지에서 위치 정보를 지정 합니다.

15. 제목 이름/주체 대체 이름 페이지에 마법사에서 자동으로 채워지는 정보가 표시 됩니다. 추가 주제 대체 이름이 필요한 경우 다음 두 단계에서 지정 합니다.

16. SIP 도메인 설정의 San (주체 대체 이름) 페이지에서 도메인 확인란을 선택 하 여 sip를 추가 합니다. \<주제\> 대체 이름 목록에 항목을 sipdomain.

17. 추가 주제 대체 이름 구성 페이지에서 필요한 추가 주체 대체 이름을 지정 합니다.
    
    <div class=" ">
    

    > [!TIP]  
    > XMPP 프록시를 설치 하면 기본적으로 도메인 이름 (예: contoso.com)이 SAN 항목에 채워집니다. 더 많은 항목이 필요한 경우이 단계에서 추가 합니다.

    
    </div>

18. 요청 요약 페이지에서 요청을 생성 하는 데 사용할 인증서 정보를 검토 합니다.

19. 명령 실행이 완료 되 면 로그를 보거나 다음을 클릭 하 여 계속 진행할 수 있습니다.

20. 인증서 요청 파일 페이지에서 마침을 클릭 하 여 인증서 마법사를 종료 하 고 보기를 클릭 하 여 생성 된 CSR (인증서 서명 요청) 파일을 볼 수 있습니다.

21. 요청 파일을 복사 하 고 공용 인증 기관에 제출 합니다.

22. 공개 인증서를 받고, 가져오고, 할당 한 후에는 Edge 서버 서비스를 중지 하 고 다시 시작 해야 합니다. Lync Server 관리 콘솔에서 입력 하 여 다음을 수행 합니다.
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. XMPP 페더레이션을 위해 DNS를 구성 하려면 외부 DNS:\_xmpp-server에 다음 SRV 레코드를 추가 합니다. \_tcp. \<도메인 이름\> SRV 레코드가 EDGE 서버의 액세스 가장자리 FQDN으로 확인 되며 포트 값은 5269입니다. 또한 액세스에 지 서버의 IP 주소를 가리키는 ' A ' 호스트 레코드 (예: xmpp.contoso.com)를 구성할 수 있습니다.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 여러 사이트에 Edge 풀을 사용 하는 경우 XMPP 페더레이션에 대해 여러 개의 SRV 레코드를 추가 하는 것이 좋습니다. 조직의 모든 Edge 풀에 대해 SRV 레코드를 추가 하 고 각 SRV 레코드에 다른 우선 순위를 부여 합니다. 모든 Edge 풀이 실행 되는 경우 XMPP 요청은 첫 번째 우선 순위로 Edge 풀에서 처리 되지만 해당 Edge 풀이 중단 되 면 XMPP 페더레이션 기능을 다시 가져오기 위해 새 SRV 레코드를 추가 해야 합니다.

    
    </div>

24. 프런트 엔드에서 Lync Server Management Shell을 열고 입력 하 여 모든 사용자를 사용할 수 있도록 하는 새 외부 액세스 정책을 구성 합니다.
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    다음과 같이 입력 하 여 외부 사용자에 대해 XMPP 액세스를 사용 하도록 설정 합니다.
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. XMPP 프록시가 배포 되는 Edge 서버에서 명령 프롬프트 또는 Windows PowerShell™ 명령줄 인터페이스를 열고 다음을 입력 합니다.
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    명령 매개 변수 – **ano** 는 네트워크 통계 명령으로, 모든 연결 및 수신 대기 포트, 주소 및 포트를 표시 하는 **ano** 요청을 숫자 형식으로 표시 하 고 소유 프로세스 ID가 각 연결에 연결 되어 있습니다. 문자 **|** 는 다음 command, **findstr**또는 find 문자열에 대 한 파이프를 정의 합니다. Findstr에 매개 변수로 전달 되는 숫자 5269 및 23456는 문자열 5269 및 23456에 대 한 netstat의 출력을 검색 하도록 findstr에 지시 합니다. XMPP가 올바르게 구성 되어 있으면 명령 결과에 Edge 서버의 외부 (포트 5269) 및 내부 (포트 23456) 인터페이스를 통해 연결을 수신 하 고 설정 해야 합니다.
    
    명령에 설정 된 포트나 수신 대기 하는 포트 (5269 및 23456)가 반환 되지 않으면 다음을 확인 합니다.

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP 페더레이션 문제 해결

1.  XMPP 프록시가 실행 중인지 확인 하려면 다음을 수행 합니다.

2.  XMPP 프록시 서비스를 로컬 관리자 그룹의 구성원으로 실행 하는 Edge 서버에 로그온 합니다.

3.  **시작**, **모든 프로그램**, **관리 도구**, **서비스** 를 차례로 클릭 합니다.

4.  서비스에서 Lync Server XMPP 번역 게이트웨이 프록시를 찾습니다. 서비스는 **시작 됨** 상태 여야 합니다. 시작 되지 않은 경우 도구 모음에서 **시작** 아이콘을 클릭 합니다. 아이콘이 녹색으로 오른쪽을 가리키는 화살표로 표시 됩니다.

5.  서비스가 **시작**됨으로 변경 되었는지 확인 합니다. 성공적으로 시작 되 면 **서비스** 를 종료 하 고 계속 합니다.
    
    서비스를 성공적으로 시작 하지 않은 경우 관리 도구에서 이벤트 뷰어를 열고 **응용 프로그램 및 서비스 로그**의 **Lync Server** 부분에서 오류 및 경고를 참조 하세요.

6.  **Lync Server XMPP 번역 게이트웨이** 서비스가 실행 되 고 나면 이전에 사용 된 netstat 명령을 다시 검사 합니다. 설정 또는 수신 대기 중인 세션이 표시 되지 않는 경우 토폴로지 작성기에서 **Xmpp 페더레이션 경로가** 올바르게 구성 되어 있는지 확인 합니다.

7.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

8.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

9.  토폴로지 작성기에서 xmpp 페더레이션 경로의 사이트를 선택 하 고 검토를 통해 **xmpp 페더레이션** 에 대 한 **사이트 페더레이션 경로 할당이** 선택한 xmpp 페더레이션 경로 할당으로 edge 서버 또는 edge 풀을 표시 하는지 확인 합니다.
    
    경로 할당이 올바르지 않거나 설정 되어 있지 않으면 사이트를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다. XMPP 페더레이션 확인란을 선택 하 고 올바른 Edge 서버 또는 Edge 풀을 선택 합니다.

10. 토폴로지를 게시 합니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-your-topology.md) 를 참조 하세요.
    
    <div class=" ">
    

    > [!TIP]  
    > 필수는 아니지만 일반적으로 필요 하지는 않지만 Edge 서버를 다시 시작 해야 하는 경우가 있을 수 있습니다.

    
    </div>

11. 이전에 사용 된 netstat 프로세스를 사용 하 여 Edge 서버가 지금 수신 대기 중이거나 포트 5269 및 포트 23456에서 세션을 설정 했는지 확인 합니다.

12. 여전히 예상 되는 세션이 표시 되지 않으면 통신 문제가 발생할 수 있는 원인이 이벤트 뷰어를 확인 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

