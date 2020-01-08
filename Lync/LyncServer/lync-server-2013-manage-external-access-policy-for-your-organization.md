---
title: 'Lync Server 2013: 조직에 대한 외부 액세스 정책 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="78189-102">Lync Server 2013에서 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="78189-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78189-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="78189-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="78189-104">하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="78189-105">기본적으로 조직에 대해 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 외부 사용자 액세스를 지원 하도록 구성 된 정책은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="78189-106">외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="78189-107">다음 정책 범위를 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="78189-108">기본적으로 전역 정책은 만들어지지만 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="78189-109">**전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="78189-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="78189-110">기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="78189-111">전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="78189-112">전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="78189-113">전역 정책을 삭제 해도 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="78189-114">대신 기본 설정으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="78189-115">**사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="78189-116">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="78189-117">예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="78189-118">기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="78189-119">**사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="78189-120">사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="78189-121">예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="78189-122">사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78189-123">하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="78189-124">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="78189-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="78189-125">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78189-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="78189-126">이러한 옵션에는 다음과 같은 외부 액세스 유형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78189-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="78189-127">**페더레이션 사용자**   와의 통신 사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="78189-128">이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 통신 하는 기능 뿐만 아니라 Microsoft Office 365와 같은 호스트 공급자도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="78189-129">이 설정을 선택 하면 XMPP 페더레이션 도메인과의 통신을 허용 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="78189-130">옵션으로, 먼저 **페더레이션 사용자와 통신 사용**을 선택 하면 **xmpp 페더레이션 파트너와 통신 사용** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="78189-131">XMPP federation는 확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP)을 사용 하는 조직이 있는 페더레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="78189-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78189-132">XMPP 페더레이션을 사용 하는 경우에는 토폴로지 작성기의 Edge 풀 구성 섹션에서 <STRONG>Xmpp 페더레이션</STRONG> 만 배포 하도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="78189-133">XMPP 페더레이션의 구성은 Edge 서버 및 프런트 엔드 서버의 XMPP 게이트웨이에서 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="78189-134">**원격 사용자**   와 통신 설정 방화벽 외부에 있는 사용자 (예: 출장 중인 재택 근무 사용자)가 인터넷을 통해 Lync Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="78189-135">**공용 사용자**   와 통신 사용 내부 사용자가 Windows Live, Yahoo\!, 북미에서 제공 하는 것과 같은 공용 IM 공급자 대화 상대와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="78189-136">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="78189-137">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="78189-138">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="78189-139">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="78189-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="78189-140">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-140">has been announced.</span></span> <span data-ttu-id="78189-141">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78189-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="78189-142">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="78189-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="78189-143">받으려면.</span><span class="sxs-lookup"><span data-stu-id="78189-143">Messenger.</span></span> <span data-ttu-id="78189-144">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="78189-145">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="78189-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="78189-146">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="78189-147">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="78189-148">외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 먼저 조직의 외부 사용자 액세스 사용을 제어 하는 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="78189-149">외부 사용자 액세스에 대 한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78189-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="78189-150">**Windows PowerShell cmdlet을 사용 하 여 외부 액세스 정책을 보려면**</span><span class="sxs-lookup"><span data-stu-id="78189-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="78189-151">Lync Server Management Shell 및 **CsExternalAccessPolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="78189-152">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78189-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="78189-153">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78189-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="78189-154">모든 외부 액세스 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="78189-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="78189-155">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78189-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="78189-156">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="78189-156">In This Section</span></span>

  - [<span data-ttu-id="78189-157">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</span><span class="sxs-lookup"><span data-stu-id="78189-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="78189-158">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="78189-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="78189-159">Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="78189-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="78189-160">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="78189-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="78189-161">Lync Server 2013에서 Lync 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="78189-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="78189-162">Lync Server 2013에서 외부 사용자 액세스 정책 다시 설정 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="78189-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

