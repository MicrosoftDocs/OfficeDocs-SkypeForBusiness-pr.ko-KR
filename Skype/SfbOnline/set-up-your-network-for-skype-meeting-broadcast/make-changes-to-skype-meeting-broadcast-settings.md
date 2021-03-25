---
title: 조직의 Skype 모임 브로드캐스트 설정을 변경합니다.
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
description: Skype 모임 브로드캐스트를 사용하도록 설정하고 해당 모임에 대한 설정 및 정책을 변경할 수 있습니다.
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106554"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="69705-103">조직의 Skype 모임 브로드캐스트 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69705-104">Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="69705-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="69705-105">이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69705-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="69705-106">Teams 관리 센터에서 [비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 글로벌 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="69705-107">자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69705-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="69705-108">Skype 모임 브로드캐스트를 사용하도록 설정하고 해당 모임에 대한 설정 및 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69705-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="69705-109">**Skype 모임 브로드캐스트 사용** Skype 모임 브로드캐스트를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="69705-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="69705-110">Skype 모임 브로드캐스트를 사용하도록 설정한 후 Skype 모임 브로드캐스트에 대한 [네트워크를 설정해야 합니다.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="69705-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="69705-111">비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보류하려는 경우 이 단계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="69705-112">**조직에 Skype 모임 브로드캐스트 미리 보기 기능 사용** 비즈니스용 Skype 고객 프로그램은 새 제품 및 기능에 대한 초기 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="69705-113">이렇게 하면 조직에서 제품 빌드를 일반 대중에게 릴리스하기 전에 사용자 환경의 새 기능을 테스트하고 피드백을 줄 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="69705-114">비즈니스용 Skype 미리 보기</span><span class="sxs-lookup"><span data-stu-id="69705-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="69705-115">**주최자가 익명 모임 예약 허용** 이렇게 하면 조직 외부의 모든 사용자가 로그인할 필요 없이 참가할 수 있는 브로드캐스트 이벤트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69705-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="69705-116">**브로드캐스트 모임을 녹화할 수 있도록 허용** 이렇게 하면 발표자 또는 이끌이가 기록해야 하는 모든 모임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69705-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="69705-117">**참석자에 대한 헬프데스크 지원 URL** 브로드캐스트 모임을 연결하거나 참석하는 데 도움이 필요한 경우 사용할 모임 브로드캐스트 참석자에 대한 링크를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69705-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="69705-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="69705-118">Related topics</span></span>

[<span data-ttu-id="69705-119">Skype 모임 브로드캐스트의 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="69705-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
