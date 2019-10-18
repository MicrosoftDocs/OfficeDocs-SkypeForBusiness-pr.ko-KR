---
title: Microsoft 팀 사용자 설정을 대량으로 편집
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft 팀 관리 센터에서 Microsoft 팀 사용자 설정을 대량으로 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 307edddf4dce8bd87f717fed6f3c33b11521fb7d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571893"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="2aac3-103">대량으로 Microsoft 팀 사용자 설정 편집</span><span class="sxs-lookup"><span data-stu-id="2aac3-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="2aac3-104">관리자는 Microsoft 팀 관리 센터에서 팀 사용자 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2aac3-105">**사용자** 페이지에서 계정 및 라이선스 세부 정보, 정책 및 기타 설정 편집 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="2aac3-106">사용자에 대 한 설정을 개별적으로 또는 여러 사용자가 동시에 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="2aac3-107">대량으로 사용자 설정 편집</span><span class="sxs-lookup"><span data-stu-id="2aac3-107">Edit user settings in bulk</span></span>

<span data-ttu-id="2aac3-108">Microsoft 팀 관리 센터를 사용 하 여 한 번에 여러 사용자의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="2aac3-109">한 번에 20 명의 사용자에 대 한 설정을 편집 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="2aac3-110">많은 수의 사용자에 대 한 설정을 편집 하려면 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="2aac3-111">자세한 내용은 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2aac3-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="2aac3-112">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="2aac3-113">편집 하려는 사용자를 검색 하거나 보기를 필터링 하 여 편집할 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="2aac3-114">**&#x2713;** (확인 표시) 열에서 다음 중 하나를 수행 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="2aac3-115">한 번에 하나씩 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-115">Select users one at a time.</span></span> <span data-ttu-id="2aac3-116">선택한 각 사용자 옆에 **&#x2713;** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="2aac3-117">20 명 이상의 사용자를 선택 하는 경우에는 차단 되지 않지만 선택 하는 사용자가 많을 수록 작업을 완료 하는 데 시간이 오래 걸릴 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="2aac3-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![사용자 선택을 표시 하는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="2aac3-119">테이블 맨 위에 있는 &#x2713; (확인 표시)을 클릭 하 여 모든 사용자 (최대 20 명의 사용자)를 선택한 다음, **선택 제한** 대화 상자에서 **계속 해 서 모두 선택을** 클릭 하 여 선택 영역을 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="2aac3-120">![선택 한계를 보여 주는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="2aac3-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="2aac3-121">선택한 사용자 옆에 **&#x2713;** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![20 명의 사용자가 선택 되었음을 보여 주는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="2aac3-123">**설정 편집**을 클릭 하 고 원하는 대로 변경한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aac3-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![설정 편집 창 스크린샷](media/bulk-edit-user-settings-edit-settings.png)
