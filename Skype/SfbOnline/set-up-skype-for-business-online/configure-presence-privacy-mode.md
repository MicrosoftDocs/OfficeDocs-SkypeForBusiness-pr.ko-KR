---
title: 현재 상태 개인 정보 모드 구성
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- ms.lync.lac.OrgPresencePrivacy
description: '사용자가 자신의 가용성을 보는 방법을 더 잘 제어할 수 있도록 사용자에 대한 개인 정보 모드를 설정하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239955"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="e99a4-103">현재 상태 개인 정보 모드 구성</span><span class="sxs-lookup"><span data-stu-id="e99a4-103">Configure presence privacy mode</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="e99a4-104">Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="e99a4-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="e99a4-105">관리에 대한 모든 비즈니스용 Skype 관리 센터에 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99a4-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="e99a4-106">전역 관리자 또는 비즈니스용 Skype [관리자의 Azure AD](/azure/active-directory/roles/permissions-reference) 관리자 역할이 비즈니스용 Skype 관리 센터에서 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99a4-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="e99a4-107">자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e99a4-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="e99a4-108">비즈니스용 Skype 온라인 현재 상태 설정은 사용자에게 사용할 수 있는지, 모임에서든 사무실에서 사용할 수 있는지를 볼 수 있는 사용자에 대한 더 많은 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e99a4-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="e99a4-109">현재 상태 및 비즈니스용 Skype 설정에 대한 자세한 내용은 온라인에서 현재 [상태 비즈니스용 Skype 참조하세요.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="e99a4-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="e99a4-110">조직의 모든 사용자에 대한 기본 온라인 상태 설정 선택</span><span class="sxs-lookup"><span data-stu-id="e99a4-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="e99a4-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e99a4-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="e99a4-112">조직 비즈니스용 Skype 관리 센터 > 일반 > **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="e99a4-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="e99a4-113">현재 **상태 개인 정보 모드에서** 설정을 선택한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e99a4-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="e99a4-114">**설정**</span><span class="sxs-lookup"><span data-stu-id="e99a4-114">**Setting**</span></span>|<span data-ttu-id="e99a4-115">**Who 사용자의 현재 상태 보기**</span><span class="sxs-lookup"><span data-stu-id="e99a4-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e99a4-116">**현재 상태 정보를 자동으로 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="e99a4-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="e99a4-117">외부 비즈니스용 Skype 차단된 개인 정보 그룹에  속하지 않는 모든 사용자입니다. </span><span class="sxs-lookup"><span data-stu-id="e99a4-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="e99a4-118">**사용자의 연락처에만 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="e99a4-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="e99a4-119">외부 또는 차단된 개인 정보 그룹에 속하지 않는 사용자의 연락처 목록의 **모든** 사용자입니다. </span><span class="sxs-lookup"><span data-stu-id="e99a4-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="e99a4-120">개별 사용자는 옵션 대화 상자에서 이 비즈니스용 Skype **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99a4-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="e99a4-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e99a4-121">Related topics</span></span>
[<span data-ttu-id="e99a4-122">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e99a4-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e99a4-123">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="e99a4-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
