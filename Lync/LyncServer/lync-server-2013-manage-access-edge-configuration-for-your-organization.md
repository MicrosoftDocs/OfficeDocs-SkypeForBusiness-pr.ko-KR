---
title: 'Lync Server 2013: 조직에 대 한 액세스에 지 구성 관리'
description: 'Lync Server 2013: 조직에 대 한 액세스에 지 구성을 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550644"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="6499b-103">Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="6499b-103">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6499b-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6499b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6499b-105">이 내용은 예비 설명서 이며 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="6499b-106">빈 항목은 자리 표시자로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="6499b-107">하나 이상의에 지 서버를 배포한 후에는 외부 도메인 또는 공급자 액세스 권한, 원격 사용자 액세스 및 조직에 대해 지원 되는에 지 서버를 통해 회의에 대 한 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-107">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="6499b-108">이러한 옵션에는 **액세스 에지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 액세스 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-108">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="6499b-109">**페더레이션 및 공용 IM 연결 사용**     페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-109">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="6499b-110">이 설정은 **외부 액세스 정책** 페이지에서 전역, 사이트 또는 사용자 범위에 대해 구성 된 SIP 페더레이션 및 xmpp 페더레이션 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-110">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="6499b-111">페더레이션 설정을 적용 하려면 두 페이지에서 모두 페더레이션 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-111">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="6499b-112">페더레이션 파트너를 검색하는 방법 및 보관 고지 사항(배포에서 보관이 사용하도록 설정되었으며 통신 세부 정보가 보관됨을 알리는 통신 대상 페더레이션 연락처에 대한 알림)을 연락처에게 보낼지 여부에 대한 선택적 설정인 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-112">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="6499b-113">**파트너 도메인 검색 사용**     이 옵션을 선택 하면 페더레이션 할 수 있는 도메인의 자동 검색을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-113">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="6499b-114">Lync Server 2013는 DNS (Domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 나열 되지 않은 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하며, 신뢰 수준, 트래픽 양 및 관리자 설정에 따라 트래픽을 제한 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-114">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="6499b-115">이 옵션을 선택 하지 않으면 허용 도메인 목록에 포함 된 도메인의 사용자에 대해서만 페더레이션 사용자 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-115">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="6499b-116">이 옵션을 선택 하지 않으면 페더레이션 도메인에서 액세스에 지 서비스를 실행 하는 특정 서버에 대 한 액세스 제한 등 개별 도메인을 차단 하거나 허용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-116">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="6499b-117">자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6499b-117">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="6499b-118">**페더레이션 파트너**     에 게 보관 고 지 사항 보내기 이 옵션을 선택 하면 페더레이션 파트너에 게 통신 세부 정보를 기록 하도록 하는 보관 고 지 사항 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-118">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="6499b-119">페더레이션 파트너 도메인과의 외부 통신을 보관 하는 경우 보관 고 지 사항 알림을 사용 하 여 배포에 따라 메시지 및 통신 세부 정보가 보관 된다는 것을 파트너에 게 경고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-119">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="6499b-120">보관에 대 한 자세한 내용은 [Lync Server 2013에서 보관에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-archiving.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6499b-120">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="6499b-121">**원격 사용자 액세스 사용**     여행 중인 재택 사용자와 같이 방화벽 외부의 사용자가 Lync Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-121">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="6499b-122">자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6499b-122">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="6499b-123">**익명 사용자가 회의에 액세스할 수 있도록 설정**     내부 사용자가 외부 익명 사용자를 구성 하는 전화 회의를 초대 하도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-123">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="6499b-124">이 설정을 사용 하도록 설정 하면 익명 사용자만 회의를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-124">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="6499b-125">사용자가 회의를 하거나 익명 사용자를 포함 하 여 수행할 수 있는 작업과 방법을 정의 하는 회의 환경 및 옵션을 구성 하려면 [사이트 또는 사용자에 대 한 회의 사용자 환경 만들기 또는 수정](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) 에서 자세한 정보 및 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6499b-125">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6499b-126">외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 정책을 구성하여 조직에서 원격 사용자 액세스 사용을 제어해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-126">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="6499b-127">외부 사용자 액세스에 대 한 정책을 만들고 구성 하 고 적용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6499b-127">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6499b-128">**Windows PowerShell cmdlet을 사용 하 여 액세스에 지 구성 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="6499b-128">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="6499b-129">액세스에 지 구성 정보는 Windows PowerShell 및 **set-csaccessedgeconfiguration** cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-129">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="6499b-130">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6499b-131">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="6499b-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="6499b-132">모든 액세스에 지 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-132">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="6499b-133">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6499b-133">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="6499b-134">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6499b-134">In This Section</span></span>

  - [<span data-ttu-id="6499b-135">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6499b-135">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="6499b-136">Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6499b-136">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="6499b-137">Lync Server 2013의 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6499b-137">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="6499b-138">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6499b-138">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="6499b-139">Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6499b-139">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="6499b-140">Lync Server 2013에서 익명 사용자를 지원 하기 위한 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6499b-140">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

