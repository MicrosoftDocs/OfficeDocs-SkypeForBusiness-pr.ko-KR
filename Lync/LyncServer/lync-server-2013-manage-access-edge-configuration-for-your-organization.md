---
title: 'Lync Server 2013: 조직에 대한 액세스 에지 구성 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="e0b0b-102">Lync Server 2013에서 조직에 대한 액세스 에지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="e0b0b-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0b0b-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e0b0b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e0b0b-104">이 문서는 예비 문서로, 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="e0b0b-105">빈 항목은 개체 틀로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="e0b0b-106">하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원 되는 Edge 서버를 통해 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스, 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="e0b0b-107">이러한 옵션에는 **액세스에 지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 유형의 액세스 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="e0b0b-108">**페더레이션 및 공용 IM 연결**   사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="e0b0b-109">이 설정은 **외부 액세스 정책** 페이지에서 전역, 사이트 또는 사용자 범위에 대해 구성 된 SIP 페더레이션 및 xmpp 페더레이션 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="e0b0b-110">페더레이션 설정을 적용 하려면 두 페이지에 모두 페더레이션 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="e0b0b-111">페더레이션 파트너를 검색 하는 방법에 대 한 선택적 설정 인 두 가지 옵션, 보관 고 지 사항 (배포에 보관이 설정 되어 있는 페더레이션 대화 상대에 대 한 알림 및 통신에 대 한 의사 소통 세부 정보 보관 됨)이 연락처에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="e0b0b-112">**파트너 도메인 검색**   사용이 옵션을 선택 하면 페더레이션 할 수 있는 도메인의 자동 검색이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="e0b0b-113">Lync Server 2013에서는 DNS (Domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 없는 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하 고, 신뢰 수준에 따라 해당 트래픽을 제한 하거나 차단 합니다. 트래픽 양 및 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="e0b0b-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="e0b0b-114">이 옵션을 선택 하지 않으면 허용 된 도메인 목록에 포함 된 도메인의 사용자만 페더레이션 사용자 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="e0b0b-115">이 옵션을 선택 하는지 여부에 관계 없이 페더레이션 도메인에서 액세스 경계 서비스를 실행 하는 특정 서버에 대 한 액세스 제한을 포함 하 여 개별 도메인을 차단 또는 허용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="e0b0b-116">자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="e0b0b-117">**페더레이션 파트너**   에 게 보관 거부 메시지 보내기이 옵션을 선택 하면 통신 세부 정보를 기록 한다는 것을 제안 하는 페더레이션 파트너에 게 보관 고 지 사항을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="e0b0b-118">페더레이션 파트너 도메인과 외부 통신을 보관 하는 경우 보관 고 지 사항 알림을 사용 하 여 해당 메시지와 통신 정보가 배포에 보관 되 고 있음을 알리는 것이 파트너에 게 경고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="e0b0b-119">보관에 대 한 자세한 내용은 [Lync Server 2013에서 보관에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-archiving.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="e0b0b-120">**원격 사용자 액세스**   사용 설정 방화벽 외부의 사용자 (예: 여행 중인 재택 근무자 및 사용자가 Lync Server에 연결할 수 있는 경우)를 사용 하도록 설정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="e0b0b-121">자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="e0b0b-122">**회의에 액세스할 수 있도록 허용**   내부 사용자가 자신이 구성 하는 회의에 외부 익명 사용자를 초대 하도록 하려면이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="e0b0b-123">이 설정을 사용 하면 익명 사용자만 회의에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="e0b0b-124">회의 환경과 사용자가 회의를 통해 수행할 수 있는 방법 및 작업을 정의 하는 옵션과 익명 사용자를 포함 하는 옵션을 구성 하려면 [사이트 또는 사용자에 대 한 회의 사용자 환경 만들기 또는 수정](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) 의 세부 정보 및 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0b0b-125">외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 조직의 원격 사용자 액세스 사용을 제어 하는 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="e0b0b-126">외부 사용자 액세스를 위한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e0b0b-127">**Windows PowerShell cmdlet을 사용 하 여 액세스에 지 구성 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="e0b0b-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="e0b0b-128">Windows PowerShell 및 **CsAccessEdgeConfiguration** cmdlet을 사용 하 여 액세스에 지 구성 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="e0b0b-129">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e0b0b-130">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="e0b0b-131">모든 액세스에 지 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="e0b0b-132">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0b0b-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0b0b-133">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e0b0b-133">In This Section</span></span>

  - [<span data-ttu-id="e0b0b-134">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e0b0b-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="e0b0b-135">Lync Server 2013에서 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e0b0b-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="e0b0b-136">Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e0b0b-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="e0b0b-137">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e0b0b-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="e0b0b-138">Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e0b0b-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="e0b0b-139">Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e0b0b-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

