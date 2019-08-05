---
title: 비즈니스용 Skype 서버의 약속 있음/없음 옵션 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 비즈니스용 Skype 서버의 약속 있음/없음 옵션 기능을 참조 하세요.
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187791"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="292cf-103">비즈니스용 Skype 서버의 약속 있음/없음 옵션 계획</span><span class="sxs-lookup"><span data-stu-id="292cf-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="292cf-104">비즈니스용 Skype 서버의 약속 있음/없음 옵션 기능을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="292cf-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="292cf-105">약속 있음 옵션은 사용자가 이미 통화 또는 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 7 월 2016 누적 업데이트에 도입 된 새로운 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="292cf-106">약속 있음/없음 신호를 사용 하 여 신규 또는 수신 전화를 거부 하거나 음성 메일로 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="292cf-107">사용 중 옵션 정책은 쌍으로 된 프론트 엔드 풀 및 SBS (Survivable Branch Server)에서 장애 조치 및 재해 복구용으로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="292cf-108">이 항목에서는 약속 있음 옵션의 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="292cf-109">약속 있음/없음 옵션을 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 약속 있음 옵션 설치 및 구성을](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="292cf-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="292cf-110">구성 옵션</span><span class="sxs-lookup"><span data-stu-id="292cf-110">Configuration options</span></span>

<span data-ttu-id="292cf-111">조직에 대 한 약속 있음 옵션을 사용 하는 경우 엔터프라이즈 음성과 비 엔터프라이즈 음성 사용자 모두 조직의 모든 사용자가 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="292cf-112">다른 용무 중입니다-사용자가 통화 중인 경우 새로운 수신 통화가 통화 중 이라는 신호를 사용 하 여 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="292cf-113">사용자가 바쁜 경우 새로운 수신 통화가 음성 메일로 착신 전환 되는 동안 보이스 메일을 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="292cf-114">다른 용무 중 옵션 기능은 장애 조치 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="292cf-115">문제가 발생 하 여 사용자가 다른 프런트 엔드 서버 또는 비즈니스용 Skype Server의 다른 풀로 장애 조치 하면 해당 통화 중 옵션 설정이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="292cf-116">약속 있음/없음 옵션이 구성 되는 방식에 관계 없이, 통화 또는 컨퍼런스 사용자 또는 통화 중 통화가 포함 된 경우에는 새 통화 또는 회의가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="292cf-117">구성 후에는 다른 용무 중 옵션 설정이 모든 사용자의 비즈니스용 Skype 통화 장치 및 클라이언트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="292cf-118">사용자의 사용 중 옵션 설정에 따라 음성 메일로 거부 하거나 보내는 통화는 Macintosh, Windows 데스크톱, 모바일 클라이언트 또는 사용자가 로그인 한 IP 전화기를 포함 하 여 사용자의 통화 장치에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="292cf-119">사용자는 비즈니스용 Skype 클라이언트 및 장치에서 부재 중 통화 알림을 볼 수 있으며, 전자 메일로도 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="292cf-120">사용량이 많은 사용자가 통화를 거부 한 호출자는 비즈니스용 Skype 클라이언트에서 다른 통화에 참가 하려고 시도 하 고 있음을 알리는 알림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="292cf-121">비즈니스용 Skype PowerShell cmdlet을 사용 하 여 다음을 수행 하 여 사용 중 옵션 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="292cf-122">엔터프라이즈에 대 한 약속 있음/없음 옵션 사용 또는 사용 안 함 음성 정책</span><span class="sxs-lookup"><span data-stu-id="292cf-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="292cf-123">엔터프라이즈의 모든 사용자가 바쁜 중이거나 보이스 메일을 사용 중인 경우</span><span class="sxs-lookup"><span data-stu-id="292cf-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="292cf-124">특정 프런트 엔드 풀에 속한 모든 사용자의 약속 있음 또는 보이스 메일을 사용 중인 동안 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="292cf-125">사용자 목록에 대 한 약속 있음 또는 보이스 메일을 사용 중인 경우를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="292cf-126">단일 사용자의 약속 있음 또는 보이스 메일을 사용 중인 경우를 관리 하세요.</span><span class="sxs-lookup"><span data-stu-id="292cf-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="292cf-127">음성 응용 프로그램과의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="292cf-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="292cf-128">약속 있음 옵션은 비즈니스용 Skype에서 다음 음성 응용 프로그램과의 상호 운용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="292cf-129">응답 그룹 (RGS)</span><span class="sxs-lookup"><span data-stu-id="292cf-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="292cf-130">응답 그룹 번호에 설정 된 약속 있음 옵션은 시스템에서 무시 됩니다. 동시에 여러 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="292cf-131">응답 그룹의 현재 수행자 라우팅 환경은 약속 있음/없음 옵션 설정을 사용 하는 에이전트에 대해 변경 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="292cf-132">응답 그룹 에이전트를 사용 하는 사용자에 게 응답 그룹에서 전달 되는 통화는 바쁜 옵션 설정으로 제한 되지 않으며 현재 RGS 환경이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="292cf-133">에이전트에 대 한 비 RGS 관련 호출은 사용 중 옵션 설정에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="292cf-134">팀 통화</span><span class="sxs-lookup"><span data-stu-id="292cf-134">Team Call</span></span>
    
  - <span data-ttu-id="292cf-135">팀 전화를 위해 설정 된 사용자에 게 들어오는 통화는 약속 있음/없음 설정에 대해 현재 상태를 무시 하 고 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="292cf-136">현재 팀 통화 환경은 사용자에 대해 설정 된 약속 있음 옵션과 변경 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="292cf-137">이러한 사용자에 대 한 비 팀 통화 관련 통화는 다른 용무 중 옵션 설정으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="292cf-138">상사/관리자 위임</span><span class="sxs-lookup"><span data-stu-id="292cf-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="292cf-139">상사 또는 관리자의 대리인에 대해 사용자에 게 수신 되는 통화는 다른 용무 중 및 다른 용무 중 설정 상태에서 현재 상태를 무시 하 고 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="292cf-140">현재 상사/관리 위임 환경은 관리자 또는 상사에 대해 설정 된 약속 있음/없음 옵션으로 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="292cf-141">관리자에 게 비 상사가 나 관리 대리인 관련 통화는 다른 용무 중 옵션 설정으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="292cf-142">공유 선 모양</span><span class="sxs-lookup"><span data-stu-id="292cf-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="292cf-143">공유 라인에 대해 설정 된 사용자 계정에 대 한 약속 있음 옵션 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="292cf-144">공유 선 모양새의 기본 사용 중이 고 음성 메일 사용 중 옵션이 대신 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="292cf-145">통화 주차 서비스</span><span class="sxs-lookup"><span data-stu-id="292cf-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="292cf-146">검색 되지 않고 시간 초과로 인해 다시 연결 되는 파킹 된 통화는 다른 용무 중 옵션을 사용 하 여 통화를 파킹 한 사용자에 게 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="292cf-147">전화 회의</span><span class="sxs-lookup"><span data-stu-id="292cf-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="292cf-148">컨퍼런스 통화의 사용자는 바쁜 것으로 간주 되며 새로운 수신 전화는 통화 중 신호를 사용 하 여 거부 되거나 통화 중 옵션 설정에 따라 음성 메일로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="292cf-149">회의 중인 사용자는 통화 중 옵션으로 새 통화 또는 회의를 시작 하는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="292cf-150">회의 사용자는 계속 해 서 새 회의 초대를 받을 수 있지만, 새로운 피어 투 피어 통화는 통화 중 옵션 설정에 따라 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="292cf-151">동시 연결 및 착신 전환</span><span class="sxs-lookup"><span data-stu-id="292cf-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="292cf-152">약속 있음/없음 기능은 동시 연결 및 착신 전환 기능과 작동 하도록 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="292cf-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

