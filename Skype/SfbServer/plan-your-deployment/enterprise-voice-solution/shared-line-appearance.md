---
title: 비즈니스용 Skype 서버 2015의 공유 라인 모양 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 이 항목을 통해 비즈니스용 Skype 서버 2015, 2015년 11월 누적 업데이트에서 SLA(공유 라인 모양)를 계획하는 방법을 배워보는 방법을 읽어보아야 합니다.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813348"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="71173-103">비즈니스용 Skype 서버 2015의 공유 라인 모양 계획</span><span class="sxs-lookup"><span data-stu-id="71173-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="71173-104">이 항목을 통해 비즈니스용 Skype 서버 2015, 2015년 11월 누적 업데이트에서 SLA(공유 라인 모양)를 계획하는 방법을 배워보는 방법을 읽어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71173-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="71173-105">공유 라인 모양은 공유 번호라는 특정 번호에서 여러 통화를 처리하기 위한 비즈니스용 Skype의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="71173-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="71173-106">SLA는 엔터프라이즈 음성을 사용하는 비즈니스용 Skype 사용자를 여러 줄이 있는 공유 번호로 구성하여 여러 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="71173-107">통화는 실제로 공유 번호로 수신되지 않고 공유 번호의 대리인 역할을 하는 사용자에게 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="71173-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="71173-108">대리인 중 한 명은 전화를 받을 수 있으며 나머지 대리인은 전화를 수신한 사용자와 그 결과로 통화 중이 되는 줄에 대한 알림을 휴대폰에서 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="71173-109">줄 수와 대리자는 모두 SLA의 공유 번호에 대해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="71173-110">또한 BusyOption(모든 줄이 통화 중일 때 발생하는 상황) 및 MissedCallOption(대리인이 통화를 선택하지 않은 경우)과 같은 고급 옵션도 공유 번호에 대해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="71173-111">SLA는 다음 휴대폰 디바이스에서만 지원됩니다(컴퓨터, 휴대폰 또는 기타 장치의 비즈니스용 Skype 클라이언트에는 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="71173-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="71173-112">펌웨어 업데이트 5.4.1이 있는 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="71173-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="71173-113">펌웨어 업데이트 5.4.1이 있는 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="71173-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="71173-114">펌웨어 업데이트 5.4.1이 있는 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="71173-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="71173-115">펌웨어 업데이트 5.4.1이 있는 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="71173-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="71173-116">SLA는 2015년 11월 누적 업데이트인 비즈니스용 Skype 서버의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="71173-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="71173-117">SLA 배포에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서 공유](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)라인 모양 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71173-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="71173-118">기능 목록</span><span class="sxs-lookup"><span data-stu-id="71173-118">Feature List</span></span>

<span data-ttu-id="71173-119">SLA 그룹을 설정하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="71173-120">그룹의 모든 대리인이 동일한 공유 번호로의 인바운드 호출에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="71173-121">통화는 PSTN 기반 또는 SIP 기반 통화일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="71173-122">대리인은 통화를 보류하고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="71173-123">대리인은 SLA 그룹 외부의 번호로 통화를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="71173-124">대리인은 현재 공유 번호에 있는 통화 수를 보고 각 통화의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="71173-125">공유 번호에 대한 최대 동시 통화 수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="71173-126">이 최대값에 도달한 후 추가 호출을 처리할 방법을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="71173-127">통화 중 신호로 초과 통화를 거부하거나, 대체 번호로 전달하거나, 음성 메일로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="71173-128">부재 중 전화(특정 시간 후에 선택되지 않은 통화)를 처리할 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71173-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="71173-129">그룹 ID에 대해 음성 메일을 사용하도록 설정하면 부재 중 전화가 자동으로 음성 메일로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="71173-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="71173-130">그룹 ID(공유 번호)에 대해 음성 메일을 사용할 수 없는 경우 통화 중 신호음으로 부재 중 전화가 거부되거나, 대체 번호로 전달되거나, 연결이 끊어지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71173-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

