---
title: 비즈니스용 Skype의 통화 관리 기능 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
description: 비즈니스용 Skype 서버 2013의 지원되는 통화 관리 기능 Enterprise Voice.
ms.openlocfilehash: 926ffe294c2819b9f68af76e61410a0ce4a9f63b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096438"
---
# <a name="plan-for-call-management-features-in-skype-for-business"></a><span data-ttu-id="25518-103">비즈니스용 Skype의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="25518-103">Plan for call management features in Skype for Business</span></span>

<span data-ttu-id="25518-104">비즈니스용 Skype 서버 2013의 지원되는 통화 관리 기능 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="25518-104">Overview of supported call-management features in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="25518-105">Enterprise Voice 통화 관리 기능은 수신 전화를 라우팅하고 받는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="25518-105">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="25518-106">비즈니스용 Skype 서버는 다음과 같은 통화 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25518-106">Skype for Business Server provides the following call management features:</span></span>

- <span data-ttu-id="25518-107">**통화 파기:** 음성 사용자가 통화를 일시적으로 중단한 다음 동일한 전화 또는 다른 전화기에서 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25518-107">**Call Park**: Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

- <span data-ttu-id="25518-108">**그룹 선택:** 음성 사용자가 통화 Pickup 그룹에 할당된 다른 음성 사용자에 대해 벨이 울리는 통화를 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="25518-108">**Group Pickup**: Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>

- <span data-ttu-id="25518-109">**응답 그룹:** 헌트 그룹 또는 IVR(대화형 음성 응답) 질문과 대답을 사용하여 수신 전화를 에이전트 그룹으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="25518-109">**Response Group**: Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

- <span data-ttu-id="25518-110">**알림**: 지정되지 않은 번호로 건 전화에 대해 메시지를 재생하거나, 전화를 다른 번호로 라우팅하거나, 두 가지를 모두 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="25518-110">**Announcement**: Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="25518-111">Enterprise Voice를 배포하려는 경우에는 이러한 통화 관리 기능 중 일부 또는 모든 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25518-111">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="25518-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="25518-112">In this section</span></span>

- [<span data-ttu-id="25518-113">통화 파킹 계획</span><span class="sxs-lookup"><span data-stu-id="25518-113">Planning for Call Parking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-call-park)

- [<span data-ttu-id="25518-114">그룹 선택 계획</span><span class="sxs-lookup"><span data-stu-id="25518-114">Planning for Group Pickup</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-group-call-pickup)

- [<span data-ttu-id="25518-115">응답 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="25518-115">Planning for Response Groups</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-response-groups)

- [<span data-ttu-id="25518-116">알림 계획</span><span class="sxs-lookup"><span data-stu-id="25518-116">Planning for Announcements</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-announcements)