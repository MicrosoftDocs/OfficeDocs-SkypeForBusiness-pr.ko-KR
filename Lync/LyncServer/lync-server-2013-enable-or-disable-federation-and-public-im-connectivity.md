---
title: 'Lync Server 2013: 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="936d2-102">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="936d2-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="936d2-103">_**마지막으로 수정한 주제:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="936d2-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="936d2-104">페더레이션에 대 한 지원은 파트너 도메인 및 사용자가 지 원하는 공개 인스턴트 메시징 (IM) 제공자 사용자를 포함 하 여 계정이 있는 사용자가 사용자와 공동 작업할 수 있도록 하기 위해 필요 합니다. 구성은.</span><span class="sxs-lookup"><span data-stu-id="936d2-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="936d2-105">페더레이션은 또한 호스팅된 Exchange 서비스 공급자를 사용 하 여 사서함이 Microsoft Exchange Online과 같은 호스팅된 Exchange 서비스에 있는 Enterprise Voice 사용자에 게 음성 메일을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="936d2-106">이러한 외부 도메인과의 신뢰 관계를 설정한 경우 해당 도메인의 사용자에 게 배포에 액세스 하 여 Lync Server 통신에 참여 하도록 허가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="936d2-107">이 신뢰 관계는 페더레이션 이라고 하며 Active Directory 신뢰 관계와 관련이 없거나 종속 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="936d2-108">페더레이션 도메인 사용자가 액세스를 지원 하려면 페더레이션을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="936d2-109">조직을 위해 페더레이션을 사용 하는 경우 다음 옵션을 구현할지 여부도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="936d2-110">**파트너 도메인 검색**   사용이 옵션을 사용 하도록 설정 하면 Lync Server에서 DNS (domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 없는 도메인을 검색 하 고 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하며 신뢰 수준, 트래픽 양, 관리자 설정에 따라 해당 트래픽을 제한 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="936d2-111">이 옵션을 선택 하지 않으면 허용 된 도메인 목록에 포함 된 도메인의 사용자만 페더레이션 사용자 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="936d2-112">이 옵션을 선택 하는지 여부에 관계 없이 페더레이션 도메인에서 액세스 경계 서비스를 실행 하는 특정 서버에 대 한 액세스 제한을 포함 하 여 개별 도메인을 차단 또는 허용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="936d2-113">페더레이션 도메인의 액세스를 제어 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="936d2-114">**페더레이션 파트너**     의 법적 고 지 사항 보내기 배포의 보관이 현재 위치에 있는 페더레이션 파트너로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="936d2-115">페더레이션 파트너 도메인과의 외부 통신 보관을 지 원하는 경우 보관 고 지 사항 알림을 사용 하 여 해당 메시지가 보관 되 고 있음을 파트너에 게 경고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="936d2-116">나중에 페더레이션 도메인 사용자의 액세스를 일시적으로 또는 영구적으로 방지 하려면 조직에 페더레이션 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="936d2-117">이 섹션의 절차를 사용 하 여 조직에 대해 지원 되는 적절 한 페더레이션 옵션 지정을 비롯 하 여 조직에 대 한 페더레이션 사용자 액세스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="936d2-118">조직에 페더레이션을 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버가 페더레이션 도메인에 대 한 라우팅을 지원 하도록 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="936d2-119">페더레이션 도메인의 사용자는 페더레이션 사용자 액세스를 지원 하기 위해 하나 이상의 정책을 구성할 때까지 조직의 IM 또는 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="936d2-120">공용 im 서비스 공급자의 사용자는 공용 IM 연결을 지원 하기 위해 하나 이상의 정책을 구성할 때까지 조직의 IM 또는 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="936d2-121">Lync Server는 호스팅된 음성 메일 정책을 구성할 때까지 호스트 된 Exchange 서비스에 사서함이 있는 사용자를 위한 자동 전화 교환 서비스, 전화 응답, Outlook Voice Access (음성 메일 포함)를 제공할 수 없습니다. 라우팅 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="936d2-122">다른 조직의 페더레이션 도메인 사용자와 통신 하는 데 필요한 정책을 구성 하는 방법에 대 한 자세한 내용은 운영 설명서의 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션 도메인 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="936d2-123">또한 IM 서비스 공급자의 사용자와의 통신을 지원 하려면 정책을 구성 하 고 지원 하려는 개별 서비스 공급자에 대 한 지원도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="936d2-124">자세한 내용은 운영 설명서의 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션된 공급자 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="936d2-125">호스팅된 음성 메일 정책 만들기에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="936d2-126">조직에 대 한 페더레이션 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="936d2-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="936d2-127">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="936d2-128">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="936d2-129">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="936d2-130">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="936d2-131">**액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="936d2-132">**액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="936d2-133">조직에 대해 페더레이션 사용자 액세스를 사용 하도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="936d2-134">조직의 페더레이션 사용자 액세스를 사용 하지 않도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="936d2-135">**페더레이션 사용자와 통신 사용** 확인란을 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="936d2-136">파트너 도메인의 자동 검색을 지원 하려면 **파트너 도메인 검색 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="936d2-137">조직에서 외부 통신 보관을 지 원하는 경우 **페더레이션 파트너에 게 보관 고 지 사항 보내기** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="936d2-138">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-138">Click **Commit**.</span></span>

<span data-ttu-id="936d2-139">페더레이션 사용자가 Lync Server 2013 배포에서 사용자와 공동 작업할 수 있도록 하려면 하나 이상의 외부 액세스 정책을 구성 하 여 페더레이션 사용자 액세스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="936d2-140">자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="936d2-141">특정 페더레이션 도메인에 대 한 액세스를 제어 하려면 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 허용 된 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="936d2-142">Windows PowerShell Cmdlet을 사용 하 여 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="936d2-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="936d2-143">페더레이션 및 공용 IM 연결도 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="936d2-144">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="936d2-145">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="936d2-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="936d2-146">페더레이션 및 공용 IM 연결을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="936d2-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="936d2-147">페더레이션 및 공용 IM 연결을 사용 하도록 설정 하려면 **AllowFederatedUsers** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="936d2-148">페더레이션 및 공용 IM 연결을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="936d2-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="936d2-149">페더레이션 및 공용 IM 연결을 사용 하지 않으려면 **AllowFederatedUsers** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="936d2-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

