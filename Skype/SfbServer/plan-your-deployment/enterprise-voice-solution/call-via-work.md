---
title: 비즈니스용 Skype 서버의 작업을 통한 통화 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 비즈니스용 skype 서버와 PBX 전화 시스템 간 통합을 통해 통화 계획을 통해 사용자가 비즈니스용 Skype를 사용 하 여 PBX 전화를 제어할 수 있습니다.
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187758"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="ff29c-103">비즈니스용 Skype 서버의 작업을 통한 통화 계획</span><span class="sxs-lookup"><span data-stu-id="ff29c-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="ff29c-104">비즈니스용 skype 서버와 PBX 전화 시스템 간 통합을 통해 통화 계획을 통해 사용자가 비즈니스용 Skype를 사용 하 여 PBX 전화를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="ff29c-105">**직장** 에서의 통화는 비즈니스용 skype 서버의 새로운 기능으로, Skype for business 솔루션을 기존 PBX 전화 시스템과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="ff29c-106">작업을 통해 통화할 수 있는 사용자는 비즈니스용 Skype를 클릭 하 여 배포 또는 외부 사용자에 게 다른 사용자에 게 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="ff29c-107">사용자의 PBX 전화기를 사용 하 여 통화가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="ff29c-108">이렇게 하면 PBX 전화기를 사용 하는 사용자가 다양 한 비즈니스용 Skype 대화에 오디오를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="ff29c-109">이전 버전의 Lync Server 원격 통화 제어는 Lync Server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 기능 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ff29c-110">비즈니스용 Skype Server에서이 기능은 업무에의 한 통화를 통해 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="ff29c-111">작업을 통해 전화 걸기 PBX 전화 사용자에 게 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="ff29c-112">PBX 전화기를 통해 제공 되는 오디오를 사용 하 여 클릭 하 여 전화를 걸 수 있는 환경</span><span class="sxs-lookup"><span data-stu-id="ff29c-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="ff29c-113">현재 상태, 사용자 검색, IM 통합-예를 들어 IM 세션의 작업 사용자를 통한 두 통화는 PBX 전화기를 통해 제공 되는 오디오를 사용 하 여 해당 세션에 오디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="ff29c-114">회사 전화를 통해 통화에 IM, 응용 프로그램 공유, 파일 전송을 추가 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="ff29c-115">한 번 클릭 모임 참가 권한</span><span class="sxs-lookup"><span data-stu-id="ff29c-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="ff29c-116">작동 방식</span><span class="sxs-lookup"><span data-stu-id="ff29c-116">How it works</span></span>

<span data-ttu-id="ff29c-117">작업을 통한 통화-PBX 시스템과 비즈니스용 Skype Server 배포 간의 B2BUA (통합 커뮤니케이션 웹 API)를 사용 하 여 연결에 컴퓨터에서 지원 되는 텔레커뮤니케이션 응용 프로그램 (CSTA) 게이트웨이가 필요 하지 않도록 합니다. PBX 시스템을 사용 하는 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="ff29c-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="ff29c-118">모바일 및 웹 클라이언트와의 연결을 가능 하 게 하기 위해 이전 버전의 Lync Server에 도입 된 서비스로, 모든 프런트 엔드 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="ff29c-119">회사 전화를 통한 통화 워크플로 호출</span><span class="sxs-lookup"><span data-stu-id="ff29c-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="ff29c-120">다음은 사용자가 회사에서 비즈니스용 Skype Server를 사용 하 여 전화를 걸 수 있도록 하는 방법에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![회사 전화를 통해 통화 중의 단계를 보여줍니다. 먼저 발신자가 비즈니스용 Skype 클라이언트에서 다른 사람에 게 전화를 겁니다. 그런 다음, 휴대 전화를 발신자의 전화기로 울릴 것입니다.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="ff29c-123">사용자가 비즈니스용 Skype 클라이언트에서 사용자를 선택 하 고 휴대폰 아이콘을 클릭 하 여 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="ff29c-124">또는 메신저 대화 중에 세션을 보유 하 고 있는 사용자에 게 전화를 거는 사용자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="ff29c-125">통화를 시작한 사용자의 PBX 전화가 ring으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="ff29c-126">이 휴대폰의 발신자 ID에는 모든 사용자의 발신자 ID에 표시 하도록 설정한 전역 전화 번호가 회사 전화를 통해 전화를 걸어 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="ff29c-127">이 전역 전화 번호는 한 사람의 휴대폰에 해당 하는 실제 전화 번호가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="ff29c-128">대신이 신호는 사용자에 게 자신의 발신 통화가 있고 동시에 수신 통화가 발생 하지 않는다는 것을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="ff29c-129">업무를 통해 전화를 배포 하는 경우이 전역 전화 번호와 의미에 대해 해당 사용자를 교육 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="ff29c-130">통화를 놓은 사용자는 자신의 PBX 전화기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="ff29c-131">그런 다음 비즈니스용 Skype에서 호출 수신자에 대 한 음성 통화를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="ff29c-132">호출 수신자가 응답 하면 음성 통화가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="ff29c-133">두 명의 사용자가 이미 메신저 대화 세션을 진행 하 고 있는 경우 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="ff29c-134">작업을 통한 전화 회의 참가</span><span class="sxs-lookup"><span data-stu-id="ff29c-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="ff29c-135">업무 사용자를 통한 통화는 모임 URL을 클릭 하 여 예약 된 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="ff29c-136">비즈니스용 Skype는 모임 서비스가 사용자의 PBX 휴대폰에 전화를 걸 때까지 메시지 **에 전화를 거** 는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="ff29c-137">회사 사용자를 통해 전화를 걸어 PBX 전화기를 선택 하 고 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="ff29c-138">회사 사용자를 통한 통화는 비즈니스용 Skype의 **모임** 시작 옵션을 사용 하 여 모임 시작 모임을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="ff29c-139">그러면 사용자가 **전화 걸기를** 메시지에 표시 하 고 PBX 전화기를 울릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="ff29c-140">업무 사용자를 통한 통화는 비즈니스용 Skype 내에서 회의 브리지 번호를 호출 하 여 모임에 전화를 걸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="ff29c-141">컨퍼런스 PIN이 필요한 경우 사용자는 PBX 휴대폰을 사용 하 여 PIN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="ff29c-142">걸려오는 전화</span><span class="sxs-lookup"><span data-stu-id="ff29c-142">Incoming Calls</span></span>

<span data-ttu-id="ff29c-143">사용자가 비즈니스용 Skype 통화를 수신 하는 경우, PBX 휴대폰 및 사용자의 비즈니스용 Skype 클라이언트가 동시에 모든 링을 연결 합니다 (사용자가 동시 연결을 설정한 경우).</span><span class="sxs-lookup"><span data-stu-id="ff29c-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="ff29c-144">사용자가 PBX 휴대폰을 선택 하거나 비즈니스용 Skype 알림에서 **수락** 을 클릭 하 여 통화를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="ff29c-145">사용자가 비즈니스용 Skype를 사용 하 여 통화를 수락 하면 통화에 대 한 비즈니스용 Skype 창이 열려 있는 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="ff29c-146">그러나 사용자가 PBX 전화기를 선택 하 여 통화를 수락 하는 경우 비즈니스용 skype 알림 창이 닫히고, 비즈니스용 Skype 세션이 없으며, PBX 전화기를 통한 음성 통화만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="ff29c-147">사용자가 전화로 전화를 걸 수 있도록 설정 된 경우 pbx 전화기만 울릴 겁니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="ff29c-148">작업을 통한 통화의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="ff29c-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="ff29c-149">직장에서의 통화는 하드웨어 설정이 거의 필요 하지 않지만 전체 엔터프라이즈 음성 또는 원격 통화 제어에서 사용할 수 있는 기능과 비교 하 여 제한 사항이 있는 음성 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="ff29c-150">직장을 통한 통화에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="ff29c-151">회사 사용자가 전화를 걸 때 회사 콜백 번호를 통해 통화 착신 전환을 설정 하 고 누군가 사용자의 전화 번호로이 사용자를 모임에 초대 하려고 하면 초대가 사용자에 게 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="ff29c-152">전화 번호가 아닌 이름을 클릭 하 여 참가자를 모임에 초대 하도록 사용자를 교육 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="ff29c-153">향상 된 911 접근 권한 및 악의적인 통화 추적은 작업 호출을 통해 통화 중에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="ff29c-154">작업을 통해 전화를 걸 수 있는 사용자는 위임, 팀 통화 또는 응답 그룹 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="ff29c-155">업무에 대 한 통화 사용자는 비즈니스용 Skype를 사용 하 여 모임을 녹화 하거나, 통화를 음소거 또는 음소거 해제 하거나, 통화를 보류 하거나, 통화 공원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="ff29c-156">사용자는 직장을 통한 통화를 사용 하 여 PBX 보이스 메일 메시지에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="ff29c-157">작업을 통한 통화 사용자는 비디오, Powerpoint, 화이트 보드 또는 한 노트와 같은 통신을 포함 하는 공동 작업 모임에 대 한 음성 통화로 시작 된 세션을 확대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="ff29c-158">작업을 통한 통화 사용자는 2 명 통화에 더 이상 사용자를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="ff29c-159">Deskphone 페어링 또는 VDI 플러그 인 페어링에 대 한 지원이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="ff29c-160">사용자가 PBX 전화기를 사용 하 여 전화를 걸거나 받고 응답 하는 경우 (비즈니스용 Skype 창을 사용 하지 않는 경우)에는 통화 로그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="ff29c-161">PBX 시스템에서 **대체를 참조**하는 것을 지원 하지 않는 경우에는 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="ff29c-162">회사 전화 통화 중에 사용자가 PBX 휴대폰에서 진행 중인 통화를 전송 하는 동안에는 비즈니스용 Skype 창에서 통화 창이 사라지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="ff29c-163">그런 다음 사용자가 호출 창을 닫으면 전송 대상과 transferee 간의 통화가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="ff29c-164">작업을 통한 통화를 위한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="ff29c-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="ff29c-165">작업을 통해 모든 사용자에 게 전화를 걸 수 있도록 설정 하려면 필요에 따라 필수 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="ff29c-166">이러한 전제 조건과 작업을 통한 통화에 사용자를 설정 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 작업 배포](../../deploy/deploy-call-via-work.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff29c-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ff29c-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff29c-167">See also</span></span>

[<span data-ttu-id="ff29c-168">비즈니스용 Skype에서 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="ff29c-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="ff29c-169">비즈니스용 Skype 서버 2015에서 회사번호로 전화 배포</span><span class="sxs-lookup"><span data-stu-id="ff29c-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

