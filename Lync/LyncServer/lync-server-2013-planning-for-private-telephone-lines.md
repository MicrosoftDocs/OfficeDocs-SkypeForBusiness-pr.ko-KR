---
title: 'Lync Server 2013: 전용 전화선 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0369ea671860b29c8cf7f7e1d9e0b894770c6d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="857da-102">Lync Server 2013를 사용 하 여 전용 전화선 계획</span><span class="sxs-lookup"><span data-stu-id="857da-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="857da-103">_**마지막으로 수정 된 항목:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="857da-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="857da-104">Lync Server 2013에는 사용자에 게 기본 전화선과 함께 보조 전용 전화선을 제공 하는 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="857da-105">전용 전화선은 경영진 및 직접 연결 가능한 등록되지 않은 전화 번호를 원하는 사람에게 할당되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="857da-106">전용 전화선은 Lync Server 관리 셸을 사용 해야만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="857da-107">Lync Server 제어판을 사용 하 여 전용 전화선을 구성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="857da-108">전용 전화선은 혼합 배포가 아닌 Lync Server 배포 에서만 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="857da-109">전용 전화선의 특성</span><span class="sxs-lookup"><span data-stu-id="857da-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="857da-110">보조 전용 전화선의 개념은 기본적으로 단순하지만 전용 회선의 특성이 무엇인지, 그리고 전용 회선이 사용자의 기본 전화선과 어떤 점에서 유사하고 어떤 점에서 다른지를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="857da-111">전용 전화선의 일반 특성</span><span class="sxs-lookup"><span data-stu-id="857da-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="857da-112">사용자 한 명이 하나의 전용 전화선만 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="857da-113">전용 전화선을 사용하는 사용자는 하나의 음성 사서함만 유지하며 단일 전자 메일 주소로 부재 중 통화 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="857da-114">전용 전화선을 사용하는 사용자에게는 보조 SIP 주소가 없으며, 보조 전용 전화선은 사용자에게 네트워크의 두 번째 현재 상태(예: 두 번째 인스턴트 메시징 ID)를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="857da-115">전용 전화선은 온-프레미스 배포에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="857da-116">호스팅된 Lync Server 배포에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="857da-117">전용 전화선이 기본 전화선과 다른 점</span><span class="sxs-lookup"><span data-stu-id="857da-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="857da-118">전용 전화선의 전화 번호는 전화 디렉터리 또는 Active Directory 도메인 서비스에서 파생된 연락처 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="857da-119">전용 전화선에서는 착신 전환, 팀 호출, 위임, 팀 전화 걸기, 그룹 통화 픽업 및 응답 그룹 응용 프로그램과 같은 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="857da-120">전용 전화선 통화에는 특별한 벨소리가 지정되며, 시스템 알림에서 사용자에게 전용 회선으로 수신 전화가 걸려 왔음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="857da-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="857da-p104">전용 전화선 통화는 항상 벨이 울리며, "방해 금지" 규칙을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="857da-p105">전용 전화선은 인바운드 전용이며, 발신 전화를 거는 데 사용할 수 없습니다. 전용 전화선이 있는 사용자가 전화를 걸면 사용자의 기본 전화선을 통해 발신되므로 사용자 이름 또는 사용자의 기본 전화 번호가 상대방에게 숨겨지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="857da-125">전용 전화선이 기본 전화선과 유사한 점</span><span class="sxs-lookup"><span data-stu-id="857da-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="857da-126">응답하지 않은 전용 전화선 통화는 기본 전화선과 동일한 음성 메일 사서함으로 라우팅됩니다(음성 메일을 사용하도록 설정한 경우).</span><span class="sxs-lookup"><span data-stu-id="857da-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="857da-127">전용 전화선의 통화 대기 및 통화 수신은 사용자의 기본 전화선과 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="857da-128">사용자의 기본 전화선에 동시 전화 신호 울림이 설정된 경우 전용 전화선에도 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="857da-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="857da-129">전용 전화선의 전화 번호는 기본 전화선의 전화 번호와 동일한 방식으로 통화 기록 정보에 기록되지만 전용 전화 번호가 표시가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="857da-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="857da-130">사용자가 전용 전화선 통화에 응답하면 이 통화는 사용자의 기본 전화선 통화와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="857da-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="857da-131">예를 들어 전용 전화선에서 통화를 수신 하는 사용자가 통화를 전달 하거나 다른 사람을 전화 회의에 초대 하는 경우 사용자 이름이 Lync 2013에 표시 되 고 사용자의 기본 전화선에 대 한 전화 번호가 발신자 번호에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="857da-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="857da-132">사용자는 기본 전화선과 같은 방식으로 전용 전화선에서 통화를 돌릴 수(응답하기 전에 휴대폰이나 집 전화와 같은 다른 대상으로 통화 리디렉션) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="857da-133">전용선 통화가 대체 전화 번호로 라우팅된 경우에는 전용 전화선의 전화 번호를 대체 전화 번호로 사용할 수 있으며 이 번호에 대한 로그에 전용 전화선의 전화 번호가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="857da-134">전화 회의에서 전용 전화선으로 건 전화는 수신 시스템 알림에 <EM>전용선</EM>이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="857da-135">전용 전화선 관리</span><span class="sxs-lookup"><span data-stu-id="857da-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="857da-p107">전용 전화선을 만들고 관리하는 기술적인 측면 외에 설정해야 하는 관리 절차가 있습니다. 여기에는 조직에서 전용선을 사용할 수 있는 자격이 있는 사람에 대한 정책 결정, 사용자 및 이들의 전화선 목록 작성 및 유지 관리, 경영진에 대한 전용 전화 디렉터리 작성, 사용자 교육 계획 및 관련 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="857da-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="857da-p108">전용 전화선은 사용자 개체에 대한 msRTCSIP-PrivateLine 특성으로 Active Directory에 저장됩니다. 기본적으로 Authenticated Users 그룹의 모든 구성원은 이 특성에 대한 읽기 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="857da-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="857da-140">전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="857da-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="857da-141">전용 전화선이 필요한 새 사용자에 대 한 계정은 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 전용 전화선이 없는 계정과 동일한 방식으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="857da-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="857da-142">Lync Server 관리 셸에서는 **csuser** cmdlet을 사용 하 여 사용자에 대 한 전용 전화선에 전화 번호를 할당 합니다 (예 **: Set-Csuser-Identity "Sip:joe@contoso.com"-PrivateLine "Tel = + 14255551212")**.</span><span class="sxs-lookup"><span data-stu-id="857da-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="857da-143">전용 전화선의 전화 번호는 3 ~ 15 자 사이 이며 "TEL:" 접두사 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="857da-144">또한 지역 코드 및 국가/지역 코드가 지정될 수 있습니다(조직에 해당 지역 코드 및 국가/지역 코드에 대한 DID(Direct Inward Dialing)가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="857da-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="857da-145">Cmdlet 및 Lync Server 관리 셸에 대 한 자세한 내용은 [Lync server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="857da-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="857da-146">혼합 배포에서의 전용 전화선</span><span class="sxs-lookup"><span data-stu-id="857da-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="857da-147">전용 전화선은 Lync Server 배포에 대해서만 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="857da-148">Lync Server와 Office communications server 2007 또는 Office Communications Server 2007 R2 서버가 둘 다 있는 배포에서 이전 버전의 사용자가 전용 전화선을 호출 하려고 하면 서버에서 전화를 거는 동안 오류가 발생 하 여 연결이 실패 합니다. 전용 전화선에서 역방향 번호 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="857da-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

