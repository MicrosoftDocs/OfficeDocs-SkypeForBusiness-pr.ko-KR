---
title: 비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '요약: 비즈니스용 Skype 서버 음성 메일에 대 한 Exchange Server 통합 메시징을 구성 합니다.'
ms.openlocfilehash: 514b2159c3836aee4bd6bcfad2b85311280277c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238009"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="1106a-103">비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="1106a-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="1106a-104">**요약:** 비즈니스용 Skype 서버 음성 메일에 대 한 Exchange Server 통합 메시징을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="1106a-105">비즈니스용 Skype Server를 사용 하 여 Exchange Server 2016 또는 Exchange Server 2013에 저장 된 보이스 메일 메시지를 할 수 있습니다. 그러면 해당 보이스 메일 메시지가 사용자의 받은 편지함에 전자 메일 메시지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="1106a-106">이전에는 알려진 exchange 통합 메시징 기능을 Exchange 2019에서 더 이상 사용할 수 없지만, 전화 시스템을 사용 하 여 음성 메일 메시지를 기록한 다음 사용자의 Exchange 사서함에 녹음/녹화 된 상태로 남겨둘 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="1106a-107">자세한 내용은 [클라우드 보이스 메일 서비스 계획](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1106a-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="1106a-108">비즈니스용 Skype 서버와 Exchange Server 2016 또는 Exchange Server 2013 간에 서버 간 인증을 이미 구성한 경우에는 통합 메시징을 설정할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="1106a-109">이렇게 하려면 먼저 Exchange Server에서 새 통합 메시징 다이얼 플랜을 만들고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="1106a-110">예를 들어 Exchange 관리 셸에서 실행 되는 다음 두 명령은 Exchange에 대 한 새로운 3 자리 다이얼 플랜을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="1106a-111">이 예제에서는 VoIPSecurity 매개 변수를 사용 하 고 매개 변수 값이 "보안"으로 표시 되는 첫 번째 명령은 신호 채널이 TLS (전송 계층 보안)를 통해 암호화 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="1106a-112">URIType는 SIP 프로토콜을 사용 하 여 메시지를 보내고 받을 수 있으며, CountryOrRegionCode는 다이얼 플랜이 미국에 적용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="1106a-113">두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수에 전달 된 매개 변수 값은이 다이얼 플랜에 사용할 수 있는 국내 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="1106a-114">매개 변수 값 "임의의 위치\*,\*,\*"는 다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="1106a-115">그룹 이름 ("어디서")</span><span class="sxs-lookup"><span data-stu-id="1106a-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="1106a-116">Allowed번호 문자열 (\*즉, 숫자 문자열이 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="1106a-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="1106a-117">DialNumberString (\*즉, 전화 번호가 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="1106a-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="1106a-118">TextComment (\*즉, 모든 텍스트 명령이 허용 됨을 나타내는 와일드 카드 문자)</span><span class="sxs-lookup"><span data-stu-id="1106a-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="1106a-119">새 다이얼 플랜을 만들면 기본 사서함 정책만 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="1106a-120">새 다이얼 플랜을 만들고 구성한 후에는 통합 메시징 서버에 새 다이얼 플랜을 추가 하 고 해당 서버의 시작 모드를 수정 해야 합니다. 특히 시작 모드를 "이중"으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="1106a-121">Exchange 관리 셸에서는 다음 두 작업을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="1106a-122">통합 메시징 서버를 구성한 후에는 다음 ExchangeCertificate cmdlet을 실행 하 여 Exchange 인증서가 통합 메시징 서비스에 적용 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="1106a-123">인증서를 올바르게 할당 한 후에는 통합 메시징 서버에서 MsExchangeUM 서비스를 중지 하 고 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-123">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="1106a-124">시작 모드를 변경할 때마다이 서비스를 중지 하 고 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-124">This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="1106a-125">통합 메시징 서버의 구성을 마친 후에는 UM 호출 라우터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="1106a-126">시작 모드가 변경 되었기 때문에 UM 통화 라우터를 호스트 하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지 하 고 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="1106a-127">통합 메시징 설정을 완료 하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용 하 여 사용자가 통합 메시징을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-127">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="1106a-128">다음과 같은 명령을 사용 하 여 사서함 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-128">You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="1106a-129">그리고 다음과 같은 명령을 사용 하 여 사용자에 게 통합 메시징을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="1106a-130">앞의 명령에서 Extensions 매개 변수는 사용자의 내선 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-130">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="1106a-131">이 예제에서 사용자는 내선 번호 100를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-131">In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="1106a-132">사서함을 사용 하도록 설정한 후에는 사용자 kenmyer@litwareinc.com Exchange 통합 메시징을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="1106a-133">비즈니스용 Skype Server Management Shell 내에서 [CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet을 실행 하 여 사용자가 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="1106a-134">통합 메시징을 사용 하도록 설정 된 두 번째 사용자가 있는 경우,이 두 번째 사용자 [](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) 가 첫 번째 사용자에 대 한 보이스 메일 메시지를 남길 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="1106a-135">Microsoft Exchange Server에서 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="1106a-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="1106a-136">UM (통합 메시징)를 사용 하 여 엔터프라이즈 음성 사용자에 대 한 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공 하려는 경우 [비즈니스용 Skype에서 Exchange 통합 메시징 통합에 대 한 계획](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)을 읽고 다음을 따르세요. 이 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="1106a-137">엔터프라이즈 음성으로 작업 하도록 Exchange UM (통합 메시징)를 구성 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="1106a-138">Exchange UM (통합 메시징) 서비스를 실행 하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="1106a-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="1106a-139">모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="1106a-140">그렇지 않은 경우에는 아웃 바운드 통화 라우팅이 예상 대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="1106a-141">필요에 따라 하나 이상의 UM SIP URI 다이얼 플랜을 구독자 액세스 전화 번호와 함께 만든 다음 해당 하는 L 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="1106a-142">Exchucutil 스크립트를 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="1106a-143">UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="1106a-144">UM 헌트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="1106a-145">비즈니스용 Skype Server에서 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="1106a-146">UM 자동 전화 교환 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="1106a-147">구독자 액세스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="1106a-148">각 사용자에 대해 SIP URI를 만들고 사용자를 UM SIP URI 다이얼 플랜에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="1106a-149">요구 사항 및 제안</span><span class="sxs-lookup"><span data-stu-id="1106a-149">Requirements and Recommendations</span></span>

<span data-ttu-id="1106a-150">시작 하기 전에이 섹션의 문서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 역할을 배포한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="1106a-151">Microsoft Exchange Server에서는 Exchange UM을 이러한 서버에서 서비스로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="1106a-152">또한 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="1106a-152">Also note the following:</span></span>
- <span data-ttu-id="1106a-153">Exchange UM을 여러 포리스트에 설치 하는 경우 각 UM 포리스트에 대해 Exchange Server 통합 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="1106a-154">또한 각 UM 포리스트는 비즈니스용 Skype 서버를 배포 하는 포리스트를 신뢰 하도록 구성 해야 하며, 비즈니스용 whichSkype Server의 포리스트가 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="1106a-155">통합 메시징 서비스가 실행 되는 Exchange 서버 역할과 비즈니스용 Skype 서버를 실행 하는 서버에 대 한 통합 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="1106a-156">Lync Server 2013 통합 단계를 수행 하기 전에 Exchange Server 통합 메시징 통합 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="1106a-157">어떤 서버와 어떤 관리자 역할에 대해 어떤 통합 단계를 수행 해야 하는지 확인 하려면 [온-프레미스 통합 메시징과 비즈니스용 Skype 통합에 대 한 배포 프로세스 개요](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1106a-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="1106a-158">Exchange UM을 (를) 실행 하는 각 서버에서 다음 도구를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="1106a-159">Exchange 관리 셸</span><span class="sxs-lookup"><span data-stu-id="1106a-159">Exchange Management Shell</span></span>
- <span data-ttu-id="1106a-160">다음 작업을 수행 하는 exchucutil 스크립트.</span><span class="sxs-lookup"><span data-stu-id="1106a-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="1106a-161">각 비즈니스용 Skype Server에 대해 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="1106a-162">각 게이트웨이에 대 한 헌트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="1106a-163">각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결 된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="1106a-164">Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 비즈니스용 Skype Server 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="1106a-165">ExchUCUtil를 사용 하 여 Microsoft Exchange에서 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="1106a-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="1106a-166">Exchange UM (통합 메시징)과 함께 Microsoft 비즈니스용 Skype 서버를 통합 하는 경우 셸에서 ExchUcUtil 스크립트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="1106a-167">ExchUcUtil 스크립트는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="1106a-168">각 비즈니스용 Skype Server 풀에 대해 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1106a-169">ExchUcUtil 스크립트는 하나 이상의 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="1106a-170">스크립트에서 만든 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="1106a-171">여기에는 스크립트를 실행 하기 전에 만든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="1106a-172">각 UM IP 게이트웨이에 대해 UM 헌트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="1106a-173">각 헌트 그룹의 파일럿 식별자는 UM IP 게이트웨이와 연결 된 비즈니스용 Skype 서버 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="1106a-174">UM 다이얼 플랜, 자동 전화 교환, UM IP 게이트웨이, UM 헌트 그룹과 같은 Active Directory UM 컨테이너 개체를 읽을 수 있는 비즈니스용 Skype Server 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="1106a-175">각 UM 포리스트는 비즈니스용 Skype 서버가 배포 되는 포리스트를 신뢰 하도록 구성 해야 하며, 비즈니스용 Skype 서버 2013이 배포 되는 포리스트를 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="1106a-176">Exchange UM을 여러 포리스트에 설치 하는 경우 각 UM 포리스트에 대해 Exchange Server 통합 단계를 수행 하거나 비즈니스용 Skype 서버 도메인을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="1106a-177">예를 들어 ExchUcUtil –. ps1-포리스트: <lync-컨트롤러-fqdn>.</span><span class="sxs-lookup"><span data-stu-id="1106a-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="1106a-178">Shell을 사용 하 여 ExchUcUtil 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="1106a-179">비즈니스용 Skype 서버와 동일한 토폴로지를가지고 있는 조직의 모든 Exchange 서버에서 ExchUcUtil 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="1106a-180">셸을 사용 하 여 사서함 서버에서 스크립트를 실행 하거나 클라이언트 액세스 서버에서 원격 Windows PowerShell을 사용 하 여 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="1106a-181">조직의 클라이언트 액세스 서버에서 스크립트를 실행 하는 경우 클라이언트 액세스 서버는 원격 Windows PowerShell 세션을 조직의 사서함 서버에 프록시 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1106a-182">ExchUcUtil 스크립트는 하나 이상의 UM IP 게이트웨이를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="1106a-183">스크립트에서 만든 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="1106a-184">여기에는 스크립트를 실행 하기 전에 만든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="1106a-185">UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하려면 UM IP 게이트웨이에서 발신 전화 사용 안 함을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1106a-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="1106a-186">스크립트를 실행 하려면 Exchange 조직 관리 역할의 사용 권한이 나 Exchange 조직 관리자 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="1106a-187">Exchange 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="1106a-188">Files\Microsoft\Exchange System32 프롬프트에서 **cd \<드라이브 문자>: a/Server\V15\Scripts>를 입력 합니다. ExchUcUtil**을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1106a-189">이 작업이 제대로 수행 되었는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1106a-189">How do you know this worked?</span></span>

<span data-ttu-id="1106a-190">ExchUcUtul 스크립트가 성공적으로 완료 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="1106a-191">Get-UMIPGateway cmdlet 또는 EAC를 사용 하 여 생성 된 새 UM IP 게이트웨이 또는 게이트웨이를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="1106a-192">UMHuntGroup cmdlet 또는 EAC를 사용 하 여 생성 된 새 UM 헌트 그룹을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="1106a-193">Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="1106a-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="1106a-194">계획 설명서의 비즈니스용 Skype 서버에서 Exchange 통합 메시징 통합 계획에 설명 된 대로 exchange um (통합 메시징)를 배포한 경우, 사용자의 엔터프라이즈 음성 사용자에 게 Exchange UM 기능을 제공 하려는 경우 조직에서 다음 절차를 사용 하 여 Exchange UM을 실행 하는 서버에서 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1106a-195">내부 인증서의 경우 비즈니스용 Skype Server를 실행 하는 서버와 Microsoft Exchange를 실행 하는 서버에 모두 상호 신뢰 되는 신뢰할 수 있는 루트 인증 기관 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="1106a-196">CA (인증 기관)가 신뢰할 수 있는 루트 인증 기관 인증서 저장소에 등록 되어 있는 경우 해당 서버는 동일 하거나 다른 인증 기관 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="1106a-197">비즈니스용 Skype 서버에 연결 하기 위해 서버 인증서를 사용 하 여 Exchange 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="1106a-198">Exchange 서버에 대 한 CA 인증서를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="1106a-199">Exchange 서버에 대 한 CA 인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="1106a-200">CA가 Exchange Server의 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="1106a-201">Exchange 서버에 대 한 인증서 요청을 만들고 인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="1106a-202">Exchange 서버에 대 한 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="1106a-203">**CA 인증서를 다운로드 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1106a-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="1106a-204">Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **발급 CA\<> 서버의 http://이름을**입력 하 고/certsrv을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="1106a-205">작업 선택에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="1106a-206">**Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **Base 64에 대 한 인코딩 방법을**선택한 다음**CA 인증서 다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1106a-207">이 단계에서 DER (고유 인코딩 규칙) 인코딩을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="1106a-208">DER 인코딩을 선택 하는 경우이 절차의 다음 단계인 **CA 인증서를 설치 하** 는 10 단계의 파일 형식은. .cer이 아닌.</span><span class="sxs-lookup"><span data-stu-id="1106a-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="1106a-209">**파일 다운로드** 대화 상자에서 **저장**을 클릭 한 다음 서버의 하드 디스크에 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="1106a-210">(이 파일에는 이전 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 확장명 중 하나가 사용 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="1106a-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="1106a-211">**CA 인증서를 설치 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1106a-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="1106a-212">Exchange UM을 (를) 실행 하는 서버에서 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 열기 상자에 **Mmc** 를 입력 하 고 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="1106a-213">**파일** 메뉴에서 **스냅인 추가/제거**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="1106a-214">**독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="1106a-215">**인증서 스냅인** 대화 상자에서 **컴퓨터 계정을**클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="1106a-216">**컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="1106a-217">**닫기를**클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="1106a-218">콘솔 트리에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관을**확장 한 다음 **인증서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="1106a-219">**인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="1106a-220">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-220">Click **Next**.</span></span> 
10. <span data-ttu-id="1106a-221">**찾아보기를** 클릭 하 여 파일을 찾은 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="1106a-222">(이 파일은 **CA 인증서를 다운로드 하기 위해**3 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 파일 확장명을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="1106a-223">**모든 인증서** 를 다음 저장소에 저장을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="1106a-224">**찾아보기를**클릭 한 다음 **신뢰할 수 있는 루트 인증 기관을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="1106a-225">**다음** 을 클릭 하 여 설정을 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="1106a-226">**CA가 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1106a-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="1106a-227">Exchange UM을 실행 하는 서버의 MMC에서 인증서 (로컬 컴퓨터)를 확장 하 고 신뢰할 수 있는 루트 인증 기관을 확장 한 다음 인증서를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="1106a-228">세부 정보 창에서 CA가 신뢰할 수 있는 Ca 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1106a-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


