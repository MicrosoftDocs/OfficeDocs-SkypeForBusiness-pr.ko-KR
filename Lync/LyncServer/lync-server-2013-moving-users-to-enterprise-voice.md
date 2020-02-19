---
title: 'Lync Server 2013: Enterprise Voice로 사용자 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 968e70e74cd129f05d4f39f626d9e21b1c3dc33a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="fa66f-102">Lync Server 2013에서 Enterprise Voice로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="fa66f-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa66f-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fa66f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fa66f-104">기존 PBX 전화 통신 인프라에서 Enterprise Voice로 사용자를 이동 하는 경우 배포 프로세스에 [Lync Server 2013의 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md)에서 이미 설명한 계획 프로세스의 일부가 아닌 몇 가지 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="fa66f-105">이전 Enterprise Voice 배포에서 사용자를 마이그레이션하는 방법에 대한 자세한 내용은 설치 미디어에 포함된 마이그레이션 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa66f-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="fa66f-106">사용자를 기존 전화 통신 인프라에서 Enterprise Voice로 이동하는 프로세스는 다음 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="fa66f-107">기본 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="fa66f-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="fa66f-108">사용자가 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="fa66f-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="fa66f-109">사용자에 대한 다이얼 플랜 준비</span><span class="sxs-lookup"><span data-stu-id="fa66f-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="fa66f-110">사용자 음성 정책 계획</span><span class="sxs-lookup"><span data-stu-id="fa66f-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="fa66f-111">통화 경로 계획</span><span class="sxs-lookup"><span data-stu-id="fa66f-111">Plan call routes.</span></span>

6.  <span data-ttu-id="fa66f-112">Enterprise Voice를 사용할 수 있는 사용자에 대한 통화를 다시 라우팅하도록 PBX 또는 SIP 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="fa66f-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="fa66f-113">사용자를 Exchange UM (통합 메시징)으로 이동 합니다 (권장).</span><span class="sxs-lookup"><span data-stu-id="fa66f-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="fa66f-114">이 항목에서는 각 단계에 필요한 계획에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="fa66f-p102">1단계. 기본 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="fa66f-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="fa66f-p103">Enterprise Voice는 음성을 다른 메시징 미디어와 통합하며, 걸려오는 전화가 서버에 도착하면 서버에서 번호를 사용자의 SIP-URI에 매핑한 다음 통화를 해당 SIP-URI에 연결된 모든 클라이언트 끝점으로 분기합니다. 이 프로세스에서는 각 사용자가 기본 전화 번호와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="fa66f-119">기본 전화 번호는 다음 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="fa66f-120">전역적으로 고유하거나 내부 내선 번호의 경우 엔터프라이즈 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="fa66f-p104">엔터프라이즈에서 소유하고 라우팅할 수 있어야 합니다. 개인 번호는 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="fa66f-123">엔터프라이즈 사용자는 Active Directory 도메인 서비스에서 두 개 이상의 전화 번호를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="fa66f-124">특정 사용자와 연결된 모든 전화 번호는 Active Directory 사용자 및 컴퓨터 스냅인의 해당 사용자에 대한 속성 시트에서 보거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="fa66f-p106">**사용자 속성** 대화 상자의 **일반** 탭에 있는 **전화 번호** 상자에는 사용자의 기본 회사 전화 번호가 포함되어야 합니다. 일반적으로 이 번호가 사용자의 기본 전화 번호로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="fa66f-127">일부 사용자에게 특별한 요구 사항이 있을 수도 있지만(예: 걸려오는 모든 전화가 비서를 통해 라우팅되기를 원하는 중역) 이러한 예외는 요구가 분명하고 중요한 경우로만 제한되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="fa66f-128">기본 전화 번호를 선택한 후 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="fa66f-129">가능한 경우 기본 전화 번호를 E.164 형식으로 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="fa66f-130">기본 전화 번호를 Active Directory **msRTCSIP-line** 특성에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa66f-131"><STRONG>RCC(원격 통화 제어)와 동시 사용</STRONG></span><span class="sxs-lookup"><span data-stu-id="fa66f-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="fa66f-132">RCC는 Lync Server를 사용 하 여 데스크톱 PBX 전화를 모니터링 하 고 제어 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="fa66f-133">제어는 PBX에 대한 게이트웨이 역할을 하는 서버를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="fa66f-134">사용자가 RCC 및 Enterprise Voice 둘 다를 사용할 수 있도록 구성할 수 없지만 줄 URI 설정은 어느 경우든 사용자의 기본 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="fa66f-135">선택한 사용자가 기존 PBX 인프라를 계속 사용하도록 하려면 조직에 단계적으로 Enterprise Voice를 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="fa66f-136">이 배포 시나리오에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013에서 DIRECT SIP 배포 옵션</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa66f-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="fa66f-137">이전 릴리스에서는 사용자에 대해 RCC 및 Enterprise Voice를 모두 사용 하도록 설정할 수 있지만 이중 포크를 위해 사용자를 구성한 경우에만 들어오는 호출이 사용자의 PBX 전화 및 Communicator에 연결 되는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="fa66f-138">Lync Server 2010에서는 이중 포크는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="fa66f-139">**msRTCSIP-line** 특성을 채우는 세 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="fa66f-140">Microsoft Identity Integration Server(권장)</span><span class="sxs-lookup"><span data-stu-id="fa66f-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="fa66f-141">Lync Server 제어판의 **사용자** 페이지</span><span class="sxs-lookup"><span data-stu-id="fa66f-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="fa66f-142">다양 한 전화 번호를 처리 해야 하는 경우 조직에서 개발한 스크립트 사용자 지정이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="fa66f-143">조직이 AD DS(Active Directory 도메인 서비스)에 전화 번호를 표시하는 조직의 방식에 따라 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성으로 복사하기 전에 E.164 형식으로 정규화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fa66f-144">조직이 AD DS(Active Directory 도메인 서비스)에서 모든 전화 번호를 단일 형식으로 유지 관리하고 해당 형식이 E.164이면 스크립트에서는 각 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fa66f-145">반면 조직이 AD DS(Active Directory 도메인 서비스)에서 모든 전화 번호를 단일 형식으로 유지 관리하지만 해당 형식이 E.164가 아니면 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기 전에 기존 형식에서 E.164로 변환하는 정규화 규칙을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fa66f-146">조직이 AD DS(Active Directory 도메인 서비스)에서 전화 번호에 대해 표준 형식을 적용하지 않는 경우 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기 전에 다양한 형식의 기본 전화 번호를 E.164 준수로 변환하는 적합한 정규화 규칙을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="fa66f-147">또한 스크립트에서 접두사 **Tel:** 을 **msRTCSIP-line** 특성에 각 기본 전화 번호를 쓰기 전에 기본 전화 번호 앞에 삽입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="fa66f-148">이 특성에 지정된 번호의 예상 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="fa66f-149">Tel: + 14255550100으로; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="fa66f-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="fa66f-150">Tel:5550100(엔터프라이즈 전체의 고유 내선)</span><span class="sxs-lookup"><span data-stu-id="fa66f-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fa66f-151">ABS에서는 Active Directory 도메인 서비스에 액세스할 수 없어 기본 전화 번호를 <STRONG>msRTCSIP-line</STRONG> 특성에 복사할 수 없으므로 ABS(주소록 서비스)에서 정규화를 수행하는 경우에도 Active Directory 도메인 서비스에 있는 각 사용자의 기본 전화 번호를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="fa66f-p111">2단계. 사용자가 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="fa66f-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="fa66f-154">사용할 수 있도록 설정할 사용자를 식별하기만 하면 이 단계를 완료하는 데 다른 특별한 계획은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="fa66f-p112">3단계. 사용자에 대해 다이얼 플랜 준비</span><span class="sxs-lookup"><span data-stu-id="fa66f-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="fa66f-p113">Enterprise Voice를 사용할 수 있도록 설정된 사용자는 적절한 다이얼 플랜이 있어야 PSTN에 전화를 걸 수 있습니다. 다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다. 정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="fa66f-160">다이얼 플랜을 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa66f-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="fa66f-161">4단계.</span><span class="sxs-lookup"><span data-stu-id="fa66f-161">Step 4.</span></span> <span data-ttu-id="fa66f-162">사용자 음성 정책 계획</span><span class="sxs-lookup"><span data-stu-id="fa66f-162">Plan user voice policies</span></span>

<span data-ttu-id="fa66f-163">회사 전화에서 장거리 또는 국제 전화를 걸 수 있는 권한 등 기존 PBX에 대한 사용자의 서비스 클래스 설정은 사용자에 대한 VoIP 정책이 Enterprise Voice로 이동함에 따라 다시 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="fa66f-164">Enterprise Voice에 대 한 정책 계획 및 만들기에 대 한 자세한 내용은 [Lync Server 2013의 음성 정책을](lync-server-2013-voice-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa66f-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="fa66f-165">5단계.</span><span class="sxs-lookup"><span data-stu-id="fa66f-165">Step 5.</span></span> <span data-ttu-id="fa66f-166">아웃바운드 통화 경로 계획</span><span class="sxs-lookup"><span data-stu-id="fa66f-166">Plan outbound call routes</span></span>

<span data-ttu-id="fa66f-167">Call 경로 Lync Server가 Enterprise Voice 사용자가 설정한 아웃 바운드 호출을 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="fa66f-168">사용자가 전화를 걸면 서버는 필요한 경우 전화 걸기 문자열을 E.164 형식으로 정규화하고 SIP URI에 일치시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="fa66f-169">일치시킬 수 없는 경우 서버는 해당 번호에 기초하여 아웃바운드 통화 라우팅 논리를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="fa66f-170">해당 논리를 정의하는 마지막 단계는 각 다이얼 플랜에 나열된 각 대상 전화 번호 집합에 대한 별도의 명명된 통화 경로를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="fa66f-171">통화 경로를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa66f-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="fa66f-172">6단계.</span><span class="sxs-lookup"><span data-stu-id="fa66f-172">Step 6.</span></span> <span data-ttu-id="fa66f-173">Enterprise Voice 사용자에 대한 통화를 다시 라우팅하도록 PBX 또는 SIP 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="fa66f-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="fa66f-174">ITSP(인터넷 전화 통신 서비스 공급자)에 연결된 일반 PBX 또는 SIP 트렁크 연결에서 이전에 호스팅된 사용자는 이동 후에도 전화 번호가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="fa66f-175">이러한 요구 사항은 이동 후에도 기업 음성 사용자에 대 한 수신 전화를 중재 서버로 라우팅하기 위해 PBX 또는 SIP 트렁크를 다시 구성 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="fa66f-p120">7단계. Exchange 통합 메시징으로 사용자 이동(권장)</span><span class="sxs-lookup"><span data-stu-id="fa66f-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="fa66f-178">사용자를 Exchange 통합 메시징으로 이동하는 과정은 다음 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="fa66f-179">Exchange 통합 메시징과 Lync Server가 함께 작동 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="fa66f-180">사용자가 Exchange 통합 메시징 통화 응답 및 Outlook Voice Access를 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="fa66f-181">이 작업은 Exchange 통합 메시징 서버에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa66f-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="fa66f-182">자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 TechNet 라이브러리를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa66f-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

