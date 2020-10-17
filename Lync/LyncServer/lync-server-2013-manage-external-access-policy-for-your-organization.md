---
title: 'Lync Server 2013: 조직에 대 한 외부 액세스 정책 관리'
description: 'Lync Server 2013: 조직에 대 한 외부 액세스 정책을 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f0bb0e6764f67403065187c62debef13c77fcc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558414"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="5a04b-103">Lync Server 2013에서 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5a04b-103">Manage external access policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a04b-104">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5a04b-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5a04b-105">Edge 서버를 하나 이상 배포한 후에는 조직에 대해 지원할 유형의 외부 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-105">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="5a04b-p101">조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 글로벌 정책이 만들어지지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="5a04b-110">**전역 정책**   Edge 서버를 배포할 때 전역 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-110">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="5a04b-111">기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-111">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="5a04b-112">전역 수준의 외부 사용자 액세스를 지원하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원하도록 전역 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-112">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="5a04b-113">전역 정책은 조직의 모든 사용자에게 적용되지만 사이트 정책 및 사용자 정책이 전역 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-113">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="5a04b-114">전역 정책을 삭제하는 경우에는 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-114">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="5a04b-115">대신, 기본 설정으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-115">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="5a04b-116">**사이트 정책**    하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스 지원을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-116">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="5a04b-117">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-117">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="5a04b-118">예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-118">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="5a04b-119">기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-119">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="5a04b-120">**사용자 정책**   하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스 지원을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-120">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="5a04b-121">사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-121">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="5a04b-122">예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-122">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="5a04b-123">사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-123">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a04b-124">한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5a04b-125">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5a04b-126">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="5a04b-127">이러한 옵션에는 다음과 같은 유형의 외부 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-127">These options include the following types of external access:</span></span>

  - <span data-ttu-id="5a04b-128">**페더레이션 사용자와의 통신 사용**   페더레이션 파트너 도메인에 대한 사용자 액세스를 지원하려면 이 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5a04b-128">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="5a04b-129">이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 정보를 교환할 수 있으며 Microsoft 365 같은 호스팅된 공급자도 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-129">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="5a04b-130">이 설정을 선택 하면 XMPP 페더레이션 도메인과의 통신을 허용 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-130">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="5a04b-p107">**페더레이션 사용자와의 통신 사용**을 처음 선택할 경우에는 옵션으로 **XMPP 페더레이션 파트너와의 통신 사용**을 선택할 수 있습니다. XMPP 페더레이션은 XMPP(Extensible Messaging and Presence Protocol)를 사용하는 조직과의 페더레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a04b-133">XMPP 페더레이션을 사용 하도록 설정 하는 경우에는 토폴로지 작성기의에 지 풀 구성 섹션에서 <STRONG>Xmpp 페더레이션</STRONG> 도 배포 하도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-133">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="5a04b-134">XMPP 페더레이션을 구성 하는 경우에는에 지 서버 및 프런트 엔드 서버의 XMPP 게이트웨이에서 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-134">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="5a04b-135">**원격 사용자**     와의 통신 사용 조직의 사용자 (예: 재택 근무자, 출장 중인 사용자)가 인터넷을 통해 Lync Server에 연결할 수 있게 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-135">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="5a04b-136">**공용 사용자**     와의 통신 사용 내부 사용자가 공용 IM 공급자 연락처 (예: Windows Live, Yahoo 및 북미 온라인)에서 제공 하는 대화 상대와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 \! 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-136">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="5a04b-137">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-137">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5a04b-138">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-138">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5a04b-139">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="5a04b-139">Messenger until the service shut down date.</span></span> <span data-ttu-id="5a04b-140">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="5a04b-140">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5a04b-141">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-141">has been announced.</span></span> <span data-ttu-id="5a04b-142">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a04b-142">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5a04b-143">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-143">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5a04b-144">메신저로.</span><span class="sxs-lookup"><span data-stu-id="5a04b-144">Messenger.</span></span> <span data-ttu-id="5a04b-145">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-145">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5a04b-146">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-146">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5a04b-147">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-147">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5a04b-148">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-148">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="5a04b-149">외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 조직에서 외부 사용자 액세스 사용을 제어하는 정책을 구성해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-149">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="5a04b-150">외부 사용자 액세스에 대 한 정책을 만들고 구성 하 고 적용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a04b-150">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5a04b-151">**Windows PowerShell cmdlet을 사용하여 외부 액세스 정책을 보려면**</span><span class="sxs-lookup"><span data-stu-id="5a04b-151">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="5a04b-152">Lync Server 관리 셸 및 **get-csexternalaccesspolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-152">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="5a04b-153">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-153">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5a04b-154">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a04b-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="5a04b-155">모든 외부 액세스 정책에 대한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-155">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="5a04b-156">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a04b-156">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a04b-157">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5a04b-157">In This Section</span></span>

  - [<span data-ttu-id="5a04b-158">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5a04b-158">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="5a04b-159">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5a04b-159">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="5a04b-160">Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5a04b-160">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="5a04b-161">Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5a04b-161">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="5a04b-162">Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5a04b-162">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="5a04b-163">Lync Server 2013에서 외부 사용자 액세스 정책 다시 설정 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="5a04b-163">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

