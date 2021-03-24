---
title: 비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '요약: Exchange Server 서버 음성 메일에 대한 통합 메시징을 구성합니다.'
ms.openlocfilehash: 24bad46103433f6af9caebbe1894b1b3b2aa83d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109824"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="6c71e-103">비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="6c71e-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="6c71e-104">**요약:** 비즈니스 Exchange Server 음성 메일에 대한 통합 메시징을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="6c71e-105">비즈니스용 Skype 서버를 사용하면 음성 메일 메시지가 Exchange Server 2016 또는 Exchange Server 2013에 저장될 수 있습니다. 이러한 음성 메일 메시지는 사용자의 받은 편지함에서 전자 메일 메시지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="6c71e-106">이전에 알려진 Exchange 통합 메시징은 Exchange 2019에서 더 이상 사용할 수 없지만 전화 시스템을 사용하여 음성 메일 메시지를 녹음한 다음 사용자의 Exchange 사서함에 기록을 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="6c71e-107">자세한 [내용은 Plan Cloud Voicemail service을](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c71e-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="6c71e-108">비즈니스용 Skype 서버와 Exchange Server 2016 또는 Exchange Server 2013 간에 서버 간 인증을 이미 구성한 경우 통합 메시징을 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="6c71e-109">이렇게하려면 먼저 새 통합 메시징 다이얼 플랜을 만들어 해당 다이얼 플랜에 할당해야 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6c71e-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="6c71e-110">예를 들어 다음 두 명령(Exchange 관리 셸 내에서 실행)은 Exchange에 대한 새 3자리 다이얼 플랜을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="6c71e-111">예제의 첫 번째 명령에서 VoIPSecurity 매개 변수와 매개 변수 값 "Secured"는 신호 채널이 TLS(전송 계층 보안)를 사용하여 암호화되고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="6c71e-112">URIType "SipName"은 메시지가 SIP 프로토콜을 사용하여 송/수신됨을 나타내고, CountryOrRegionCode 1은 다이얼 플랜이 미국에 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="6c71e-113">두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수로 전달되는 매개 변수 값은 이 다이얼 플랜에 사용할 수 있는 국가 내 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="6c71e-114">매개 변수 값 "Anywhere, \* \* , " \* 는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="6c71e-115">그룹 이름("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="6c71e-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="6c71e-116">AllowedNumberString( , 숫자 문자열이 허용되었음을 나타내는 와일드카드 \* 문자)</span><span class="sxs-lookup"><span data-stu-id="6c71e-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="6c71e-117">DialNumberString( , 전화 걸기 번호가 허용되었음을 나타내는 와일드카드 \* 문자)</span><span class="sxs-lookup"><span data-stu-id="6c71e-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="6c71e-118">TextComment( , 모든 텍스트 명령이 허용되었음을 나타내는 \* 와일드카드 문자)</span><span class="sxs-lookup"><span data-stu-id="6c71e-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c71e-119">새 다이얼 플랜을 만들면 기본 사서함 정책도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="6c71e-120">새 다이얼 플랜을 만들고 구성한 후 통합 메시징 서버에 새 다이얼 플랜을 추가한 다음 해당 서버의 시작 모드를 수정해야 합니다. 특히 시작 모드를 "Dual"로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="6c71e-121">Exchange 관리 셸 내에서 이러한 두 작업을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="6c71e-122">통합 메시징 서버를 구성한 후 다음에는 Enable-ExchangeCertificate cmdlet을 실행하여 Exchange 인증서가 통합 메시징 서비스에 적용되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="6c71e-p106">인증서가 올바르게 할당되고 나면 통합 메시징 서버에서 MsExchangeUM 서비스를 중지했다가 다시 시작해야 합니다. 시작 모드를 변경할 때마다 이 서비스를 중지한 후 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="6c71e-125">통합 메시징 서버 구성이 완료되면 UM Call Router를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="6c71e-126">시작 모드가 변경되었으므로 UM Call Router를 호스팅하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지했다가 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="6c71e-p107">통합 메시징 설정을 완료하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용하여 사용자가 통합 메시징을 사용할 수 있도록 설정해야 합니다. 다음과 같은 명령을 사용하여 사서함 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="6c71e-129">그리고 다음과 같은 명령을 사용하면 사용자가 통합 메시징을 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="6c71e-p108">위의 명령에서 Extensions 매개 변수는 사용자의 전화 내선 번호를 나타냅니다. 이 예에서 사용자의 내선 번호는 100입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="6c71e-132">해당 사서함을 사용하도록 설정하고 나면 kenmyer@litwareinc.com 사용자가 Exchange 통합 메시징을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="6c71e-133">사용자가 비즈니스용 Skype 서버 관리 셸 내에서 [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet을 실행하여 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="6c71e-134">통합 메시징을 사용할 수 있도록 설정된 두 번째 사용자가 있는 경우 [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet을 사용하여 두 번째 사용자가 첫 번째 사용자에게 음성 메일 메시지를 남길 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="6c71e-135">통합 메시징에서 Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6c71e-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="6c71e-136">UM(Exchange 통합 메시징)을 사용하여 Enterprise Voice 사용자를 위해 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공하려는 경우 비즈니스용 [Skype에서 Exchange](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)통합 메시징 통합 계획을 읽고 이 섹션의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="6c71e-137">Exchange UM(통합 메시징)이 Enterprise Voice 작동하도록 구성하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="6c71e-138">Exchange UM(통합 메시징) 서비스를 실행하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="6c71e-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="6c71e-139">모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="6c71e-140">그렇지 않은 경우 아웃바운드 통화 라우팅이 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="6c71e-141">필요한 경우 구독자 액세스 전화 번호와 함께 하나 이상의 UM SIP URI 다이얼 플랜을 만든 다음 해당 L 다이얼 플랜을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="6c71e-142">다음 exchucutil.ps1 스크립트를 사용하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="6c71e-143">UM IP 게이트웨이 만들기</span><span class="sxs-lookup"><span data-stu-id="6c71e-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="6c71e-144">UM 헌트 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6c71e-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="6c71e-145">UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 비즈니스용 Skype 서버에게 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="6c71e-146">UM 자동 회의 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="6c71e-147">구독자 액세스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="6c71e-148">각 사용자에 대해 SIP URI를 만들고 사용자를 UM SIP URI 다이얼 플랜과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="6c71e-149">요구 사항 및 권장 사항</span><span class="sxs-lookup"><span data-stu-id="6c71e-149">Requirements and Recommendations</span></span>

<span data-ttu-id="6c71e-150">시작하기 전에 이 섹션의 설명서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 역할을 배포했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="6c71e-151">이 Microsoft Exchange Server Exchange UM은 이러한 서버에서 서비스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="6c71e-152">또한 다음에 주의하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c71e-152">Also note the following:</span></span>
- <span data-ttu-id="6c71e-153">Exchange UM이 여러 포리스트에 설치되어 있는 경우 각 UM Exchange Server 통합 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="6c71e-154">또한 비즈니스용 Skype 서버가 배포된 포리스트를 신뢰하도록 각 UM 포리스트를 구성해야 합니다. 또한 비즈니스용 Skype 서버가 배포된 포리스트는 각 UM 포리스트를 신뢰하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="6c71e-155">통합 단계는 통합 메시징 서비스가 Exchange Server 역할과 비즈니스용 Skype 서버를 실행하는 서버에서 모두 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="6c71e-156">Lync Server 2013 Exchange Server 전에 통합 메시징 통합 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="6c71e-157">어떤 서버에서 어떤 통합 단계와 관리자 역할이 수행되는지 확인 내용은 [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business을 참조하십시오.](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6c71e-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="6c71e-158">Exchange UM을 실행하는 각 서버에서 다음 도구를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="6c71e-159">Exchange 관리 셸</span><span class="sxs-lookup"><span data-stu-id="6c71e-159">Exchange Management Shell</span></span>
- <span data-ttu-id="6c71e-160">다음 작업을 수행하는 스크립트 exchucutil.ps1</span><span class="sxs-lookup"><span data-stu-id="6c71e-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="6c71e-161">각 비즈니스용 Skype 서버에 대해 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="6c71e-162">각 게이트웨이에 대한 헌트 그룹 만들기.</span><span class="sxs-lookup"><span data-stu-id="6c71e-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="6c71e-163">각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용하는 UM SIP URI 다이얼 플랜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="6c71e-164">Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 권한을 비즈니스용 Skype 서버에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="6c71e-165">통합 메시징을 사용하여 Microsoft Exchange에서 ExchUCUtil.ps1</span><span class="sxs-lookup"><span data-stu-id="6c71e-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="6c71e-166">Microsoft 비즈니스용 Skype 서버를 Exchange UM(통합 메시징)에 통합하는 경우 셸에서 ExchUcUtil.ps1 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="6c71e-167">ExchUcUtil.ps1 스크립트는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="6c71e-168">각 비즈니스용 Skype 서버 풀에 대한 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c71e-169">ExchUcUtil.ps1 스크립트는 UM IP 게이트웨이를 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="6c71e-170">스크립트가 만들어진 한 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="6c71e-171">또한 스크립트를 실행하기 전에 만들어진 UM IP 게이트웨이에서도 발신 전화를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="6c71e-172">각 UM IP 게이트웨이에 대해 UM 헌트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="6c71e-173">각 헌트 그룹의 파일럿 식별자는 UM IP 게이트웨이와 연결된 비즈니스용 Skype 서버 프런트 엔드 풀 또는 Standard Edition 서버에서 사용하는 UM SIP URI 다이얼 플랜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="6c71e-174">비즈니스용 Skype 서버에 UM 다이얼 플랜, 자동 전화 통신, UM IP 게이트웨이 및 UM 헌트 그룹과 같은 Active Directory UM 컨테이너 개체를 읽을 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="6c71e-175">각 UM 포리스트는 비즈니스용 Skype 서버가 배포된 포리스트를 신뢰하도록 구성해야 합니다. 또한 각 UM 포리스트를 신뢰하도록 비즈니스용 Skype 서버 2013이 배포된 포리스트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="6c71e-176">Exchange UM이 여러 포리스트에 설치된 경우 Exchange Server UM 포리스트에 대해 통합 단계를 수행하거나 비즈니스용 Skype 서버 도메인을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="6c71e-177">예를 들어 -ExchUcUtil.ps1:<-lync-domain-controller-fqdn을>.</span><span class="sxs-lookup"><span data-stu-id="6c71e-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="6c71e-178">셸을 사용하여 ExchUcUtil.ps1 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="6c71e-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="6c71e-179">조직의 ExchUcUtil.ps1 비즈니스용 Skype 서버와 동일한 토폴로지에 있는 Exchange 서버에서 ExchUcUtil.ps1 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="6c71e-180">셸을 사용하여 사서함 서버에서 스크립트를 실행하거나, 클라이언트 액세스 서버에서 원격 Windows PowerShell을 사용하여 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="6c71e-181">조직의 클라이언트 액세스 서버에서 스크립트를 실행하면 클라이언트 액세스 서버가 원격 Windows PowerShell 세션을 조직에 있는 사서함 서버로 프록시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6c71e-182">ExchUcUtil.ps1 스크립트는 UM IP 게이트웨이를 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="6c71e-183">스크립트가 만들어진 한 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="6c71e-184">또한 스크립트를 실행하기 전에 만들어진 UM IP 게이트웨이에서도 발신 전화를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="6c71e-185">UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정하려면 UM IP 게이트웨이에서 거는 전화를 사용 하지 않도록 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c71e-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="6c71e-186">사용자는 Exchange 조직 관리 역할의 사용 권한이 있거나, 스크립트를 실행할 수 있는 Exchange 조직 관리 보안 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="6c71e-187">Exchange 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="6c71e-188">C:\Windows\System32 프롬프트에 **cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** 를 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6c71e-189">작동 여부를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="6c71e-189">How do you know this worked?</span></span>

<span data-ttu-id="6c71e-190">ExchUcUtul.ps1 스크립트가 완료되었는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="6c71e-191">Get-UMIPGateway cmdlet 또는 EAC를 사용하여 새로운 UM IP 게이트웨이 또는 만들어진 게이트웨이를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="6c71e-192">Get-UMHuntGroup cmdlet 또는 EAC를 사용하여 새로운 UM 헌트 그룹 또는 만들어진 그룹을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="6c71e-193">통합 메시징을 실행하는 서버에서 Exchange Server 구성</span><span class="sxs-lookup"><span data-stu-id="6c71e-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="6c71e-194">계획 설명서의 Planning for Exchange Unified Messaging integration in Skype for Business Server에 설명된 바와 같이 Exchange UM(통합 메시징)을 배포한 경우 조직의 Enterprise Voice 사용자에게 Exchange UM 기능을 제공하려는 경우 다음 절차에 따라 Exchange UM을 실행하는 서버에서 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c71e-195">내부 인증서의 경우 비즈니스용 Skype 서버를 실행하는 서버와 Microsoft Exchange를 실행하는 서버에는 상호 신뢰할 수 있는 신뢰할 수 있는 루트 기관 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="6c71e-196">서버에 인증 기관의 루트 인증서가 신뢰할 수 있는 루트 기관 인증서 저장소에 등록되어 있는 한 CA(인증 기관)는 동일하거나 다른 인증 기관일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="6c71e-197">비즈니스 Exchange Server 연결하려면 서버 인증서를 사용하여 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="6c71e-198">Exchange Server에 대한 CA 인증서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="6c71e-199">Exchange Server에 대한 CA 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="6c71e-200">Exchange Server의 신뢰할 수 있는 루트 CA 목록에 해당 CA가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="6c71e-201">Exchange Server에 대한 인증서 요청을 만들고 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="6c71e-202">Exchange Server에 대한 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="6c71e-203">**CA 인증서를 다운로드하려면**</span><span class="sxs-lookup"><span data-stu-id="6c71e-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="6c71e-204">Exchange UM을 실행하는 서버에서 **시작,** 실행을 **클릭하고** **\<name of your Issuing CA Server> /certsrv를 http:// /certsrv를** 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c71e-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="6c71e-205">작업 선택에서 CA 인증서, 인증서 체인 또는 **CRL 다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c71e-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="6c71e-206">CA 인증서, 인증서 체인 또는 **CRL** 다운로드에서 기준 **64로** 인코딩 방법을 선택한 다음 CA 인증서 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c71e-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="6c71e-207">이 단계에서 DER(Distinguished Encoding Rules) 인코딩을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="6c71e-208">DER 인코딩을 선택하는 경우 이 절차 다음 단계와 **CA 인증서를 설치하려면** 의 10단계에서 파일 형식은 .cer이 아닌 .p7b입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="6c71e-p123">**파일 다운로드** 대화 상자에서 **저장** 을 클릭한 다음 파일을 서버의 하드 디스크에 저장합니다. 이전 단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-p123">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="6c71e-211">**CA 인증서를 설치하려면**</span><span class="sxs-lookup"><span data-stu-id="6c71e-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="6c71e-212">Exchange UM을 실행하는 서버에서 시작, 실행을 클릭하고 열기 상자에 **mmc를** 입력한 다음 확인 을 클릭하여 MMC(Microsoft Management Console)를 열 **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="6c71e-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="6c71e-213">**파일** 메뉴에서 **스냅인 추가/제거** 를 클릭한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="6c71e-214">**독립 실행형 스냅인 추가** 상자에서 **인증서** 를 클릭한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="6c71e-215">**인증서 스냅인** 대화 상자에서 **컴퓨터 계정** 을 클릭한 다음 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="6c71e-216">컴퓨터 **선택** 대화 상자에서 로컬 **컴퓨터: (이** 콘솔이 실행되고 있는 컴퓨터) 확인란이 선택되어 있는지 확인한 다음 마침을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c71e-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="6c71e-217">**닫기** 를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="6c71e-218">콘솔 트리에서 **인증서(로컬 컴퓨터)**, **신뢰할 수 있는 루트 인증 기관** 을 차례로 확장한 다음 **인증서** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="6c71e-219">**인증서** 를 마우스 오른쪽 단추로 클릭하고 **모든 작업** 을 클릭하고 **가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="6c71e-220">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-220">Click **Next**.</span></span> 
10. <span data-ttu-id="6c71e-p124">**찾아보기** 를 클릭하여 파일을 찾은 다음 **다음** 을 클릭합니다. **CA 인증서를 다운로드하려면** 의 3단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-p124">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="6c71e-223">다음 **저장소에 모든 인증서** 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="6c71e-224">**찾아보기** 를 클릭한 다음 **신뢰할 수 있는 루트 인증 기관** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="6c71e-225">**다음** 을 클릭하여 설정을 확인한 다음 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="6c71e-226">**CA가 신뢰할 수 있는 루트 CA 목록에 있는지 확인:**</span><span class="sxs-lookup"><span data-stu-id="6c71e-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="6c71e-227">Exchange UM을 실행하는 서버의 MMC에서 인증서(로컬 컴퓨터)를 확장하고 신뢰할 수 있는 루트 인증 기관을 확장한 다음 인증서를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="6c71e-228">세부 정보 창에서 해당 CA가 신뢰할 수 있는 CA 목록에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71e-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>