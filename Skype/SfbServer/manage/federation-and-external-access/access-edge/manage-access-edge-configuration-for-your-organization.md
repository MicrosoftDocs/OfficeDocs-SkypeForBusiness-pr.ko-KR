---
title: 조직에 대한 액세스 Edge 구성 관리
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 하나 이상의 에지 서버를 배포한 후 조직에서 지원되는 에지 서버를 통해 회의에 대한 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스 및 익명 사용자 액세스를 사용하도록 설정해야 합니다.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817338"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>조직에 대한 액세스 Edge 구성 관리

하나 이상의 에지 서버를 배포한 후 조직에서 지원되는 에지 서버를 통해 회의에 대한 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스 및 익명 사용자 액세스를 사용하도록 설정해야 합니다.

이러한 옵션에는 **액세스 에지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 액세스 유형이 포함됩니다.

  - **페더ation 및 공용 IM**   연결을 사용하도록 설정   페더타 파트너 도메인에 대한 사용자 액세스를 지원하려면 이 옵션을 사용하도록 설정하세요. 이 설정은 외부 액세스 정책 페이지의 전역, 사이트 또는 사용자 범위에 대해 구성된 SIP 페더전에 **적용됩니다.** 페더전 설정을 적용하려면 두 페이지에서 모두 페더전 지원을 구성해야 합니다.
    
    페더링 파트너가 검색된 방식과 보관 고지 사항(배포에서 보관을 사용하도록 설정하고 통신 세부 정보가 보관될 것임과 통신하는 페더링 연락처에 대한 알림)이 연락처에게 전송될지 여부에 대한 선택적 설정인 두 가지 옵션이 있습니다.
    
      - **파트너 도메인 검색 사용**   이 옵션을 선택하면 페더링할 수 있는 도메인을 자동으로 검색할 수 있습니다. 비즈니스용 Skype 서버는 DNS(Domain Name System) 레코드를 사용하여 허용 도메인 목록에 나열되지 않은 도메인을 검색하여 검색된 페더링 파트너의 들어오는 트래픽을 자동으로 평가하고 트러스트 수준, 트래픽 양 및 관리자 설정에 따라 해당 트래픽을 제한하거나 차단합니다. 이 옵션을 선택하지 않은 경우 허용된 도메인 목록에 포함되는 도메인의 사용자에 한해 페더타 사용자 액세스가 사용하도록 설정됩니다. 이 옵션을 선택하는지 여부에 따라 페더링 도메인에서 액세스 에지 서비스를 실행하는 특정 서버에 대한 액세스 제한을 포함하여 개별 도메인을 차단하거나 허용하도록 지정할 수 있습니다. 자세한 내용은 허용되는 외부 도메인에 대한 지원 [구성을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **페더링**   파트너에게 보관 고지 조항 보내기   이 옵션을 선택하면 통신 세부 정보를 기록할 것을 알려주는 보관 고지 사항 메시지를 페더링 파트너에게 보낼 수 있습니다. 페더레이드 파트너 도메인과의 외부 통신을 보관하는 경우 보관 고지 사항 알림을 사용하도록 설정하여 파트너에게 배포에 의해 메시지 및 통신 세부 정보가 보관되고 있는 것을 경고해야 합니다. 보관에 대한 자세한 내용은 페더링 파트너에게 보관 고지 사항 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **원격 사용자 액세스 사용**   방화벽 외부의 사용자(예: 재직자 및 출장하는 사용자)가 비즈니스용 Skype 서버에 연결할 수 있도록 하려는 경우 이 옵션을 사용하도록 설정하세요. 자세한 내용은 원격 사용자 액세스 사용 또는 [사용 안 하도록 설정 을 참조 합니다.](enable-or-disable-remote-user-access.md)

  - **익명 사용자가 회의에 액세스할 수 있도록 설정**   내부 사용자가 구성하는 회의에 외부 익명 사용자를 초대하도록 하려는 경우 이 옵션을 사용하도록 설정하세요. 이 설정을 사용하도록 설정하면 익명 사용자만 회의에 사용할 수 있습니다.

> [!NOTE]  
> 외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 정책을 구성하여 조직에서 원격 사용자 액세스 사용을 제어해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다. 외부 사용자 액세스에 대한 정책을 만들고 구성하고 적용하는 데 대한 자세한 내용은 조직의 외부 액세스 정책 [관리를 참조합니다.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**에지 cmdlet을 사용하여 액세스 Windows PowerShell 정보 보기**

  - 액세스 에지 구성 정보는 Windows PowerShell **Get-CsAccessEdgeConfiguration** cmdlet을 사용하여 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell. 
    
    모든 액세스 에지 구성 설정에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르십시오.
    
     `Get-CsAccessEdgeConfiguration`
    
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

