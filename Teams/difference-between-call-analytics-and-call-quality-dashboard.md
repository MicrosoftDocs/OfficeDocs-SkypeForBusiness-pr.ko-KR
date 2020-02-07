---
title: 통화 분석 및 통화 품질 대시보드
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 통화 분석 및 통화 품질 대시보드 및이를 사용 하 여 통화 품질 문제를 모니터링 하 고 해결 하는 시기에 대해 알아봅니다.
ms.openlocfilehash: be63c4e227e74e242169ec5c3b5e0b01a43a0730
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824914"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="0d508-103">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="0d508-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="0d508-104">Microsoft 팀과 비즈니스용 Skype는 통화 품질 문제를 모니터링 하 고 문제를 해결 하는 두 가지 방법, 즉, Call Analytics 및 통화 품질 대시보드 (CQD)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="0d508-105">이 문서에서는 이러한 두 가지 방법에 대해 설명 하 고 각 항목을 사용 하는 방법을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="0d508-106">통화 분석 및 CQD는 병렬로 실행 되며 독립적으로 또는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="0d508-107">예를 들어 통신 지원 전문가에 게 전화 문제 해결에 대 한 추가 지원이 필요 하다 고 판단 한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-107">For example, say that a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="0d508-108">커뮤니케이션 지원 전문가는 커뮤니케이션 지원 엔지니어에 게 통화를 전달 하 고,이는 통화 분석에서 통신 지원 전문가 보다 더 많은 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="0d508-109">통신 지원 엔지니어가 네트워크 엔지니어에 게 문제를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="0d508-110">네트워크 엔지니어가 전체 사이트 관련 문제가 통화 문제의 원인이 될 수 있는지를 확인 하기 위해 CQD를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-110">The network engineer can check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="0d508-111">통화 분석의 정의 및 사용 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0d508-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="0d508-112">**이제 [Microsoft 팀 관리 센터](https://admin.teams.microsoft.com)에서 통화 분석을 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0d508-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="0d508-113">사용자의 모든 통화 정보 및 데이터를 보려면 사용자 프로필 페이지의 **통화 기록** 탭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-113">To see all call information and data for a user, use the **Call History** tab on a user's profile page.</span></span> <span data-ttu-id="0d508-114">탭을 보려면 대시보드에서 사용자를 검색 하거나 왼쪽 탐색 모음의 **사용자** 탭에서 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-114">To see the tab, either search for the user from the dashboard or find the user from the **Users** tab in the left navigation bar.</span></span>

<span data-ttu-id="0d508-115">통화 분석에는 Microsoft 팀 또는 비즈니스용 Skype 테 넌 트 계정에서 각 사용자의 통화 및 모임과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-115">Call Analytics shows detailed information about the devices, networks, and connectivity related to the calls and meetings for each user in a Microsoft Teams or Skype for Business tenant account.</span></span> <span data-ttu-id="0d508-116">이 사용자에 게이 오후의 통화가 좋지 않은 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0d508-116">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="0d508-117">전화 분석을 사용 하 여 Office 365 관리자 또는 교육 된 헬프 데스크 상담원은 Microsoft 팀과 비즈니스용 Skype에서 통화 품질과 연결 문제를 해결 하기 위해 통화와 관련 된 장치, 네트워크, 연결, 기타 요소를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-117">With Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to a call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="0d508-118">Microsoft 팀 관리 센터에서 사용자에 대 한이 정보를 보려면 사용자 세부 정보 페이지에서 해당 사용자의 **통화 기록** 탭을 클릭 하 여 지난 30 일 동안 해당 사용자에 대 한 모든 통화와 모임을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-118">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page to see all calls and meetings for that user in the last 30 days.</span></span>

![모든 분석 사용자 데이터의 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="0d508-120">자세한 미디어 및 네트워킹 통계를 포함 하 여 지정 된 세션에 대 한 추가 정보를 얻으려면 세션을 클릭 하 여 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-120">To get additional information about a given session including detailed media and networking statistics, click a session to see the details.</span></span>

![통화 분석 사용자 세션 데이터 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="0d508-122">관리자가 아닌 사용자 (예: 외부 공급 업체의 헬프데스크 에이전트)가 통화 분석을 사용 하도록 하려면 사용 권한을 할당 하 여 통화 분석을 사용할 수 있지만 나머지 Microsoft 팀 관리 센터에 액세스할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-122">If you want non-admins (such as helpdesk agents from an external vendor) to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span>
  
- <span data-ttu-id="0d508-123">**통신 지원이 포함 된 헬프데스크 에이전트 전문가 권한**: 상담원은 통화 분석에서 제한 된 데이터 집합과 PII (개인 식별 가능 정보)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-123">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="0d508-124">통화 문제를 해결할 수 있지만, 커뮤니케이션 지원 엔지니어에 게 모임에 대 한 문제를 제기 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-124">They can troubleshoot calls, but they escalate problems with meetings to a communications support engineer.</span></span>
- <span data-ttu-id="0d508-125">**통신 지원 엔지니어가 사용 권한이 있는 헬프데스크 에이전트**: 상담원은 콜 분석에서 사용 가능한 모든 데이터를 확인 하 고 통화와 회의 모두의 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-125">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="0d508-126">콜 로그와 고객 정보에 대 한 모든 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-126">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="0d508-127">통신 지원 전문가 역할은 미리 보기 포털의 계층 1 지원 역할과 같으며 통신 지원 엔지니어 역할은 미리 보기 포털의 계층 2 지원 역할에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-127">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="0d508-128">통신 지원 전문가 및 통신 지원 엔지니어 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리를](using-admin-roles.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-128">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d508-129">Microsoft 팀 관리 센터에서 지원 되는 헬프데스크 에이전트 권한 및 네트워크 토폴로지 업로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-129">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0d508-130">통신 지원 전문가 및 통신 지원 엔지니어가이 포털을 사용 하 여 통화 분석 및 통화 품질 대시보드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-130">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>

<span data-ttu-id="0d508-131">통화 분석에 대 한 자세한 내용은 비즈니스용 [Skype 통화 분석 설정을](set-up-call-analytics.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-131">For details about Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="0d508-132">헬프데스크 에이전트가 통화 분석을 사용 하는 방법에 대 한 자세한 내용은 통화 [분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-132">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="0d508-133">통화 품질 대시보드의 정의 및 사용 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0d508-133">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="0d508-134">통화 분석은 관리자와 헬프데스크 상담원에 게 *특정 전화*의 통화 음질 문제를 해결 하는 데 도움이 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-134">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with *specific calls*.</span></span> <span data-ttu-id="0d508-135">콜 품질 대시보드 (CQD)는 팀 관리자, 비즈니스용 Skype 관리자, 네트워크 엔지니어가 *네트워크를 최적화*하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-135">Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers *optimize a network*.</span></span> <span data-ttu-id="0d508-136">CQD는 특정 사용자 로부터 포커스를 이동 하 고 대신 전체 팀 또는 비즈니스용 Skype 조 직에 대 한 집계 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-136">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="0d508-137">자세한 내용은 [팀과 비즈니스용 Skype Online에 대 한 통화 품질 대시보드의 기능](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-137">For more information, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="0d508-138">사용자의 잘못 된 통화 품질이 다른 많은 사용자에 게 영향을 주는 네트워크 문제로 인해 발생 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-138">Suppose a user's poor call quality is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="0d508-139">개인 통화 환경은 CQD에서 볼 수 없지만 Microsoft 팀 또는 비즈니스용 Skype를 사용 하 여 생성 된 전체 통화 품질은 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-139">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="0d508-140">CQD를 사용 하면 전체 패턴이 명확 하 게 나타날 수 있으므로 네트워크 엔지니어가 통화 품질 평가를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-140">With  CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="0d508-141">CQD는 전체 통화 품질, 서버 클라이언트 스트림, 클라이언트-클라이언트 스트림, 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 대 한 정보를 제공 하는 통화 품질 메트릭의 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-141">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![통화 품질 대시보드의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="0d508-143">CQD의 위치 향상 보고서는 사용자의 건물 내에서 통화 품질과 안정성을 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-143">CQD's Location-Enhanced Reports aggregate call quality and reliability within a user's building.</span></span> <span data-ttu-id="0d508-144">데이터를 평가 하 여 문제가 단일 사용자에 게 격리 되었는지 또는 대규모 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-144">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![통화 품질 대시보드의 위치 향상 보고서 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="0d508-146">CQD에서 빌드 또는 끝점 관련 보기를 사용 하도록 설정 하려면 관리자가 CQD의 테 넌 트 데이터 업로드 페이지에서 [빌드 또는 끝점 정보를 업로드](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-146">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span>

<span data-ttu-id="0d508-147">관리자가 아닌 사용자 (예: 헬프데스크 에이전트)가 통화 품질 대시보드를 사용 하 게 하려면 다음 역할 중 하나를 할당할 수 있으며, 여기에는 통화 품질 대시보드에 액세스 하는 데 필요한 권한도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-147">If you want non-admin users (such as helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which also have permissions needed to access Call Quality Dashboard:</span></span>

- <span data-ttu-id="0d508-148">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="0d508-148">Global Administrator</span></span>
- <span data-ttu-id="0d508-149">전역 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="0d508-149">Global Reader</span></span>
- <span data-ttu-id="0d508-150">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="0d508-150">Skype for Business Administrator</span></span>
- <span data-ttu-id="0d508-151">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="0d508-151">Teams Service Administrator</span></span>
- <span data-ttu-id="0d508-152">Teams 커뮤니케이션 관리자</span><span class="sxs-lookup"><span data-stu-id="0d508-152">Teams Communications Administrator</span></span>
- <span data-ttu-id="0d508-153">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="0d508-153">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="0d508-154">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="0d508-154">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="0d508-155">보고서 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="0d508-155">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="0d508-156">팀 의사 소통 지원 엔지니어, 팀 의사 소통 지원 전문가, 보고서 리더 역할은 CQD의 테 넌 트 데이터 업로드 페이지에서 파일을 수정 하거나 테 넌 트에 대해 CQD를 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d508-156">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="0d508-157">이러한 역할에 대 한 자세한 내용은 [Office 365 관리자 역할](/office365/admin/add-users/about-admin-roles)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-157">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="0d508-158">CQD에 대 한 자세한 내용은 microsoft 팀과 비즈니스용 Skype Online 및 [microsoft 비즈니스용 Skype online 용 통화 품질 대시보드에서 제공 되는 크기 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)에 [대 한 통화 품질 대시보드 켜기 및 사용](turning-on-and-using-call-quality-dashboard.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d508-158">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0d508-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0d508-159">Related topics</span></span>

[<span data-ttu-id="0d508-160">비디오: 통화 품질 개요</span><span class="sxs-lookup"><span data-stu-id="0d508-160">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="0d508-161">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="0d508-161">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="0d508-162">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0d508-162">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="0d508-163">Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용</span><span class="sxs-lookup"><span data-stu-id="0d508-163">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
