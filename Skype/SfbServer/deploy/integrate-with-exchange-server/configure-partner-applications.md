---
title: 비즈니스용 Skype 서버 2015 및 Exchange Server에서 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype Server에 대 한 서버 인증을 서버로 구성 합니다.'
ms.openlocfilehash: 004b9c1926f00cd869658ae0b90679897d20516b
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001258"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="e605a-103">비즈니스용 Skype 서버 및 Exchange Server에서 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="e605a-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="e605a-104">**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype Server에 대해 서버를 서버 인증으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="e605a-105">일반적으로 서버 간 인증은 다른 공급 업체의 보안 토큰 서버와 통신 해야 하는 두 개의 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="e605a-106">서버 A와 서버 B가 통신 해야 하는 경우 일반적으로 두 서버 모두 토큰 서버에 연결 하 고 상호 신뢰 된 보안 토큰을 가져오는 방법으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="e605a-107">그런 다음 서버 A는 해당 인증 및 신뢰성을 보장 하는 방법으로 서버 B에 보안 토큰을 표시 합니다 (그 반대의 경우도 마찬가지).</span><span class="sxs-lookup"><span data-stu-id="e605a-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="e605a-108">그러나 일반 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-108">However, that's a general rule.</span></span> <span data-ttu-id="e605a-109">비즈니스용 Skype 서버, Exchange Server 2016, Exchange Server 2013 및 SharePoint Server 2013는 서로 통신할 때 타사 토큰 서버를 사용할 필요가 없습니다. 이는 이러한 서버 제품이 별도의 토큰 서버 없이 다른 사람이 수락할 수 있는 보안 토큰을 만들 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="e605a-110">이 접근 권한 값은 비즈니스용 Skype 서버, Exchange Server 2016, Exchange Server 2013 및 SharePoint Server 2013 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="e605a-111">다른 Microsoft server 제품을 포함 하 여 다른 서버와 서버 간 인증을 설정 해야 하는 경우 타사 토큰 서버를 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="e605a-112">비즈니스용 Skype 서버와 Exchange Server 간에 서버 간 인증을 설정 하려면 다음 두 가지 작업을 수행 해야 합니다. 1) 각 서버에 적절 한 인증서를 할당 해야 합니다. and, 2) 각 서버를 다른 서버의 파트너 응용 프로그램으로 구성 해야 합니다. 즉, 비즈니스용 Skype 서버를 Exchange Server 파트너 응용 프로그램으로 구성 해야 하며, Skype에 대 한 파트너 응용 프로그램이 되도록 Exchange Server를 구성 해야 합니다. 비즈니스 서버용</span><span class="sxs-lookup"><span data-stu-id="e605a-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="e605a-113">비즈니스용 Skype 서버를 Exchange Server 용 파트너 응용 프로그램으로 구성</span><span class="sxs-lookup"><span data-stu-id="e605a-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="e605a-114">Exchange server 2016 또는 Exchange Server 2013를 사용 하 여 비즈니스용 Skype 서버를 파트너 응용 프로그램으로 구성 하는 가장 쉬운 방법은 Exchange Server와 함께 제공 되는 Windows PowerShell 스크립트인 Configure-EnterprisePartnerApplication 스크립트를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="e605a-115">이 스크립트를 실행 하려면 비즈니스용 Skype 서버 인증 메타 데이터 문서에 대 한 URL을 제공 해야 합니다. 이는 일반적으로 비즈니스용 Skype 서버 풀의 정규화 된 도메인 이름이 고 그 뒤에는 접미사가/metadata/json/1..</span><span class="sxs-lookup"><span data-stu-id="e605a-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e605a-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="e605a-117">비즈니스용 Skype 서버를 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (C: 드라이브에 Exchange가 설치 되어 있고 기본 폴더 경로를 사용 하 고 있다고 가정).</span><span class="sxs-lookup"><span data-stu-id="e605a-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="e605a-118">파트너 응용 프로그램을 구성한 후에는 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="e605a-119">컴퓨터 atl-exchange-001에서 서비스를 다시 시작 하는 다음과 같은 명령을 사용 하 여 IIS를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="e605a-120">이 명령은 Exchange 관리 셸 내에서 또는 관리자 권한으로 실행 되는 다른 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="e605a-121">비즈니스용 Skype 서버용 파트너 응용 프로그램이 되도록 Exchange Server 구성</span><span class="sxs-lookup"><span data-stu-id="e605a-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="e605a-122">비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013의 파트너 응용 프로그램으로 구성한 후에는 Exchange Server를 비즈니스용 Skype 서버용 파트너 응용 프로그램으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="e605a-123">이 작업은 비즈니스용 Skype 서버 관리 셸을 사용 하 고 Exchange 용 인증 메타 데이터 문서를 지정 하 여 수행할 수 있습니다. 이는 일반적으로 Exchange 자동 검색 서비스의 URI이 고 그 뒤에 접미사/metadata/json/1. 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e605a-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="e605a-125">비즈니스용 Skype Server에서 파트너 응용 프로그램은 [CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="e605a-126">메타 데이터 URI를 지정 하는 것 외에도 응용 프로그램 신뢰 수준을 Full로 설정 해야 합니다. 이를 통해 Exchange는 자신 및 영역에 있는 권한 있는 모든 사용자를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="e605a-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="e605a-128">또는 비즈니스용 Skype 서버에서 서버 간 인증 설명서에 있는 스크립트 코드를 복사 하 여 수정 하 여 파트너 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="e605a-129">자세한 내용은 비즈니스용 [Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](../../manage/authentication/server-to-server-and-partner-applications.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e605a-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="e605a-130">비즈니스용 Skype 서버와 Exchange Server 모두에 대 한 파트너 응용 프로그램을 성공적으로 구성한 경우 두 제품 간에 서버 간 인증도 성공적으로 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="e605a-131">비즈니스용 skype Server에는 Windows PowerShell cmdlet 인 [Test CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) 포함 되어 있으며,이를 통해 서버 간 인증이 올바르게 구성 되어 있고 비즈니스용 Skype 서버 저장소 서비스에서 Exchange server에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="e605a-132">Cmdlet은 Exchange Server 사용자의 사서함에 연결 하 고 해당 사용자의 대화 내용 폴더에 항목을 쓴 다음 (선택적으로) 해당 항목을 삭제 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="e605a-133">비즈니스용 Skype 서버 및 Exchange Server의 통합을 테스트 하려면 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="e605a-134">앞의 명령에서 SipUri는 Exchange Server의 계정이 있는 사용자의 SIP 주소를 나타냅니다. 이 명령은 올바른 사용자 계정이 아닌 경우에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e605a-135">이 cmdlet에서 401 응답을 수신 하는 경우 Exchange의 기본 구성에 Oauth 토큰 허용에 대 한 지원이 포함 되지 않기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="e605a-136">Exchange에서 Oauth를 사용 하는 방법에 대 한 자세한 내용은 [SharePoint 2013 및 비즈니스용 Skype 서버를 사용 하 여 Oauth 인증 구성을](https://go.microsoft.com/fwlink/p/?LinkId=513103)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e605a-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="e605a-137">테스트가 성공 하 고 연결이 설정 되 면 계속 진행 하 여 보관 통합 및 통합 된 연락처 저장소와 같은 선택적 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e605a-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
