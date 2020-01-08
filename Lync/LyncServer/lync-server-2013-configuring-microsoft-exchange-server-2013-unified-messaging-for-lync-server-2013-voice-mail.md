---
title: 'Lync Server 2013: Lync Server에 대 한 Microsoft Exchange Server 2013 통합 메시지를 구성 하는 방법 2013 음성 메일'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Microsoft Lync Server 2013 음성 메일용 Microsoft Exchange Server 2013 통합 메시징 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-04_

Microsoft Lync Server 2013을 통해 Microsoft Exchange Server 2013에 저장 된 보이스 메일 메시지를 사용할 수 있습니다. 그러면 해당 보이스 메일 메시지가 사용자의 받은 편지함에 전자 메일 메시지로 표시 됩니다. 이 접근 권한 값은 Lync Server 및 Exchange의 2010 버전 에서도 찾을 수 있습니다. 그러나이 "통합 메시징"을 구성 하는 프로세스는 UM 호출 라우터 구성 요소가 도입 되어 2013 버전에서 간소화 되었습니다. 이 구성 요소는 Exchange 2013 클라이언트 액세스 서버에 설치 되어 있으며, Exchange 통합 메시징 (예: 보이스 메일)에 대 한 모든 호출은 먼저 통화 라우터를 통해 라우팅되며 다음 적절 한 사서함 서버로 리디렉션됩니다.

Lync Server 2013 및 Exchange 2013 간에 서버 간 인증을 이미 구성한 경우에는 통합 메시징을 설정할 준비가 된 것입니다. 이렇게 하려면 먼저 Exchange server에서 새 통합 메시징 다이얼 플랜을 만들고 할당 해야 합니다. 예를 들어 Exchange 관리 셸에서 실행 되는 다음 두 명령은 Exchange에 대 한 새로운 3 자리 다이얼 플랜을 구성 합니다.

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

이 예제에서는 VoIPSecurity 매개 변수를 사용 하 고 매개 변수 값이 "보안"으로 표시 되는 첫 번째 명령은 신호 채널이 TLS (전송 계층 보안)를 통해 암호화 됨을 나타냅니다. URIType는 SIP 프로토콜을 사용 하 여 메시지를 보내고 받을 수 있으며, CountryOrRegionCode는 다이얼 플랜이 미국에 적용 됨을 나타냅니다.

두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수에 전달 된 매개 변수 값은이 다이얼 플랜에 사용할 수 있는 국내 그룹을 지정 합니다. 매개 변수 값 "임의의 위치\*,\*,\*"는 다음을 설정 합니다.

  - 그룹 이름 ("어디서")

  - Allowed번호 문자열 (\*즉, 숫자 문자열이 허용 됨을 나타내는 와일드 카드 문자)

  - DialNumberString (\*즉, 전화 번호가 허용 됨을 나타내는 와일드 카드 문자)

  - TextComment (\*즉, 모든 텍스트 명령이 허용 됨을 나타내는 와일드 카드 문자)

<div>


> [!NOTE]  
> 새 다이얼 플랜을 만들면 기본 사서함 정책만 생성 됩니다.



</div>

새 다이얼 플랜을 만들고 구성한 후에는 통합 메시징 서버에 새 다이얼 플랜을 추가 하 고 해당 서버의 시작 모드를 수정 해야 합니다. 특히 시작 모드를 "이중"으로 설정 해야 합니다. Exchange 관리 셸에서는 다음 두 작업을 모두 수행할 수 있습니다.

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

통합 메시징 서버를 구성한 후에는 다음 ExchangeCertificate cmdlet을 실행 하 여 Exchange 인증서가 통합 메시징 서비스에 적용 되었는지 확인 해야 합니다.

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

인증서를 올바르게 할당 한 후에는 통합 메시징 서버에서 MsExchangeUM 서비스를 중지 하 고 다시 시작 해야 합니다. 시작 모드를 변경할 때마다이 서비스를 중지 하 고 다시 시작 해야 합니다.

통합 메시징 서버의 구성을 마친 후에는 UM 호출 라우터를 구성할 수 있습니다.

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

시작 모드가 변경 되었기 때문에 UM 통화 라우터를 호스트 하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지 하 고 다시 시작 해야 합니다.

통합 메시징 설정을 완료 하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용 하 여 사용자가 통합 메시징을 사용할 수 있도록 해야 합니다. 다음과 같은 명령을 사용 하 여 사서함 정책을 만들 수 있습니다.

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

그리고 다음과 같은 명령을 사용 하 여 사용자에 게 통합 메시징을 사용할 수 있습니다.

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

앞의 명령에서 Extensions 매개 변수는 사용자의 내선 번호를 나타냅니다. 이 예제에서 사용자는 내선 번호 100를 사용 합니다.

사서함을 사용 하도록 설정한 후에는 사용자 kenmyer@litwareinc.com Exchange 통합 메시징을 사용할 수 있어야 합니다. Lync Server Management Shell 내에서 [CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet을 실행 하 여 사용자가 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

통합 메시징을 사용 하도록 설정 된 두 번째 사용자가 있는 [경우,이](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) 두 번째 사용자가 첫 번째 사용자에 대 한 보이스 메일 메시지를 남길 수 있는지 여부를 확인할 수 있습니다.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

