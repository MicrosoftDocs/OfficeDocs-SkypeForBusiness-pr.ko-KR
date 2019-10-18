---
title: 보고서를 실행 하 여 활성 StaffHub 사용 현황 표시
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 보고서를 실행 하 여 조직의 활성 StaffHub 사용자 목록을 가져오는 방법을 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569666"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="718ec-103">보고서를 실행 하 여 활성 StaffHub 사용 현황 표시</span><span class="sxs-lookup"><span data-stu-id="718ec-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="718ec-104">2019 년 12 월 31 일에 효력을 StaffHub Microsoft는 곧 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="718ec-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="718ec-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="718ec-107">StaffHub는 2019 년 12 월 31 일에 모든 사용자의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="718ec-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="718ec-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="718ec-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="718ec-110">이 문서의 단계를 사용 하 여 보고서를 실행 하 여 조직의 활성 StaffHub 사용자 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="718ec-111">이 정보는 [StaffHub 팀을 Microsoft 팀으로 이동할](move-staffhub-teams-to-shifts-in-teams.md)준비를 할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="718ec-112">StaffHub에서 팀으로 전환할 때, 보고서에서 통신에 포함 해야 하는 사람을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="718ec-113">이 문서의 단계를 수행 하려면 Azure AD Premium이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="718ec-114">Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="718ec-115">왼쪽 창에서 **Azure Active Directory** 리소스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="718ec-116">**모니터링**에서 **로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="718ec-117">**응용 프로그램**에서 **Microsoft StaffHub**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="718ec-118">보고서에 대해 원하는 날짜 범위를 설정한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="718ec-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![활성 StaffHub 사용법을 표시 하는 방법에 대 한 단계를 보여 주는 스크린샷](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="718ec-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="718ec-120">Related topics</span></span>

- [<span data-ttu-id="718ec-121">Microsoft 팀에서 Microsoft StaffHub 팀을 교대으로 옮기기</span><span class="sxs-lookup"><span data-stu-id="718ec-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
