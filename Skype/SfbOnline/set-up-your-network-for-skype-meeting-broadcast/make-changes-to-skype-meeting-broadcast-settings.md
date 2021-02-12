---
title: 조직의 Skype 모임 브로드캐스트 설정 변경
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: Skype 모임 브로드캐스트를 사용하도록 설정하고 해당 모임의 설정 및 정책을 변경할 수 있습니다.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753413"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="869bc-103">조직의 Skype 모임 브로드캐스트 설정 변경</span><span class="sxs-lookup"><span data-stu-id="869bc-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="869bc-104">Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="869bc-105">이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="869bc-106">Teams 관리 센터에서 비즈니스용 Skype 기능을 관리하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="869bc-107">자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="869bc-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="869bc-108">Skype 모임 브로드캐스트를 사용하도록 설정하고 해당 모임의 설정 및 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="869bc-109">**Skype 모임 브로드캐스트 사용** Skype 모임 브로드캐스트를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="869bc-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="869bc-110">Skype 모임 브로드캐스트를 사용하도록 설정한 후 Skype 모임 브로드캐스트에 대한 [네트워크를 설정해야 합니다.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="869bc-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="869bc-111">비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보유하려는 경우 이 단계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="869bc-112">**조직에 Skype 모임 브로드캐스트 미리 보기 기능 사용** 비즈니스용 Skype 고객 프로그램은 새로운 제품 및 기능에 대한 초기 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="869bc-113">이렇게 하면 제품 빌드를 일반 대중에게 릴리스하기 전에 조직에서 사용자 환경에서 새로운 기능을 테스트하고 피드백을 제공하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="869bc-114">비즈니스용 Skype 미리 보기</span><span class="sxs-lookup"><span data-stu-id="869bc-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="869bc-115">**이끌이가 익명 모임을 예약할 수 있도록 허용** 이렇게 하면 이끌이가 조직 외부의 모든 사용자가 로그인할 필요 없이 참가할 수 있는 브로드캐스트 이벤트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="869bc-116">**브로드캐스트 모임 녹화 허용** 이렇게 하면 발표자 또는 이끌이가 기록해야 하는 모든 모임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="869bc-117">**참석자에 대한 기술** 지원 기술 지원 URL 브로드캐스트 모임에 연결하거나 참석하는 데 도움이 필요한 경우 모임 브로드캐스트 참석자에 대한 링크를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="869bc-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="869bc-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="869bc-118">Related topics</span></span>

[<span data-ttu-id="869bc-119">Skype 모임 브로드캐스트의 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="869bc-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
