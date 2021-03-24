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
description: '비즈니스용 Skype를 설정하여 공동 작업자의 가용성을 볼 수 있는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 807b2dd15b3bdbe1fac42192ed9052b26bf1f256
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093492"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="01342-103">비즈니스용 Skype Online에서 현재 상태 구성</span><span class="sxs-lookup"><span data-stu-id="01342-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01342-104">Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="01342-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="01342-105">이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01342-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="01342-106">Teams 관리 센터에서 [비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 글로벌 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01342-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="01342-107">자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01342-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="01342-108">기본적으로 비즈니스용 Skype를 사용하여 조직의 사용자 중 하나와 통신할 수 있는 모든 사용자도 해당 사람이 온라인인지 여부를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01342-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="01342-109">비즈니스용 Skype는 사람이 온라인, 모임, 오프라인 또는 다른 표시기에서 사용할 수 있는지 여부를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="01342-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![비즈니스용 Skype에서 개인의 온라인 상태의 예입니다.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="01342-111">비즈니스의 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 모든 사용자에 대한 관리자로 비즈니스용 Skype에서 자신의 온라인 존재를 보는 사람을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01342-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="01342-112">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="01342-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="01342-113">관리 센터로 > 비즈니스용 Skype 센터로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="01342-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="01342-114">비즈니스용 **Skype 관리 센터에서** 조직 을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="01342-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="01342-115">현재 **상태 개인 정보 모드에서** 다음 설정 중 하나를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01342-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="01342-116">**설정**</span><span class="sxs-lookup"><span data-stu-id="01342-116">**Setting**</span></span>|<span data-ttu-id="01342-117">**사용자의 현재 상태 볼 수 있는 사용자**</span><span class="sxs-lookup"><span data-stu-id="01342-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01342-118">**현재 상태 정보를 자동으로 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="01342-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="01342-119">사용자의 외부 또는 차단 목록에 추가되지 않은 비즈니스용  Skype  사용자는 해당 사용자의 온라인 현재 상태도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01342-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="01342-120">**사용자의 연락처에만 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="01342-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="01342-121">외부 또는 차단된 목록에 추가하지 않은 사람의  연락처 목록에 있는 모든 **사람이 나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="01342-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="01342-122">개인은 비즈니스용 Skype 앱인 설정 도구 옵션에서 기본 설정을 **오버라이드할**  >  **수**  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="01342-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="01342-123">비즈니스용 Skype에서 사용자가 변경할 수 있는 내용에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01342-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="01342-124">비즈니스용 Skype에서 현재 상태 정보에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="01342-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="01342-125">비즈니스용 Skype에서 상태 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="01342-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="01342-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="01342-126">Related topics</span></span>

[<span data-ttu-id="01342-127">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="01342-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="01342-128">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="01342-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)