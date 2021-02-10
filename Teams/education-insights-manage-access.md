---
title: Education Insights에 대한 사용자 액세스 관리
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams의 Education Insights에 대한 사용자 액세스를 관리합니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145942"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="14871-103">Education Insights에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="14871-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="14871-104">이 문서는 [Microsoft Teams의 Education Insights](class-insights.md)에 대한 사용자 액세스를 관리하는 데 필요한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="14871-105">교육 리더, 학군 리더, 교장, 교사 부장, 상담 교사, 학습 분야 책임자, 프로그램 디렉터, 사회복지사, 심리학자에게 사용 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="14871-106">교육자는 수업 팀을 맡게 되면 *자동으로* 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="14871-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="14871-107">조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조를 올바르게 매핑하도록 [SIS(학생 정보 시스템)에서 데이터를 가져와야](education-insights-sis-data-sync.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="14871-108">전역 관리자만이 Insights에 대한 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14871-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="14871-109">모든 교육 리더가 각 학교를 이해할 수 있는 데이터와 신속하게 문제를 식별하고 교육자에게 지원을 제공하도록 모든 교육 리더의 Insights를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14871-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="14871-110">파일럿을 실행 중인 경우라도 모든 교육 리더에게 Insights를 사용하는 것이 여전히 도움이 될 수 있으나 파일럿 사용자 그룹에 대한 통신만 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="14871-111">사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="14871-111">Grant permissions</span></span>

* <span data-ttu-id="14871-112">Insights 앱을 열고 **설정** 을 클릭한 다음 **사용자 권한** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="설정":::

* <span data-ttu-id="14871-114">**사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-114">Select **Add users**.</span></span>
* <span data-ttu-id="14871-115">각 사용자의 사용자 이름 또는 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="14871-116">사용 권한 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-116">Select the permission level:</span></span>
  * <span data-ttu-id="14871-117">**모든 조직에 대한 액세스** 는 사용자가 모든 수준에서 모든 조직 단위를 본다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="14871-118">**특정 학교에 대한 액세스** 는 사용자가 선택한 학교를 본다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="14871-119">입력을 시작하고 목록에서 학교를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="14871-120">여러 학교를 함께 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14871-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="14871-121">**새 사용자 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="사용 권한 부여":::

> [!NOTE]
> <span data-ttu-id="14871-123">사용 권한이 필요한 교육 리더와 이들이 책임을 맡고 있는 조직 단위에게만 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="14871-124">특정 조직에 대한 사용자 권한이 필요한지 여부가 불확실한 경우, 해당 기관의 개인 정보 문제 전문가(법률 또는 HR 직원)에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="14871-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="14871-125">사용 권한 편집</span><span class="sxs-lookup"><span data-stu-id="14871-125">Edit permissions</span></span>
* <span data-ttu-id="14871-126">특정 사용자를 선택한 다음 **사용자 권한 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="14871-127">사용 권한 수준 또는 학교 목록을 업데이트하고 **사용 권한 업데이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="사용 권한 편집":::

## <a name="remove-permissions"></a><span data-ttu-id="14871-129">사용 권한 제거</span><span class="sxs-lookup"><span data-stu-id="14871-129">Remove permissions</span></span>
* <span data-ttu-id="14871-130">제거하려는 사용자를 선택한 다음 **사용자 제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14871-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="14871-131">이러한 사용자는 더 이상 조직 수준의 Insights에 액세스할 수 없지만, 수업 팀을 맡은 경우 수업 수준 Insights에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14871-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="사용 권한 제거":::
