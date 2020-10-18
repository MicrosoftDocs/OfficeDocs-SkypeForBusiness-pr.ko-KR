---
title: 'Lync Server 2013: Microsoft Exchange에서 통합 메시징 구성'
description: 'Lync Server 2013: Microsoft Exchange에서 통합 메시징을 구성 합니다.'
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577524"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

이 항목에서는 Enterprise Voice에서 사용 하기 위해 Microsoft Exchange Server에서 Exchange UM (통합 메시징)을 구성 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> 이 항목의 cmdlet 예제는 exchange 2007 버전의 exchange 관리 셸에 대 한 구문을 제공 합니다. Exchange 2010 또는 Exchange 2013를 실행 하는 경우 참조 되는 해당 설명서를 참조 하세요.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Exchange Server UM을 실행하는 서버를 구성하려면

1.  각 Enterprise Voice 위치 프로필에 대한 UM SIP(Session Initiation Protocol) URI(Uniform Resource Identifier) 다이얼 플랜을 만듭니다. Exchange 관리 콘솔을 사용하도록 선택하는 경우 **보안(기본 설정)** 보안 설정을 사용하여 새 다이얼 플랜을 만듭니다.
    
    <div>
    

    > [!WARNING]  
    > 보안 설정 값을 <STRONG>sip</STRONG> 트래픽 전용으로 암호화를 사용 하도록 설정 하는 경우에는 프런트 엔드 풀이 암호화를 요구 하도록 구성 된 경우에는이 보안 설정이 충분 하지 않으므로, 즉 풀에서 SIP 및 RTP 트래픽 모두에 대 한 암호화가 필요 합니다. 다이얼 플랜 및 풀 보안 설정이 호환 되지 않으면 프런트 엔드 풀에서 Exchange UM에 대 한 모든 호출이 실패 하 여 "보안 설정이 호환 되지 않습니다." 라는 오류가 표시 됩니다.

    
    </div>
    
    Exchange 관리 셸을 사용하는 경우에는 다음을 입력합니다.
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    참조 항목
    
      - Office Communications Server 2007의 경우, "통합 메시징 SIP URI 다이얼 플랜을 만드는 방법" [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) 및 "새 UMDialplan 플랜: Exchange 2007 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 하세요.
    
      - Exchange 2010의 경우에는 "UM 다이얼 플랜 만들기" [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) 및 "새 Umdialplan: Exchange 2010 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 하세요.
    
      - Exchange 2013의 경우 "통합 메시징"을 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
    <div>
    

    > [!NOTE]  
    > <STRONG>SIP 보안</STRONG> 또는 <STRONG>보안</STRONG> 보안 수준의 선택은 미디어 암호화에 대한 SRTP(Secure Real-time Transport Protocol)의 활성화 여부에 따라 결정됩니다. Exchange UM과의 Lync Server 2010 통합의 경우이는 Lync Server 미디어 구성의 암호화 수준과 일치 해야 합니다. Lync Server 미디어 구성은 <STRONG>get-csmediaconfiguration</STRONG> cmdlet을 실행 하 여 볼 수 있습니다. 자세한 내용은 Lync Server Management Shell 설명서의 Get-CsMediaConfiguration를 참조 하십시오.<BR>적절 한 VoIP 보안 설정을 선택 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">온-프레미스 통합 메시징 및 Lync Server 2013의 통합을 위한 배포 프로세스</A>를 참조 하십시오.

    
    </div>

2.  다음 cmdlet를 실행하여 각 UM 다이얼 플랜의 FQDN(정규화된 도메인 이름)을 가져옵니다.
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    참조 항목
    
      - Exchange 2007의 경우에는에서 "Get UMDialplan 플랜: Exchange 2007 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 하세요.
    
      - Exchange 2010의 경우에는에서 "Get UMDialplan 플랜: Exchange 2010 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 하세요.
    
      - Exchange 2013의 경우 "통합 메시징"을 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .

3.  각 UM 다이얼 플랜의 다이얼 플랜 이름을 기록합니다. 사용 중인 Exchange Server 버전에 따라 다이얼 플랜 이름이 일치 하도록 각 UM 다이얼 플랜의 해당 Lync Server 다이얼 플랜 이름으로 나중에 각 다이얼 플랜 이름의 FQDN을 사용 해야 할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 다이얼 플랜 이름은 Exchange 2010 SP1 <EM>이전</EM> 버전의 EXCHANGE에서 um 다이얼 플랜을 실행 하는 경우에만 um 다이얼 플랜 이름과 일치 해야 합니다.

    
    </div>

4.  다음과 같이 Exchange UM을 실행 하는 서버에 다이얼 플랜을 추가 합니다.
    
      - Exchange 관리 콘솔을 사용하도록 선택한 경우 서버에 대한 속성 시트에서 다이얼 플랜을 추가할 수 있습니다. 특정 지침은 Exchange Server 제품 설명서를 참조하십시오.
        
        Exchange 2007의 경우에는 "다이얼 플랜에 통합 메시징 서버를 추가 하는 방법"을 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 하세요.
        
        Exchange 2010의 경우에서 "UM 서버의 속성 보기 또는 구성"을 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .
        
        Exchange 2013의 경우 "통합 메시징"을 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
      - Exchange 관리 셸을 사용하는 경우 각 Exchange UM 서버에 대해 다음을 실행합니다.
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 다음 단계를 수행하기 전에 모든 Enterprise Voice 사용자가 Exchange Server 사서함에 구성되었는지 확인합니다.<BR>Exchange 2007의 경우 Exchange Server 2007 TechNet 라이브러리를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .<BR>Exchange 2010의 경우 Exchange Server 2010 TechNet 라이브러리를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .<BR>1단계에서 만든 각 다이얼 플랜에 대해 사서함 정책을 지정할 때 기본 정책 또는 사용자가 만든 정책을 선택할 수 있습니다.

    
    </div>

5.  스크립트로 이동한 \<Exchange installation directory\> \\ 다음 Exchange가 단일 포리스트에 배포 된 경우 다음을 입력 합니다.
    ```console
    exchucutil.ps1
    ```
    또는 Exchange가 여러 포리스트에 배포된 경우 다음을 입력합니다.
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    여기서 포리스트 FQDN은 Lync Server가 배포 되는 포리스트를 지정 합니다.
    
    여러 IP 게이트웨이와 연결된 UM 다이얼 플랜이 하나 이상 있는 경우 6단계를 계속 진행하고, 다이얼 플랜이 각각 하나의 IP 게이트웨이에만 연결된 경우 6단계를 건너뜁니다.
    
    <div>
    

    > [!IMPORTANT]  
    > exchucutil.ps1을 실행한 <EM>후</EM><STRONG>Lync Server 프런트 엔드</STRONG> 서비스(rtcsrv.exe)를 다시 시작해야 합니다. 그렇지 않으면 Lync Server는 토폴로지에서 통합 메시징을 검색 하지 않습니다.

    
    </div>

6.  Exchange 관리 셸 또는 Exchange 관리 콘솔을 사용하여 각 다이얼 플랜과 연결된 IP 게이트웨이 중 하나를 제외하고 모든 IP 게이트웨이에 대해 아웃바운드 통화를 해제합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계는 Exchange Server 통합 메시징을 실행 하는 서버의 아웃 바운드 통화 (예: 전화에서 재생 시나리오의 경우)가 회사 방화벽을 안정적으로 통과 하도록 하기 위해 필요 합니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 발신 전화를 허용할 UM IP 게이트웨이를 선택할 때는 가장 많은 트래픽을 처리할 수 있을 것으로 생각되는 게이트웨이를 선택합니다. Lync Server 디렉터 풀에 연결 되는 IP 게이트웨이를 통해 나가는 트래픽을 허용 하지 않습니다. 또한 다른 중앙 사이트 또는 분기 사이트의 풀도 피해야 합니다. 다음 방법 중 하나를 사용하여 발신 전화가 IP 게이트웨이를 통과하지 못하도록 차단할 수 있습니다.

    
    </div>
    
      - Exchange 관리 셸을 사용하는 경우 다음 명령을 실행하여 각 IP 게이트웨이를 해제합니다.
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Exchange 2007의 경우 "설정-UMIPGateway: Exchange 2007 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 하세요.
        
        Exchange 2010의 경우 "설정-UMIPGateway: Exchange 2010 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 하세요.
    
      - Exchange 관리 콘솔을 사용하는 경우 **이 IP 게이트웨이를 통해 발신 전화 허용** 확인란의 선택을 취소합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > UM SIP URI 다이얼 플랜과 연결된 IP 게이트웨이가 하나뿐인 경우에는 이 게이트웨이를 통한 발신 전화를 거부하지 마십시오.

    
    </div>

7.  각 Lync Server 다이얼 플랜에 대 한 UM 자동 전화 교환을 만듭니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 자동 전화 교환 이름에 공백을 포함하지 마십시오.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    참조 항목
    
      - Exchange 2007의 경우 "New UMAutoAttendant 전화 교환: Exchange 2007 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 하세요.
    
      - Exchange 2010의 경우 "New UMAutoAttendant 전화 교환: Exchange 2010 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 하세요.
    
    Lync Server 사용자가 Enterprise Voice를 사용할 수 있도록 설정한 후 SIP Uri를 확인 한 후에는 각 사용자에 대해 다음 단계를 수행 해야 합니다.

8.  각각 Exchange 사서함에 대해 구성해야 하는 Exchange UM 사용자를 UM 다이얼 플랜과 연결하고 각 사용자에 대한 SIP-URI를 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 다음 샘플의 <STRONG>SIPResourceIdentifier</STRONG> 은 Lync Server 사용자의 SIP 주소 여야 합니다.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    자세한 내용은 다음을 참조하세요.
    
      - Exchange 2007의 경우 "Enable-UMMailbox: Exchange 2007 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 하세요.
    
      - Exchange 2010의 경우 "Enable-UMMailbox: Exchange 2010 Help"를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

