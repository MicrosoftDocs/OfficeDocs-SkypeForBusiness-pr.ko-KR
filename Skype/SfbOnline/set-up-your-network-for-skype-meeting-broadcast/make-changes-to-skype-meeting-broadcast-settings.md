---
title: 조직의 Skype 모임 브로드캐스트 설정을 변경할 수 있습니다.
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
description: Skype 모임 브로드캐스트를 사용 하도록 설정 하 고 해당 모임에 대 한 설정 및 정책을 변경할 수 있습니다.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753413"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="3a34d-103">조직의 Skype 모임 브로드캐스트 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a34d-104">Microsoft 팀 관리 센터에서 비즈니스용 Skype 관리 센터 (레거시 포털)를 대체 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="3a34d-105">비즈니스용 Skype 관리에 대 한 모든 설정이 이제 팀 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="3a34d-106">팀 관리 센터에서 비즈니스용 Skype 기능을 관리 하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [AZURE AD 관리자 역할이](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="3a34d-107">자세히 알아보려면 [Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a34d-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="3a34d-108">Skype 모임 브로드캐스트를 사용 하도록 설정 하 고 해당 모임에 대 한 설정 및 정책을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="3a34d-109">**Skype 모임 브로드캐스트 사용** Skype 모임 브로드캐스트를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="3a34d-110">Skype 모임 브로드캐스트를 사용 하도록 설정한 후에는 [Skype 모임 브로드캐스트에 맞게 네트워크를 설정](set-up-your-network-for-skype-meeting-broadcast.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="3a34d-111">비즈니스 외부 사용자에 대 한 웹 세미나 진행 및 기타 브로드캐스트를 유지 하려는 경우이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="3a34d-112">**내 조직에 대해 Skype 모임 브로드캐스트 미리 보기 기능 사용** 비즈니스용 Skype 고객 프로그램은 새 제품 및 기능에 대 한 초기 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="3a34d-113">이렇게 하면 조직에서 사용 하는 작업을 살펴보고 자신의 환경에서 새로운 기능을 테스트 하 고 사용자 의견을 제공 하 여 제품 빌드를 일반 공개로 릴리스할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="3a34d-114">비즈니스용 Skype preview</span><span class="sxs-lookup"><span data-stu-id="3a34d-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="3a34d-115">**이끌이가 익명 모임 일정을 예약할 수 있도록 허용** 이렇게 하면 이끌이는 해당 조직 외부의 모든 사용자가 로그인 필요 없이 참가할 수 있도록 하는 브로드캐스트 이벤트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="3a34d-116">**브로드캐스트 모임 기록 허용** 이렇게 하면 발표자 또는 이끌이만 모임을 녹음/녹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="3a34d-117">**참석자를 위한 헬프데스크 지원 URL** 모임 브로드캐스트 참석자에 대 한 링크를 입력 하 여 브로드캐스트 모임에 연결 하거나 참석 하는 데 도움이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34d-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3a34d-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3a34d-118">Related topics</span></span>

[<span data-ttu-id="3a34d-119">Skype 모임 브로드캐스트의 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="3a34d-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
