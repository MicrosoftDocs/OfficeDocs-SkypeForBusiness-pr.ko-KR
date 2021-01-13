---
title: 비즈니스용 Skype 서버에 대한 사용 중 옵션 계획
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 비즈니스용 Skype 서버의 다른 업무용 옵션 기능에 대해 읽어 보십시오.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813698"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="f8a39-103">비즈니스용 Skype 서버에 대한 사용 중 옵션 계획</span><span class="sxs-lookup"><span data-stu-id="f8a39-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="f8a39-104">비즈니스용 Skype 서버의 다른 업무용 옵션 기능에 대해 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="f8a39-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="f8a39-105">다른 사용자가 이미 통화 또는 회의에 참석 중이거나 통화를 보류 중일 때 수신 전화가 처리되는 방법을 구성할 수 있도록 2016년 7월 누적 업데이트에 도입된 새로운 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="f8a39-106">새 전화나 수신 전화는 통화 중 신호로 거부되거나 음성 메일로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="f8a39-107">사용 중 옵션 정책은 페어링된 프런트 엔드 풀 및 SBS(Survivable Branch Server)에서 장애 조치 및 재해 복구에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="f8a39-108">이 항목에서는 다른 사용 중 옵션의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="f8a39-109">다른용 Skype 옵션을 설치 및 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버의 다른용 옵션 설치 및 [구성을 참조하세요.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="f8a39-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="f8a39-110">구성 옵션</span><span class="sxs-lookup"><span data-stu-id="f8a39-110">Configuration options</span></span>

<span data-ttu-id="f8a39-111">조직에서 다른 사용자 옵션을 사용하도록 설정한 경우 조직의 모든 사용자가 Enterprise Voice 사용자와 비영구 Enterprise Voice 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="f8a39-112">다른 사용자의 통화 중 - 사용자가 통화 중일 때 통화 중 신호로 새 수신 전화가 거부되는 경우</span><span class="sxs-lookup"><span data-stu-id="f8a39-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="f8a39-113">통화 중 음성 메일 - 사용자가 통화 중일 때 새 수신 전화가 음성 메일로 전달되는 경우</span><span class="sxs-lookup"><span data-stu-id="f8a39-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="f8a39-114">다른용 옵션 기능은 장애 조치(failover) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="f8a39-115">문제가 발생하여 사용자가 비즈니스용 Skype 서버의 다른 프런트 엔드 서버 또는 다른 풀로 장애 조치(fail over)되면 해당 사용 중 옵션 설정이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="f8a39-116">통화 중 옵션의 구성 방식에 관계없이 통화 또는 회의의 사용자 또는 통화가 보류된 사용자는 새 통화나 회의를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="f8a39-117">구성 후 모든 사용자의 비즈니스용 Skype 통화 장치 및 클라이언트에 대해 통화 중 옵션 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="f8a39-118">사용자의 통화 중 옵션 설정에 따라 거부되거나 음성 메일로 전송되는 통화는 사용자가 로그인한 Macintosh, Windows 데스크톱, 모바일 클라이언트 또는 IP 전화를 비롯한 사용자의 통화 장치에서 벨이 울리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="f8a39-119">사용자는 비즈니스용 Skype 클라이언트 및 장치에서 부재 중 전화 알림을 볼 수 있으며 전자 메일로도 알림을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="f8a39-120">다른 통화 중으로 인해 통화가 거부된 발신자는 다른 통화를 시도한 사용자가 다른 통화 중일 때 통화 중이라는 알림을 비즈니스용 Skype 클라이언트에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="f8a39-121">비즈니스용 Skype PowerShell cmdlet을 사용하여 다음을 위해 사용 중 옵션 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="f8a39-122">엔터프라이즈에 대해 다른용 옵션 음성 정책을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f8a39-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="f8a39-123">기업의 모든 사용자에 대해 다른 사용자가 다른용 또는 다른 사용자의 다른 다른 사용자에 대해 다른 사용자의 다른 사용자에 대해 다른 사용자에 대해 다른 사용자의</span><span class="sxs-lookup"><span data-stu-id="f8a39-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="f8a39-124">특정 프런트 엔드 풀에 있는 모든 사용자의 다른 사용자에 대해 다른 사용자가 다른용 또는 다른 사용자의 다른 사용 중일 때 음성메일을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="f8a39-125">사용자 목록에 대해 다른 사용자가 사용 중일 때 또는 다른 사용자가 있는 경우 음성메일을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="f8a39-126">사용자 한 명에 대해 다른 사용자가 다른용 또는 다른 사용자의 다른 사용자에 대해 다른 사용자의 다른 음성사용자 수가 1명인 경우 해당 음성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="f8a39-127">음성 응용 프로그램과의 상호 실행성</span><span class="sxs-lookup"><span data-stu-id="f8a39-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="f8a39-128">사용 중 옵션은 비즈니스용 Skype에서 다음 음성 응용 프로그램과의 상호 연동성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="f8a39-129">응답 그룹(RGS)</span><span class="sxs-lookup"><span data-stu-id="f8a39-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="f8a39-130">응답 그룹 번호에 설정된 다른 사용 중 옵션은 시스템에서 무시됩니다. 여러 개의 동시 통화가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="f8a39-131">응답 그룹의 현재 Attendant 라우팅 환경은 사용 중인 옵션 설정이 있는 에이전트에 대해 변경되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="f8a39-132">응답 그룹에서 응답 그룹 에이전트인 사용자에게 걸려오는 호출은 다른 통화 옵션 설정에 의해 스로틀되지 않습니다. 현재 RGS 환경은 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="f8a39-133">RGS가 아닌 에이전트 관련 호출은 다른 통화 중 옵션 설정에 따라 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f8a39-134">Team Call(팀 호출)</span><span class="sxs-lookup"><span data-stu-id="f8a39-134">Team Call</span></span>
    
  - <span data-ttu-id="f8a39-135">팀 통화에 대해 설정된 사용자의 수신 전화에 우선 순위가 지정되어 통화 중에는 다른 사용자가 통화 중일 때를 무시하고 통화 중 설정의 음성 메일은 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f8a39-136">현재 팀 통화 환경은 사용자에 대해 설정된 다른 통화 옵션과 변경되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="f8a39-137">이러한 사용자에 대한 팀이 아닌 통화 관련 통화는 통화 중 옵션 설정에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f8a39-138">관리자/관리자 위임</span><span class="sxs-lookup"><span data-stu-id="f8a39-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="f8a39-139">상사/관리자 위임으로 설정된 사용자에게 걸러오는 수신 전화는 다른 사용자가 통화 중일 때를 무시하고 통화 중 설정에서 음성 메일이 통화 중일 때를 무시하는 우선 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f8a39-140">현재의 상사/관리자 위임 환경은 관리자 또는 상사에 대해 설정된 다른 사용 중 옵션으로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="f8a39-141">관리자에 대한 비사용자/관리자 위임 관련 통화는 다른 통화 옵션 설정에 따라 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f8a39-142">회선 공유 기능</span><span class="sxs-lookup"><span data-stu-id="f8a39-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="f8a39-143">공유 행 모양에 대해 설정된 사용자 계정의 다른 사용 중 옵션 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="f8a39-144">대신에 공유 행 모양의 다른 다른 사용자와 다른 사용자들이 다른 일정에 있는 음성메일 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="f8a39-145">통화 파킹 서비스</span><span class="sxs-lookup"><span data-stu-id="f8a39-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="f8a39-146">검색되지 않은 통화가 있으며 시간 아웃으로 인해 다시 울리는 통화는 다른 통화 옵션에 의해 통화를 저장한 사용자에게는 벨이 울리면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="f8a39-147">통화 회의</span><span class="sxs-lookup"><span data-stu-id="f8a39-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="f8a39-148">회의 통화의 사용자는 통화 중으로 간주하고 새 수신 전화는 다른 통화 중 신호로 거부되거나 통화 중 옵션 설정에 따라 음성 메일로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="f8a39-149">회의의 사용자는 다른 사용자의 통화 중 옵션으로 새 통화나 회의를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="f8a39-150">회의의 사용자는 여전히 새 전화 회의 초대를 받을 수 있지만 다른 피어 투 피어 통화는 다른 사용자의 다른 통화 옵션 설정에 따라 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="f8a39-151">동시 벨 울림 및 전달</span><span class="sxs-lookup"><span data-stu-id="f8a39-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="f8a39-152">다른 작업 중 기능은 동시 벨 울림 및 통화 전달과 함께 작동하도록 설계되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a39-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

