---
title: 조직에 대한 액세스 Edge 구성 관리
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원되는 에지 서버를 통해 외부 도메인 또는 공급자 액세스 유형, 원격 사용자 액세스 및 익명 사용자 액세스를 회의에 사용하도록 설정해야 합니다.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674600"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>조직에 대한 액세스 Edge 구성 관리

하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원되는 에지 서버를 통해 외부 도메인 또는 공급자 액세스 유형, 원격 사용자 액세스 및 익명 사용자 액세스를 회의에 사용하도록 설정해야 합니다.

이러한 옵션에는 **액세스 에지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 액세스 유형이 포함됩니다.

  - **페더레이션 및 공용 IM 연결 사용**   페더레이션된 파트너 도메인에 대한 사용자 액세스를 지원하려는 경우 이를 사용하도록 설정합니다. 이 설정은 **외부 액세스 정책** 페이지의 전역, 사이트 또는 사용자 범위에 대해 구성된 SIP 페더레이션에 적용됩니다. 페더레이션 설정을 적용하려면 두 페이지에서 페더레이션 지원을 구성해야 합니다.
    
    페더레이션된 파트너를 검색하는 방법에 대한 선택적 설정인 두 가지 옵션이 있으며, 보관 고지 사항(배포와 통신하는 페더레이션된 연락처에 대한 알림이 보관을 사용하도록 설정되어 있고 통신 세부 정보가 보관될 것임을 알려 줍니다.)
    
      - **파트너 도메인 검색 사용**   이 옵션을 선택하면 페더레이션할 수 있는 도메인을 자동으로 검색할 수 있습니다. 비즈니스용 Skype 서버 DNS(Domain Name System) 레코드를 사용하여 허용된 도메인 목록에 나열되지 않은 도메인을 검색하고, 검색된 페더레이션 파트너로부터 들어오는 트래픽을 자동으로 평가하고, 신뢰 수준, 트래픽 양 및 관리자 설정에 따라 해당 트래픽을 제한하거나 차단합니다. 이 옵션을 선택하지 않으면 허용된 도메인 목록에 포함된 도메인의 사용자에 대해서만 페더레이션된 사용자 액세스가 활성화됩니다. 이 옵션을 선택하든 그렇지 않든 페더레이션된 도메인에서 Access Edge 서비스를 실행하는 특정 서버에 대한 액세스를 제한하는 것을 포함하여 개별 도메인을 차단하거나 허용하도록 지정할 수 있습니다. 자세한 내용은 [허용된 외부 도메인에 대한 지원 구성을 참조하세요](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **페더레이션 파트너에게 보관 고지 사항 보내기**   이 옵션을 선택하면 통신 세부 정보가 기록되도록 조언하는 페더레이션 파트너에게 보관 고지 사항 메시지를 보낼 수 있습니다. 페더레이션된 파트너 도메인과 외부 통신을 보관하는 경우 보관 고지 사항 알림을 사용하도록 설정하여 파트너에게 해당 메시지 및 통신 세부 정보가 배포에 의해 보관되고 있음을 경고해야 합니다. 보관에 대한 자세한 내용은 [보관 고지 사항을 페더레이션된 파트너에게 보내기 사용 또는 사용 안](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) 함을 참조하세요.

  - **원격 사용자 액세스 사용**   통신 사용자 및 이동 중인 사용자와 같이 방화벽 외부에 있는 조직의 사용자가 비즈니스용 Skype 서버 연결할 수 있도록 하려면 이 옵션을 사용하도록 설정합니다. 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](enable-or-disable-remote-user-access.md) 참조하세요.

  - **익명 사용자가 회의에 액세스할 수 있도록 설정**   내부 사용자가 외부 익명 사용자를 조직하는 회의에 초대하도록 하려면 이 옵션을 사용하도록 설정합니다. 이 설정을 사용하도록 설정하면 익명 사용자만 회의에 참석할 수 있습니다.

> [!NOTE]  
> 외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 정책을 구성하여 조직에서 원격 사용자 액세스 사용을 제어해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다. 외부 사용자 액세스에 대한 정책을 만들고 구성하고 적용하는 방법에 대한 자세한 내용은 [조직의 외부 액세스 정책 관리를 참조하세요](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Windows PowerShell cmdlet을 사용하여 Access Edge 구성 정보 보기**

  - Access Edge 구성 정보는 Windows PowerShell 및 **Get-CsAccessEdgeConfiguration** cmdlet을 사용하여 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 원격 세션에서 실행할 수 있습니다. 
    
    모든 Access Edge 구성 설정에 대한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter 키를 누릅니다.
    
     `Get-CsAccessEdgeConfiguration`
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    ID: 전역<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers: False<br/>
    AllowOutsideUsers: True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery: False<br/>
    EnableArchivingDisclaimer: False<br/>
    EnableUserReplicator: True<br/>
    KeepCrlsUpToDateForPeers: True<br/>
    MarkSourceVerifiableOnOutgoingMessages: True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate: 20<br/>
    EnableDiscoveredPartnerContactsLimit: True<br/>
    MaxContactsPerDiscoveredPartner: 1000<br/>
    DiscoveredPartnerReportPeriodMinutes: 60<br/>
    MaxAcceptedCertificatesStored: 1000<br/>
    MaxRejectedCertificatesStored: 500<br/>
    CertificatesDeletedPercentage: 20<br/>
    RoutingMethod: UseDnsSrvRouting<br/>

