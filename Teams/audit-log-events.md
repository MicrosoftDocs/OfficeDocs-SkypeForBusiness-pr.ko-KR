---
title: Microsoft 팀에서 이벤트 감사 로그 검색
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Office 365 감사 로그에서 Microsoft 팀 데이터를 검색 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90645a7c2ffde142bdda80855b613877afc2f19e
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183638"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="87b74-103">Microsoft 팀에서 이벤트 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="87b74-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="87b74-104">감사 로그는 Office 365 서비스에서 특정 작업을 조사 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="87b74-105">팀의 경우 감사 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="87b74-106">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="87b74-106">Team creation</span></span>

-   <span data-ttu-id="87b74-107">팀 삭제</span><span class="sxs-lookup"><span data-stu-id="87b74-107">Team deletion</span></span>

-   <span data-ttu-id="87b74-108">채널 추가 됨</span><span class="sxs-lookup"><span data-stu-id="87b74-108">Added channel</span></span>

-   <span data-ttu-id="87b74-109">설정 변경 됨</span><span class="sxs-lookup"><span data-stu-id="87b74-109">Changed setting</span></span>

<span data-ttu-id="87b74-110">Office 365에서 감사 되는 활동의 전체 목록을 보려면 [office 365 보안 & 준수 센터에서 감사 로그 검색](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)을 읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="87b74-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="87b74-111">팀에서 감사 설정</span><span class="sxs-lookup"><span data-stu-id="87b74-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="87b74-112">감사 데이터를 보려면 먼저 **보안 & 준수 센터**()https://protection.office.com)에서 감사를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="87b74-113">감사를 설정 하려면 [Office 365 감사 로그 검색 설정 또는 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87b74-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="87b74-114">감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="87b74-115">감사 로그에서 팀 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="87b74-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="87b74-116">감사 로그를 검색 하려면 [보안 & 준수 센터로](https://go.microsoft.com/fwlink/?linkid=855775)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="87b74-117">**검색 & 조사**에서 **감사 로그 검색**을 선택 합니다. ![감사 로그 검색 페이지 스크린샷](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="87b74-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>

2.  <span data-ttu-id="87b74-118">**검색** 을 사용 하 여 감사 하려는 활동, 날짜 및 사용자를 기준으로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="87b74-119">추가 분석을 위해 결과를 Excel로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="87b74-120">감사 데이터는 감사가 설정 된 경우 감사 로그에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="87b74-121">비디오: TechTip: 팀에서 감사 로그 검색 사용</span><span class="sxs-lookup"><span data-stu-id="87b74-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="87b74-122">Office 365 보안 & 준수 센터에서 팀에 대 한 감사 로그 검색을 수행 하는 방법을 보여 주는 팀을 위한 프로그램 관리자 인 a Ansuman에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b74-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






