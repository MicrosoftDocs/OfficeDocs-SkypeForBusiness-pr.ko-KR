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
localization_priority: Normal
description: 하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원 되는 Edge 서버를 통해 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스, 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188859"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>조직에 대한 액세스 에지 구성 관리

하나 이상의 Edge 서버를 배포한 후에는 조직에서 지원 되는 Edge 서버를 통해 외부 도메인 또는 공급자 액세스, 원격 사용자 액세스, 익명 사용자 액세스를 사용 하도록 설정 해야 합니다.

이러한 옵션에는 **액세스에 지 구성** 페이지를 통해 구성할 수 있는 다음과 같은 유형의 액세스 권한이 포함 됩니다.

  - **페더레이션 및 공용 IM 연결**   사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다. 이 설정은 **외부 액세스 정책** 페이지의 전역, 사이트 또는 사용자 범위에 대해 구성 된 SIP 페더레이션에 적용 됩니다. 페더레이션 설정을 적용 하려면 두 페이지에 모두 페더레이션 지원을 구성 해야 합니다.
    
    페더레이션 파트너를 검색 하는 방법에 대 한 선택적 설정 인 두 가지 옵션, 보관 고 지 사항 (배포에 보관이 설정 되어 있는 페더레이션 대화 상대에 대 한 알림 및 통신에 대 한 의사 소통 세부 정보 보관 됨)이 연락처에 게 전송 됩니다.
    
      - **파트너 도메인 검색**   사용이 옵션을 선택 하면 페더레이션 할 수 있는 도메인의 자동 검색이 가능 합니다. 비즈니스용 Skype 서버는 DNS (Domain Name System) 레코드를 사용 하 여 허용 된 도메인 목록에 나열 되지 않은 도메인을 검색 하 고, 검색 된 페더레이션 파트너 로부터 들어오는 트래픽을 자동으로 평가 하 고, 신뢰에 따라 해당 트래픽을 제한 하거나 차단 합니다. 수준, 트래픽 양, 관리자 설정 이 옵션을 선택 하지 않으면 허용 된 도메인 목록에 포함 된 도메인의 사용자만 페더레이션 사용자 액세스를 사용할 수 있습니다. 이 옵션을 선택 하는지 여부에 관계 없이 페더레이션 도메인에서 액세스 경계 서비스를 실행 하는 특정 서버에 대 한 액세스 제한을 포함 하 여 개별 도메인을 차단 또는 허용 하도록 지정할 수 있습니다. 자세한 내용은 허용 된 [외부 도메인에 대 한 지원 구성을](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)참조 하세요.
    
      - **페더레이션 파트너**   에 게 보관 거부 메시지 보내기이 옵션을 선택 하면 통신 세부 정보를 기록 한다는 것을 제안 하는 페더레이션 파트너에 게 보관 고 지 사항을 보낼 수 있습니다. 페더레이션 파트너 도메인과 외부 통신을 보관 하는 경우 보관 고 지 사항 알림을 사용 하 여 해당 메시지와 통신 정보가 배포에 보관 되 고 있음을 알리는 것이 파트너에 게 경고 해야 합니다. 보관에 대 한 자세한 내용은 [페더레이션 파트너에 보관 거부 전송 사용 또는 사용 안 함을](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)참조 하세요.

  - **원격 사용자 액세스**   사용 설정 방화벽 외부의 사용자 (예: 출장 중인 가정용 가정용 사용자)가 비즈니스용 Skype Server에 연결할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다. 자세한 내용은 [원격 사용자 액세스 설정 또는 해제](enable-or-disable-remote-user-access.md)를 참조 하세요.

  - **회의에 액세스할 수 있도록 허용**   내부 사용자가 자신이 구성 하는 회의에 외부 익명 사용자를 초대 하도록 하려면이 옵션을 사용 합니다. 이 설정을 사용 하면 익명 사용자만 회의에 참석할 수 있습니다.

> [!NOTE]  
> 외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 조직의 원격 사용자 액세스 사용을 제어 하는 정책을 구성 합니다. 외부 사용자 액세스를 위한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 [조직의 외부 액세스 정책 관리](../external-access-policies/manage-external-access-policy-for-your-organization.md)를 참조 하세요.

**Windows PowerShell cmdlet을 사용 하 여 액세스에 지 구성 정보 보기**

  - Windows PowerShell 및 **CsAccessEdgeConfiguration** cmdlet을 사용 하 여 액세스에 지 구성 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 
    
    모든 액세스에 지 구성 설정에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
     `Get-CsAccessEdgeConfiguration`
    
    이는 다음과 같은 정보를 반환 합니다.
    
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

