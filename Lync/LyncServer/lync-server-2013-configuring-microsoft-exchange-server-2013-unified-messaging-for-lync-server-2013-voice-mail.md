---
title: 'Lync Server 2013: Lync Server 용 Microsoft Exchange Server 2013 통합 메시징 2013 음성 메일 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 718616db34cbdc612d083fa88c7e47da03e22bed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="fb711-102">Microsoft Lync Server 2013 음성 메일에 대해 Microsoft Exchange Server 2013 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="fb711-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb711-103">_**마지막으로 수정 된 항목:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="fb711-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="fb711-104">Microsoft Lync Server 2013을 사용 하면 Microsoft Exchange Server 2013에 음성 메일 메시지를 저장할 수 있습니다. 그러면 해당 음성 메일 메시지가 사용자의 받은 편지함에 전자 메일 메시지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="fb711-105">이 기능은 Lync Server 및 Exchange의 2010 버전 에서도 발견 되었습니다. 그러나 UM 통화 라우터 구성 요소를 도입 하 여이 "통합 메시징"을 구성 하는 프로세스는 2013 버전에서 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="fb711-106">이 구성 요소는 Exchange 2013 클라이언트 액세스 서버에 설치 되며 Exchange 통합 메시징에 대 한 모든 호출 (예: 음성 메일)은 먼저 통화 라우터를 통해 라우팅되고 다음 해당 사서함 서버로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="fb711-107">Lync Server 2013 및 Exchange 2013 간에 서버 간 인증을 이미 구성한 경우에는 통합 메시징을 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="fb711-108">이렇게 하려면 먼저 Exchange 서버에 새 통합 메시징 다이얼 플랜을 만들고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="fb711-109">예를 들어 Exchange 관리 셸 내에서 실행 되는 이러한 두 명령에는 Exchange에 대해 새 3 자리 다이얼 플랜을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="fb711-p103">위 예의 첫 번째 명령에서 VoIPSecurity 매개 변수와 매개 변수의 값 "Secured"는 신호 채널이 TLS(전송 계층 보안)를 사용하여 암호화됨을 나타냅니다. URIType "SipName"은 메시지가 SIP 프로토콜을 사용하여 송/수신됨을 나타내고, CountryOrRegionCode 1은 다이얼 플랜이 미국에 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="fb711-112">두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수로 전달되는 매개 변수 값은 이 다이얼 플랜에 사용할 수 있는 국가 내 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="fb711-113">"임의의 위치,\*\*\*" 매개 변수 값은 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="fb711-114">그룹 이름("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="fb711-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="fb711-115">Allowed번호 문자열 (\*숫자 문자열이 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="fb711-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="fb711-116">DialNumberString (\*전화를 건 모든 번호가 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="fb711-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="fb711-117">TextComment (\*모든 텍스트 명령이 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="fb711-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb711-118">또한 새 다이얼 플랜을 만들면 기본 사서함 정책도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="fb711-119">새 다이얼 플랜을 만들고 구성한 후에는 통합 메시징 서버에 새 다이얼 플랜을 추가한 다음 해당 서버의 시작 모드를 수정 해야 합니다. 특히 시작 모드를 "이중"으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="fb711-120">Exchange 관리 셸에서 이러한 두 작업을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="fb711-121">통합 메시징 서버를 구성한 후에는 다음 Get-exchangecertificate cmdlet을 실행 하 여 Exchange 인증서가 통합 메시징 서비스에 적용 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="fb711-p106">인증서가 올바르게 할당되고 나면 통합 메시징 서버에서 MsExchangeUM 서비스를 중지했다가 다시 시작해야 합니다. 시작 모드를 변경할 때마다 이 서비스를 중지한 후 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="fb711-124">통합 메시징 서버 구성이 완료되면 UM Call Router를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="fb711-125">시작 모드가 변경되었으므로 UM Call Router를 호스팅하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지했다가 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="fb711-p107">통합 메시징 설정을 완료하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용하여 사용자가 통합 메시징을 사용할 수 있도록 설정해야 합니다. 다음과 같은 명령을 사용하여 사서함 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="fb711-128">그리고 다음과 같은 명령을 사용하면 사용자가 통합 메시징을 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="fb711-p108">위의 명령에서 Extensions 매개 변수는 사용자의 전화 내선 번호를 나타냅니다. 이 예에서 사용자의 내선 번호는 100입니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="fb711-131">해당 사서함을 사용하도록 설정하고 나면 kenmyer@litwareinc.com 사용자가 Exchange 통합 메시징을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="fb711-132">Lync Server 관리 셸 내에서 [test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet을 실행 하 여 사용자가 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="fb711-133">통합 메시징을 사용할 수 있도록 설정된 두 번째 사용자가 있는 경우 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet을 사용하여 두 번째 사용자가 첫 번째 사용자에게 음성 메일 메시지를 남길 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb711-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

