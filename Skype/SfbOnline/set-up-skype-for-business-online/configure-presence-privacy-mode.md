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
description: '사용자의 사용 가능 시간을 보다 효율적으로 제어할 수 있도록 사용자에 대 한 개인 정보 모드를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: f0f9237f701be219a9cbce9a44704cbb582f48d4
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739186"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="bbd6e-103">현재 상태 개인 정보 모드 구성</span><span class="sxs-lookup"><span data-stu-id="bbd6e-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbd6e-104">Microsoft 팀 관리 센터에서 비즈니스용 Skype 관리 센터 (레거시 포털)를 대체 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="bbd6e-105">비즈니스용 Skype 관리에 대 한 모든 설정이 이제 팀 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="bbd6e-106">자세히 알아보려면 [Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="bbd6e-107">비즈니스용 Skype Online 현재 상태 설정을 사용 하면 사용자가 대화 상대를 볼 수 있는지, 모임 중이 든, 부재 중에 대 한 제어권이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-107">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="bbd6e-108">비즈니스용 Skype 현재 상태 및 개인 정보 설정에 대 한 자세한 내용은 [비즈니스용 Skype Online에서 현재 상태 구성을](configure-presence-in-skype-for-business-online.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-108">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="bbd6e-109">조직의 모든 사용자에 대 한 기본 온라인 상태 설정 선택</span><span class="sxs-lookup"><span data-stu-id="bbd6e-109">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="bbd6e-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="bbd6e-110"><a name="__top"> </a></span></span>

1. <span data-ttu-id="bbd6e-111">비즈니스용 Skype Online 관리 센터 > **조직 > 일반**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-111">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="bbd6e-112">**현재 상태 개인 정보 모드**에서 설정을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-112">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="bbd6e-113">**설정**</span><span class="sxs-lookup"><span data-stu-id="bbd6e-113">**Setting**</span></span>|<span data-ttu-id="bbd6e-114">**사용자의 현재 상태를 볼 수 있는 사용자**</span><span class="sxs-lookup"><span data-stu-id="bbd6e-114">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bbd6e-115">**자동으로 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="bbd6e-115">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="bbd6e-116">**외부** 대화 상대 또는 **차단** 된 개인 정보 그룹에 속하지 않는 비즈니스용 Skype 사용자</span><span class="sxs-lookup"><span data-stu-id="bbd6e-116">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="bbd6e-117">**사용자의 대화 상대 에게만 현재 상태 정보 표시**</span><span class="sxs-lookup"><span data-stu-id="bbd6e-117">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="bbd6e-118">**외부** 또는 **차단** 된 개인 정보 그룹에 속하지 않는 사용자의 연락처 목록에 있는 모든 사람</span><span class="sxs-lookup"><span data-stu-id="bbd6e-118">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="bbd6e-119">개인 사용자는 비즈니스용 Skype **옵션** 대화 상자에서이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd6e-119">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="bbd6e-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bbd6e-120">Related topics</span></span>
[<span data-ttu-id="bbd6e-121">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="bbd6e-121">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="bbd6e-122">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="bbd6e-122">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
