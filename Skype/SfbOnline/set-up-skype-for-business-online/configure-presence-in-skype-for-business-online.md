---
title: 비즈니스용 Skype Online에서 현재 상태 구성
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: '동료의 가용성을 확인할 수 있도록 비즈니스용 Skype를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: f2b149a2b6277d356fe4478ee6de12ec6b078f48
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753453"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="5d021-103">비즈니스용 Skype Online에서 현재 상태 구성</span><span class="sxs-lookup"><span data-stu-id="5d021-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d021-104">Microsoft 팀 관리 센터에서 비즈니스용 Skype 관리 센터 (레거시 포털)를 대체 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="5d021-105">비즈니스용 Skype 관리에 대 한 모든 설정이 이제 팀 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="5d021-106">팀 관리 센터에서 비즈니스용 Skype 기능을 관리 하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [AZURE AD 관리자 역할이](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="5d021-107">자세히 알아보려면 [Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d021-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="5d021-108">기본적으로 비즈니스용 Skype를 사용 하 여 조직 내 사용자 중 하 나와 통신할 수 있는 사람은 누구 든 지 온라인 상태 인지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="5d021-109">비즈니스용 Skype에서 온라인, 모임, 오프 라인 또는 다른 표시기를 볼 수 있는지 여부를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![비즈니스용 Skype에서 사용자의 온라인 상태에 대 한 예입니다.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="5d021-111">비즈니스의 모든 사용자에 대 한 **[관리자](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 는 비즈니스용 Skype에서 온라인 상태를 볼 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="5d021-112">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="5d021-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="5d021-113">관리 센터로 이동 하 > **관리**센터  >  **비즈니스용 Skype**.</span><span class="sxs-lookup"><span data-stu-id="5d021-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="5d021-114">**비즈니스용 Skype 관리 센터**에서 **조직을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="5d021-115">**현재 상태 개인 정보 모드**에서 다음 설정 중 하나를 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="5d021-116">**설정**</span><span class="sxs-lookup"><span data-stu-id="5d021-116">**Setting**</span></span>|<span data-ttu-id="5d021-117">**사용자의 현재 상태를 볼 수 있는 사용자**</span><span class="sxs-lookup"><span data-stu-id="5d021-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d021-118">**자동으로 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="5d021-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="5d021-119">사용자의 **외부** 또는 **차단** 목록에 추가 되지 않은 기업의 모든 비즈니스용 Skype 사용자는 해당 사용자의 온라인 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d021-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="5d021-120">**사용자의 대화 상대 에게만 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="5d021-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="5d021-121">**외부** 또는 **차단** 목록에 추가 되지 않은 사용자의 연락처 목록에 있는 모든 사람</span><span class="sxs-lookup"><span data-stu-id="5d021-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="5d021-122">사용자는 비즈니스용 Skype 앱에서 기본 설정을 재정의할 수 있습니다 ( **설정**  >  **도구**  >  **옵션**).</span><span class="sxs-lookup"><span data-stu-id="5d021-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="5d021-123">비즈니스용 Skype에서 사용자가 변경할 수 있는 사항에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d021-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="5d021-124">비즈니스용 Skype에서 현재 상태 정보에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="5d021-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="5d021-125">비즈니스용 Skype에서 상태 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="5d021-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="5d021-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5d021-126">Related topics</span></span>

[<span data-ttu-id="5d021-127">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="5d021-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5d021-128">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="5d021-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


