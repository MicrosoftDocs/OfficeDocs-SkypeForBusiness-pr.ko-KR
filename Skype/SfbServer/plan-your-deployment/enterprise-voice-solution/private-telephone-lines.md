---
title: 비즈니스용 Skype를 통해 전용 전화선 계획
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
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 비즈니스용 Skype 서버의 개인(보조) 전화선 계획 Enterprise Voice.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813598"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="fb09e-103">비즈니스용 Skype를 통해 전용 전화선 계획</span><span class="sxs-lookup"><span data-stu-id="fb09e-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="fb09e-104">비즈니스용 Skype 서버의 개인(보조) 전화선 계획 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fb09e-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fb09e-105">비즈니스용 Skype 서버를 사용하면 사용자에게 기본 전화선 외에 두 번째 전용 전화선도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="fb09e-106">전용 전화선은 경영진 및 직접 연결 가능한 등록되지 않은 전화 번호를 원하는 사람에게 할당되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="fb09e-107">전용 전화선은 비즈니스용 Skype 서버 관리 셸로만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="fb09e-108">비즈니스용 Skype 서버 제어판에서는 전용 전화선을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="fb09e-109">전용 전화선은 혼합 배포가 아닌 비즈니스용 Skype 서버 배포에서만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="fb09e-110">전용 전화선의 특성</span><span class="sxs-lookup"><span data-stu-id="fb09e-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="fb09e-111">제2 전용 전화선의 개념은 기본적으로 간단하지만 전용선의 특징과 사용자의 기본 전화선과 어떻게 유사하고 어떻게 다른지 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="fb09e-112">전용 전화선의 일반 특성</span><span class="sxs-lookup"><span data-stu-id="fb09e-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="fb09e-113">사용자 한 명이 하나의 전용 전화선만 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="fb09e-114">전용 전화선을 사용하는 사용자는 하나의 음성 사서함만 유지하며 단일 전자 메일 주소로 부재 중 통화 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="fb09e-115">전용 전화선을 사용하는 사용자에게는 보조 SIP 주소가 없으며, 보조 전용 전화선은 사용자에게 네트워크의 두 번째 현재 상태(예: 두 번째 인스턴트 메시징 ID)를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="fb09e-116">전용 전화선은 온-프레미스 배포에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="fb09e-117">비즈니스용 Skype 서버의 호스팅된 배포에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="fb09e-118">전용 전화선이 기본 전화선과 다른 점</span><span class="sxs-lookup"><span data-stu-id="fb09e-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="fb09e-119">전용 전화선의 전화 번호는 전화 디렉터리 또는 Active Directory 도메인 서비스에서 파생된 연락처 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="fb09e-120">전용 전화선에는 통화 전달, 팀 통화, 위임, 팀 링, 그룹 통화 Pickup 및 응답 그룹 응용 프로그램과 같은 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="fb09e-121">전용 전화선 통화에는 특별한 벨소리가 지정되며, 시스템 알림에서 사용자에게 전용 회선으로 수신 전화가 걸려 왔음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="fb09e-p104">전용 전화선 통화는 항상 벨이 울리며, "방해 금지" 규칙을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="fb09e-124">전용 전화선은 인바운드 전용이며, 발신 전화를 거는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="fb09e-125">전용 전화선이 있는 사용자가 전화를 걸면 통화가 사용자의 기본 전화선에서 시작된 것이고 사용자의 이름이나 사용자의 기본 전화 번호가 전화를 거는 사람을 숨기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="fb09e-126">전용 전화선이 기본 전화선과 유사한 점</span><span class="sxs-lookup"><span data-stu-id="fb09e-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="fb09e-127">응답하지 않은 전용 전화선 통화는 기본 전화선과 동일한 음성 메일 사서함으로 라우팅됩니다(음성 메일을 사용하도록 설정한 경우).</span><span class="sxs-lookup"><span data-stu-id="fb09e-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="fb09e-128">통화 파크 및 통화 선택은 사용자의 기본 전화선과 동일한 방식으로 전용 전화선에서 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="fb09e-129">사용자의 기본 전화선에서 동시 전화 울림을 사용하도록 설정하면 전용 전화선에서도 동시 벨 울림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="fb09e-130">전용 전화선의 전화 번호는 사용자의 기본 전화선에 대한 전화 번호와 같은 방식으로 통화 정보 레코드에 기록되지만 전용 전화 번호로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="fb09e-131">사용자가 전용 전화선 통화에 응답하면 해당 통화는 사용자의 기본 전화선 통화와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="fb09e-132">예를 들어 전용 전화선으로 전화를 받은 사용자가 통화를 전달하거나 다른 사용자를 전화 회의에 초대하면 사용자의 이름이 비즈니스용 Skype에 표시될 수 있으며 사용자의 기본 전화선의 전화 번호는 발신자 번호에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="fb09e-133">사용자는 기본 전화선과 같은 방식으로 전용 전화선에서 통화를 돌릴 수(응답하기 전에 휴대폰이나 집 전화와 같은 다른 대상으로 통화 리디렉션) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fb09e-134">전용선 통화가 대체 전화 번호로 라우팅된 경우에는 전용 전화선의 전화 번호를 대체 전화 번호로 사용할 수 있으며 이 번호에 대한 로그에 전용 전화선의 전화 번호가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="fb09e-135">전화 회의에서 전용 전화선으로 걸려오는 전화에는 수신 시스템 알림에 전용 회선이 표시되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="fb09e-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="fb09e-136">전용 전화선 관리</span><span class="sxs-lookup"><span data-stu-id="fb09e-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="fb09e-p107">전용 전화선을 만들고 관리하는 기술적인 측면 외에 설정해야 하는 관리 절차가 있습니다. 여기에는 조직에서 전용선을 사용할 수 있는 자격이 있는 사람에 대한 정책 결정, 사용자 및 이들의 전화선 목록 작성 및 유지 관리, 경영진에 대한 전용 전화 디렉터리 작성, 사용자 교육 계획 및 관련 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb09e-p108">전용 전화선은 사용자 개체에 대한 msRTCSIP-PrivateLine 특성으로 Active Directory에 저장됩니다. 기본적으로 Authenticated Users 그룹의 모든 구성원은 이 특성에 대한 읽기 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="fb09e-141">전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="fb09e-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="fb09e-142">전용 전화선이 필요한 새 사용자의 계정은 전용 전화선이 없는 계정과 동일한 방식으로 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="fb09e-143">비즈니스용 Skype 서버 관리 셸에서 **Set-CsUser** cmdlet을 사용하여 사용자의 전용 전화선에 전화 번호를 할당합니다(예: **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**).</span><span class="sxs-lookup"><span data-stu-id="fb09e-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="fb09e-144">전용 전화선의 전화 번호는 3에서 15 사이의 숫자일 수 있으며 앞에 "TEL:" 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="fb09e-145">또한 지역 코드 및 국가/지역 코드가 지정될 수 있습니다(조직에 해당 지역 코드 및 국가/지역 코드에 대한 DID(Direct Inward Dialing)가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="fb09e-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="fb09e-146">cmdlet 및 비즈니스용 Skype 서버 관리 셸에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb09e-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="fb09e-147">혼합 배포에서의 전용 전화선</span><span class="sxs-lookup"><span data-stu-id="fb09e-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="fb09e-148">전용 전화선은 비즈니스용 Skype 서버 또는 Lync Server 2013 배포에만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="fb09e-149">이전 버전의 Lync Server를 실행하는 서버가 있는 배포에서 이전 버전의 사용자가 전용 전화선 통화를 시도하면 서버가 전용 전화선에서 역방향 전화 번호를 찾을 수 없는 경우 통화 라우팅이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fb09e-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

