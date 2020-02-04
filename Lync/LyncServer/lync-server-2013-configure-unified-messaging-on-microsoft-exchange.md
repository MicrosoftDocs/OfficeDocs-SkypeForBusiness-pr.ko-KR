---
title: 'Lync Server 2013: Microsoft Exchange에서 통합 메시징 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

이 항목에서는 Enterprise Voice에서 사용할 수 있도록 Microsoft Exchange Server에서 Exchange UM (통합 메시징)를 구성 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> 이 항목의 cmdlet 예제는 exchange 2007 버전의 Exchange 관리 셸에 대 한 구문을 제공 합니다. Exchange 2010 또는 Exchange 2013을 실행 중인 경우에는 해당 설명서를 참조 하세요.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Exchange Server UM을 실행 하는 서버를 구성 하려면

1.  각 엔터프라이즈 음성 위치 프로필에 대 한 SIP (UM 세션 초기화 프로토콜)의 URI (Uniform Resource Identifier) 다이얼 플랜을 만듭니다. Exchange 관리 콘솔을 사용 하도록 선택한 경우 보안 설정 **(기본 설정)** 을 사용 하 여 새 다이얼 플랜을 만듭니다.
    
    <div>
    

    > [!WARNING]  
    > 보안 설정 값을 <STRONG>sip</STRONG> 트래픽 전용으로 암호화를 사용 하도록 설정 하는 경우, 앞에서 권장 하는 것 처럼 프런트 엔드 풀에 암호화가 필요 하도록 구성 된 경우에는이 보안 설정이 충분 하지 않으므로,이는 풀에 SIP 및 RTP 트래픽 모두에 대 한 암호화가 필요 하다는 것을 의미 합니다. 다이얼 플랜 및 풀 보안 설정이 호환 되지 않으면 프런트 엔드 풀에서 Exchange UM에 대 한 모든 호출이 실패 하 고 "호환 되지 않는 보안 설정"이 있음을 나타내는 오류가 발생 합니다.

    
    </div>
    
    Exchange 관리 셸을 사용 하는 경우 다음을 입력 합니다.
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    자세한 내용은 다음을 참조 하세요.
    
      - Office Communications Server 2007의 경우에는 "통합 메시징 SIP URI 다이얼 플랜을 만드는 방법" [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) 및 "새 umdialplan: Exchange 2007 도움말"을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).
    
      - Exchange 2010의 경우에는 "UM 다이얼 플랜 만들기" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) 및 "새 umdialplan 플랜: Exchange 2010 도움말"을 참조 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)하세요.
    
      - Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>SIPSecured</STRONG> 의 보안 수준을 선택 하는지 여부는 보안 실시간 전송 프로토콜 (SRTP)이 미디어 암호화에 대해 활성화 되었는지 여부에 <STRONG>따라 달라 집니다</STRONG> . Lync Server 2010에서 Exchange UM과 통합 하는 경우이는 Lync Server 미디어 구성의 암호화 수준과 일치 해야 합니다. Lync Server 미디어 구성은 <STRONG>CsMediaConfiguration</STRONG> cmdlet을 실행 하 여 볼 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서의 Get-help CsMediaConfiguration을 참조 하세요.<BR>적절 한 VoIP 보안 설정을 선택 하는 방법에 대 한 자세한 내용은 온 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">-프레미스 통합 메시징 및 Lync Server 2013 통합에 대 한 배포 프로세스</A>를 참조 하세요.

    
    </div>

2.  다음 cmdlet을 실행 하 여 각 UM 다이얼 플랜에 대 한 FQDN (정규화 된 도메인 이름)을 가져옵니다.
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    자세한 내용은 다음을 참조 하세요.
    
      - Exchange 2007의 경우에 [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)는 "get-help 다이얼 플랜: Exchange 2007 도움말"을 참조 하세요.
    
      - Exchange 2010의 경우에 [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)는 "get-help 다이얼 플랜: Exchange 2010 도움말"을 참조 하세요.
    
      - Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.

3.  각 UM 다이얼 플랜의 다이얼 플랜 이름을 기록 합니다. 사용 중인 Exchange Server 버전에 따라 다이얼 플랜 이름이 일치 하도록 각 UM 다이얼 플랜의 해당 Lync Server 다이얼 플랜 이름으로 나중에 각 다이얼 플랜 이름에 대 한 FQDN을 사용 해야 할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 다이얼 플랜 이름은 Exchange 2010 SP1 <EM>이전</EM> 버전의 EXCHANGE에서 um 다이얼 플랜을 실행 하는 경우에만 um 다이얼 플랜 이름과 일치 해야 합니다.

    
    </div>

4.  다음과 같이 Exchange UM을 (를) 실행 하는 서버에 다이얼 플랜을 추가 합니다.
    
      - Exchange 관리 콘솔을 사용 하도록 선택한 경우 서버에 대 한 속성 시트에서 다이얼 플랜을 추가할 수 있습니다. 특정 지침은 Exchange Server 제품 설명서를 참조 하세요.
        
        Exchange 2007의 경우, "다이얼 플랜에 통합 메시징 서버를 추가 하는 방법" [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)을 참조 하세요.
        
        Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)"UM 서버의 속성 보기 또는 구성"을 참조 하세요.
        
        Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.
    
      - Exchange 관리 셸을 사용 하는 경우 각 Exchange UM 서버에 대해 다음을 실행 합니다.
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 다음 단계를 수행 하기 전에 모든 Enterprise Voice 사용자가 Exchange Server 사서함으로 구성 되어 있는지 확인 합니다.<BR>Exchange 2007의 경우에 <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>는 exchange Server 2007 TechNet 라이브러리를 참조 하세요.<BR>Exchange 2010의 경우에 <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>는 exchange Server 2010 TechNet 라이브러리를 참조 하세요.<BR>1 단계에서 만든 각 다이얼 플랜에 대 한 사서함 정책을 지정할 때 기본 정책이 나 사용자가 만든 정책 중 하나를 선택 합니다.

    
    </div>

5.  \<Exchange 설치 디렉터리\>\\스크립트로 이동한 다음 exchange를 단일 포리스트에 배포 하는 경우 다음을 입력 합니다.
    ```console
    exchucutil.ps1
    ```
    또는 Exchange가 여러 포리스트에 배포 된 경우 다음을 입력 합니다.
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    여기서 포리스트 FQDN은 Lync 서버가 배포 되는 포리스트를 지정 합니다.
    
    여러 IP 게이트웨이와 연결 된 UM 다이얼 플랜이 하나 이상 있는 경우 6 단계로 넘어갑니다. 다이얼 플랜이 각 IP 게이트웨이와만 연결 되어 있는 경우 6 단계를 건너뜁니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Exchucutil를 실행 <EM>한 후</EM> <STRONG>Lync Server 프런트 엔드</STRONG> 서비스 (rtcsrv)를 다시 시작 해야 합니다. 그렇지 않으면 Lync Server는 토폴로지에서 통합 메시징을 검색 하지 않습니다.

    
    </div>

6.  Exchange 관리 셸 또는 Exchange 관리 콘솔을 사용 하 여 각 다이얼 플랜에 연결 된 IP 게이트웨이 중 하나를 제외 하 고 모두에 대해 아웃 바운드 호출을 사용 하지 않도록 설정할 수도 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계는 전화 접속 시나리오의 경우 처럼 Exchange Server 통합 메시징을 실행 하는 서버에의 한 아웃 바운드 호출이 회사 방화벽을 안정적으로 트래버스 하도록 하기 위해 필요 합니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 나가는 통화를 허용 하는 데 사용할 UM IP 게이트웨이를 선택 하는 경우 대부분의 트래픽을 처리 하는 것을 선택 합니다. Lync Server 디렉터 풀에 연결 하는 IP 게이트웨이를 통해 나가는 트래픽을 허용 하지 않습니다. 또한 다른 중앙 사이트 또는 지점 사이트의 풀을 사용 하지 마세요. 다음 방법 중 하나를 사용 하 여 IP 게이트웨이를 통과 하는 데 나가는 통화를 차단할 수 있습니다.

    
    </div>
    
      - Exchange 관리 셸을 사용 하는 경우 다음 명령을 실행 하 여 각 IP 게이트웨이를 사용 하지 않도록 설정 합니다.
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Exchange 2007의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)"Set UMIPGateway: Exchange 2007 도움말"을 참조 하세요.
        
        Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)"Set UMIPGateway: Exchange 2010 도움말"을 참조 하세요.
    
      - Exchange 관리 콘솔을 사용 하는 경우 **이 IP 게이트웨이를 통해 발신 전화 허용** 확인란의 선택을 취소 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > UM SIP URI 다이얼 플랜을 단일 IP 게이트웨이와만 연결 하는 경우이 게이트웨이를 통해 나가는 호출을 허용 하지 마세요.

    
    </div>

7.  각 Lync Server 다이얼 플랜에 대 한 UM 자동 전화 교환을 만듭니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 자동 전화 교환 이름에 공백을 포함 하지 마세요.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    자세한 내용은 다음을 참조 하세요.
    
      - Exchange 2007의 경우에는에서 [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)"새로운 UMAutoAttendant 전화 교환: Exchange 2007 도움말"을 참조 하세요.
    
      - Exchange 2010의 경우에는에서 [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)"새로운 UMAutoAttendant 전화 교환: Exchange 2010 도움말"을 참조 하세요.
    
    각 사용자에 대해 Lync Server 사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정한 후 SIP Uri를 확인 한 후에 다음 단계를 수행 해야 합니다.

8.  UM 다이얼 플랜을 사용 하 여 Exchange UM 사용자 (각각의 Exchange 사서함을 구성 해야 함)를 연결 하 고 각 사용자에 대 한 SIP URI를 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 다음 샘플의 <STRONG>SIPResourceIdentifier</STRONG> 는 Lync Server 사용자의 SIP 주소 여야 합니다.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    자세한 내용은 다음을 참조 하세요.
    
      - Exchange 2007의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)"Enable-ummailbox: Exchange 2007 도움말"을 참조 하세요.
    
      - Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)"Enable-ummailbox: Exchange 2010 도움말"을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

