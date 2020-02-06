---
title: 조직에 대한 액세스 에지 구성 관리
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원 되는 Edge 서버를 통해 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스, 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818349"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="72e39-103">조직에 대한 액세스 에지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="72e39-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="72e39-104">하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원 되는 Edge 서버를 통해 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스, 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="72e39-105">이러한 옵션에는 **액세스에 지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 유형의 액세스 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="72e39-106">**페더레이션 및 공용 IM 연결**   사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="72e39-107">이 설정은 **외부 액세스 정책** 페이지의 전역, 사이트 또는 사용자 범위에 대해 구성 된 SIP 페더레이션에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="72e39-108">페더레이션 설정을 적용 하려면 두 페이지에 모두 페더레이션 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="72e39-109">페더레이션 파트너를 검색 하는 방법에 대 한 선택적 설정 인 두 가지 옵션, 보관 고 지 사항 (배포에 보관이 설정 되어 있는 페더레이션 대화 상대에 대 한 알림 및 통신에 대 한 의사 소통 세부 정보 보관 됨)이 연락처에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="72e39-110">**파트너 도메인 검색**   사용이 옵션을 선택 하면 페더레이션 할 수 있는 도메인의 자동 검색이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="72e39-111">비즈니스용 Skype 서버는 DNS (Domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 나열 되지 않은 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하 고, 신뢰에 따라 해당 트래픽을 제한 하거나 차단 합니다. 수준, 트래픽 양, 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="72e39-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="72e39-112">이 옵션을 선택 하지 않으면 허용 된 도메인 목록에 포함 된 도메인의 사용자만 페더레이션 사용자 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="72e39-113">이 옵션을 선택 하는지 여부에 관계 없이 페더레이션 도메인에서 액세스 경계 서비스를 실행 하는 특정 서버에 대 한 액세스 제한을 포함 하 여 개별 도메인을 차단 또는 허용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="72e39-114">자세한 내용은 허용 된 [외부 도메인에 대 한 지원 구성을](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72e39-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="72e39-115">**페더레이션 파트너**   에 게 보관 거부 메시지 보내기이 옵션을 선택 하면 통신 세부 정보를 기록 한다는 것을 제안 하는 페더레이션 파트너에 게 보관 고 지 사항을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="72e39-116">페더레이션 파트너 도메인과 외부 통신을 보관 하는 경우 보관 고 지 사항 알림을 사용 하 여 해당 메시지와 통신 정보가 배포에 보관 되 고 있음을 알리는 것이 파트너에 게 경고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="72e39-117">보관에 대 한 자세한 내용은 [페더레이션 파트너에 보관 거부 전송 사용 또는 사용 안 함을](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72e39-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="72e39-118">**원격 사용자 액세스**   사용 설정 방화벽 외부의 사용자 (예: 출장 중인 가정용 가정용 사용자)가 비즈니스용 Skype Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="72e39-119">자세한 내용은 [원격 사용자 액세스 설정 또는 해제](enable-or-disable-remote-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72e39-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="72e39-120">**회의에 액세스할 수 있도록 허용**   내부 사용자가 자신이 구성 하는 회의에 외부 익명 사용자를 초대 하도록 하려면이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="72e39-121">이 설정을 사용 하면 익명 사용자만 회의에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="72e39-122">외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 조직의 원격 사용자 액세스 사용을 제어 하는 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="72e39-123">외부 사용자 액세스를 위한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 [조직의 외부 액세스 정책 관리](../external-access-policies/manage-external-access-policy-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72e39-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="72e39-124">**Windows PowerShell cmdlet을 사용 하 여 액세스에 지 구성 정보 보기**</span><span class="sxs-lookup"><span data-stu-id="72e39-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="72e39-125">Windows PowerShell 및 **CsAccessEdgeConfiguration** cmdlet을 사용 하 여 액세스에 지 구성 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="72e39-126">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="72e39-127">모든 액세스에 지 구성 설정에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="72e39-128">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e39-128">That will return information similar to this:</span></span>
    
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

