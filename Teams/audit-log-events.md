---
title: Microsoft 팀에서 이벤트 감사 로그 검색
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Office 365 감사 로그에서 Microsoft 팀 데이터를 검색 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341626"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="8c9de-103">Microsoft 팀에서 이벤트 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="8c9de-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8c9de-104">감사 로그는 Office 365 서비스에서 특정 작업을 조사 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="8c9de-105">팀의 경우 감사 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="8c9de-106">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="8c9de-106">Team creation</span></span>

- <span data-ttu-id="8c9de-107">팀 삭제</span><span class="sxs-lookup"><span data-stu-id="8c9de-107">Team deletion</span></span>

- <span data-ttu-id="8c9de-108">채널 추가 됨</span><span class="sxs-lookup"><span data-stu-id="8c9de-108">Added channel</span></span>

- <span data-ttu-id="8c9de-109">설정 변경 됨</span><span class="sxs-lookup"><span data-stu-id="8c9de-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="8c9de-110">개인 채널의 감사 이벤트도 팀 및 표준 채널의 경우에도 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="8c9de-111">Office 365에서 감사 되는 활동의 전체 목록을 보려면 [office 365 보안 & 준수 센터에서 감사 로그 검색](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)을 읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="8c9de-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="8c9de-112">팀에서 감사 설정</span><span class="sxs-lookup"><span data-stu-id="8c9de-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="8c9de-113">감사 데이터를 보려면 먼저 [보안 & 준수 센터](https://protection.office.com)에서 감사를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8c9de-114">감사를 설정 하려면 [Office 365 감사 로그 검색 설정 또는 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c9de-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c9de-115">감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="8c9de-116">감사 로그에서 팀 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="8c9de-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="8c9de-117">감사 로그를 검색 하려면 [보안 & 준수 센터로](https://go.microsoft.com/fwlink/?linkid=855775)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="8c9de-118">**검색**에서 **감사 로그 검색**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="8c9de-119">**검색** 을 사용 하 여 감사 하려는 활동, 날짜 및 사용자를 기준으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="8c9de-120">추가 분석을 위해 결과를 Excel로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c9de-121">감사 데이터는 감사가 설정 된 경우 감사 로그에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="8c9de-122">외부 사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="8c9de-122">External user scenario</span></span>

<span data-ttu-id="8c9de-123">비즈니스 측면에서 눈을 지속적으로 유지할 수 있는 한 가지 시나리오는 외부 사용자를 팀 환경에 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="8c9de-124">외부 사용자가 사용 하도록 설정 된 경우에는 현재 상태 모니터링이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="8c9de-126">이 정책을 통해 외부 사용자 추가를 모니터링 하 고, 비즈니스 요구에 따라 심각도를 설정 하 고, (이 경우에는) 단일 활동으로 설정한 다음, 구체적 으로만 모니터링 하는 매개 변수를 설정 하는 것을 허용 합니다. 비 내부 사용자의 경우이 활동을 Microsoft 팀으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="8c9de-127">그런 다음 활동 로그에서이 정책의 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsExternalUserList.png)

<span data-ttu-id="8c9de-129">여기서 설정한 정책과 일치 하는 항목을 검토 하 고 필요에 따라 조정을 수행 하거나 결과를 내보내 다른 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="8c9de-130">대량 삭제 시나리오</span><span class="sxs-lookup"><span data-stu-id="8c9de-130">Mass delete scenario</span></span>

<span data-ttu-id="8c9de-131">위에서 설명한 대로 삭제 시나리오를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="8c9de-132">팀 사이트의 대량 삭제를 모니터링 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![대량 팀 삭제 검색에 대 한 정책의 설정을 보여 주는 정책 만들기 페이지 스크린샷](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="8c9de-134">화면에 표시 되는 것 처럼이 정책에 대해 다양 한 매개 변수를 설정 하 여 심각도, 단일 또는 반복 작업을 비롯 한 팀 삭제를 모니터링할 수 있으며,이를 팀 및 사이트 삭제로 제한 하는 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c9de-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="8c9de-135">이 작업은 서식 파일과 관계 없이 수행할 수 있으며 조직의 요구 사항에 따라이 정책을 기반으로 만든 서식 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="8c9de-136">비즈니스에 사용할 정책을 설정한 후에는 이벤트가 트리거될 때 활동 로그에서 결과를 검토 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![대량 삭제에 의해 트리거되는 이벤트 목록의 스크린샷](media/TeamsMassDeleteList.png)

<span data-ttu-id="8c9de-138">설정한 정책에 맞게 필터링 하 여 해당 정책의 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="8c9de-139">활동 로그에서 발생 하는 결과가 만족 스 럽 지 않은 경우 (결과가 많은 경우 또는 아무것도 표시 되지 않는 경우)에는 필요한 사항에 맞게 쿼리를 세부적으로 조정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="8c9de-140">비디오: TechTip: 팀에서 감사 로그 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8c9de-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="8c9de-141">Office 365 보안 & 준수 센터에서 팀에 대 한 감사 로그 검색을 수행 하는 방법을 보여 주는 팀을 위한 프로그램 관리자 인 a Ansuman에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9de-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
