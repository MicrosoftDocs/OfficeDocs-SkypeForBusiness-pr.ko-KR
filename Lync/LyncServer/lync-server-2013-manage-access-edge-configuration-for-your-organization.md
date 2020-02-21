---
title: 'Lync Server 2013: 조직에 대 한 액세스에 지 구성 관리'
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
ms.openlocfilehash: 31aa51647fa19a11cb4944829c2ab5e8eb10f2e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 내용은 예비 설명서 이며 변경 될 수 있습니다. 빈 항목은 자리 표시자로 포함되어 있습니다.

하나 이상의에 지 서버를 배포한 후에는 외부 도메인 또는 공급자 액세스 권한, 원격 사용자 액세스 및 조직에 대해 지원 되는에 지 서버를 통해 회의에 대 한 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.

이러한 옵션에는 **액세스 에지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 액세스 유형이 포함됩니다.

  - **페더레이션**   파트너 도메인에 대 한 사용자 액세스를 지원 하려면 페더레이션을 사용 하도록 설정 및 공용 IM 연결을 사용 하도록 설정 합니다. 이 설정은 **외부 액세스 정책** 페이지에서 전역, 사이트 또는 사용자 범위에 대해 구성 된 SIP 페더레이션 및 xmpp 페더레이션 둘 다에 적용 됩니다. 페더레이션 설정을 적용 하려면 두 페이지에서 모두 페더레이션 지원을 구성 해야 합니다.
    
    페더레이션 파트너를 검색하는 방법 및 보관 고지 사항(배포에서 보관이 사용하도록 설정되었으며 통신 세부 정보가 보관됨을 알리는 통신 대상 페더레이션 연락처에 대한 알림)을 연락처에게 보낼지 여부에 대한 선택적 설정인 두 가지 옵션이 있습니다.
    
      - **파트너 도메인 검색**   사용이 옵션을 선택 하면 페더레이션 할 수 있는 도메인의 자동 검색이 사용 하도록 설정 됩니다. Lync Server 2013는 DNS (Domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 나열 되지 않은 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하며, 신뢰 수준에 따라 트래픽을 제한 하거나 차단 합니다. 트래픽 양 및 관리자 설정 이 옵션을 선택 하지 않으면 허용 도메인 목록에 포함 된 도메인의 사용자에 대해서만 페더레이션 사용자 액세스를 사용할 수 있습니다. 이 옵션을 선택 하지 않으면 페더레이션 도메인에서 액세스에 지 서비스를 실행 하는 특정 서버에 대 한 액세스 제한 등 개별 도메인을 차단 하거나 허용 하도록 지정할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md)참조 하십시오.
    
      - **페더레이션 파트너**   에 게 보관 고 지 사항 보내기이 옵션을 선택 하면 통신 세부 정보가 기록 된다는 것을 알리는 페더레이션 파트너에 게 보관 고 지 메시지를 보낼 수 있습니다. 페더레이션 파트너 도메인과의 외부 통신을 보관 하는 경우 보관 고 지 사항 알림을 사용 하 여 배포에 따라 메시지 및 통신 세부 정보가 보관 된다는 것을 파트너에 게 경고 해야 합니다. 보관에 대 한 자세한 내용은 [Lync Server 2013에서 보관에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-archiving.md)를 참조 하세요.

  - **원격 사용자 액세스**   사용 조직에서 방화벽 외부의 사용자 (예: 여행 중인 재택 사용자)가 Lync Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다. 자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.

  - **회의 액세스를 사용 하도록 설정**   내부 사용자가 외부 익명 사용자를 구성 하는 전화 회의에 초대 하도록 하려면이 옵션을 사용 하도록 설정 합니다. 이 설정을 사용 하도록 설정 하면 익명 사용자만 회의를 할 수 있습니다. 사용자가 회의를 하거나 익명 사용자를 포함 하 여 수행할 수 있는 작업과 방법을 정의 하는 회의 환경 및 옵션을 구성 하려면 [사이트 또는 사용자에 대 한 회의 사용자 환경 만들기 또는 수정](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) 에서 자세한 정보 및 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.

<div>


> [!NOTE]  
> 외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 정책을 구성하여 조직에서 원격 사용자 액세스 사용을 제어해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다. 외부 사용자 액세스에 대 한 정책을 만들고 구성 하 고 적용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하십시오.



</div>

**Windows PowerShell cmdlet을 사용 하 여 액세스에 지 구성 정보 보기**

  - 액세스에 지 구성 정보는 Windows PowerShell 및 **set-csaccessedgeconfiguration** cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.
    
    모든 액세스에 지 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsAccessEdgeConfiguration
    
    그러면 다음과 같은 정보가 반환됩니다.
    
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

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Lync Server 2013의 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013에서 익명 사용자를 지원 하기 위한 회의 정책 할당](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

