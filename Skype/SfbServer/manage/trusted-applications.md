---
title: 신뢰할 수 있는 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187074"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="26baa-103">비즈니스용 Skype 서버에서 신뢰할 수 있는 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="26baa-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="26baa-104">*신뢰할 수 있는 응용* 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 ma) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="26baa-105">(C) MA 응용 프로그램에 대 한 자세한 내용은에서 http://go.microsoft.com/fwlink/p/?linkId=210320"통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26baa-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="26baa-106">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="26baa-107">신뢰할 수 있는 새 응용 프로그램 서버를 구성 하 고 신뢰할 수 있는 응용 프로그램 목록을 보고 신뢰할 수 있는 응용 프로그램 정보를 보는 방법에 대해 알아보려면이 문서를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="26baa-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="26baa-108">신뢰할 수 있는 새 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="26baa-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="26baa-109">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="26baa-110">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="26baa-111">**기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="26baa-112">**다른 이름으로 토폴로지 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="26baa-113">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="26baa-114">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고,이를 단일 서버 또는 다중 서버 중에서 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="26baa-115">**다음 홉 선택** 페이지의 목록에서 비즈니스용 Skype 서버 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="26baa-116">**마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="26baa-117">최상위 노드 **비즈니스용 Skype 서버**를 선택 하 고 **작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="26baa-118">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어지고 올바른 프런트 엔드 풀에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="26baa-119">신뢰할 수 있는 응용 프로그램 목록 보기</span><span class="sxs-lookup"><span data-stu-id="26baa-119">View a list of trusted applications</span></span>

<span data-ttu-id="26baa-120">비즈니스용 skype server 제어판을 사용 하 여 비즈니스용 Skype 서버 환경에서 배포한 신뢰할 수 있는 응용 프로그램 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="26baa-121">신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="26baa-122">이 신뢰 관계는 다음 목록에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="26baa-123">신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버 인증에 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="26baa-124">신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 SIP 거래, 연결 또는 VoIP (인터넷 프로토콜) 전화를 위해 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="26baa-125">신뢰 하는 응용 프로그램은 모든 사용자를 가장할 수 있으며 rosters에 표시 하지 않고 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="26baa-126">신뢰할 수 있는 응용 프로그램은 가용성이 높고 탄력적입니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="26baa-127">비즈니스용 Skype Server 제어판에는 응용 프로그램 이름, 실행 중인 풀, 사용 하는 포트 등이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="26baa-128">신뢰할 수 있는 응용 프로그램 목록 보기</span><span class="sxs-lookup"><span data-stu-id="26baa-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="26baa-129">CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 Csserveradministrator 관리자 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="26baa-130">비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [RBAC (역할 기반 액세스 제어](../plan-your-deployment/security/role-based-access-control-rbac.md))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26baa-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="26baa-131">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="26baa-132">왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **신뢰할 수 있는 응용 프로그램**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="26baa-133">필요한 경우 **신뢰할 수 있는 응용 프로그램** 페이지에서 열 머리글을 클릭 하 여 응용 프로그램을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="26baa-134">신뢰할 수 있는 응용 프로그램 정보 보기</span><span class="sxs-lookup"><span data-stu-id="26baa-134">View trusted application information</span></span>

<span data-ttu-id="26baa-135">Windows PowerShell 및 **CsTrustedApplication** cmdlet을 사용 하 여 신뢰 된 응용 프로그램에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="26baa-136">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="26baa-137">신뢰할 수 있는 응용 프로그램을 보려면</span><span class="sxs-lookup"><span data-stu-id="26baa-137">To view trusted applications</span></span>

<span data-ttu-id="26baa-138">신뢰할 수 있는 모든 응용 프로그램을 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="26baa-139">이 명령은 각 신뢰 하는 응용 프로그램에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="26baa-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="26baa-140">자세한 내용은 [Get-help CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26baa-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
