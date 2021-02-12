---
title: 클라우드 커넥터에서 여러 사이트 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Cloud Connector Edition에서 여러 PSTN 사이트를 배포하는 방법을 자세히 알아보고,
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358924"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>클라우드 커넥터에서 여러 사이트 배포

> [!Important] 
> Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Cloud Connector Edition에서 여러 PSTN 사이트를 배포하는 방법을 자세히 알아보고,
  
이 섹션에서는 여러 PSTN(Public Switched Telephone Network) 사이트를 배포하는 방법을 설명합니다. 사이트는 단일 사이트를 배포하는 단계와 동일한 단계를 사용하여 한 번씩 배포됩니다. 이 항목에서는 다중 사이트 배포의 사이트와 사이트 간 고려 사항과 차이점에 대해 설명합니다. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>여러 PSTN(Public Switched Telephone Network) 사이트

다음에서는 서로 다른 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 커넥터 Edition을 배포하는 예제 구성을 보여줍니다. 배포를 시작하기 전에 구성 설정이 올바른지 확인합니다.
  
PSTN 사이트 1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN 사이트 2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

추가할 각 PSTN 사이트에 대해 클라우드 커넥터에서 단일 사이트 배포의 [단계를 따릅니다.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> HA(고가용성)를 준비하기 위한 공유 폴더는 PSTN 사이트당입니다. 공유 **폴더는** PSTN 사이트 간에 달라야 합니다. 여러 사이트에 동일한 공유 폴더를 사용하지 않습니다.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>다중 사이트 배포에 비해 HA(고가용성)가 있는 단일 사이트
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

다음 표에는 HA가 지원되는 단일 사이트와 다중 사이트 배포 간의 차이점이 나열됩니다.
  
|**범주**|**항목**|**HA가 있는 단일 사이트**|**다중 사이트**|
|:-----|:-----|:-----|:-----|
|구성  <br/> |Appliance 호스트 이름 <br/> |**다양한** 어플라이언스 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|설정  <br/> |공유 폴더  <br/> |**어플라이언스에서** 동일한 공유 폴더 필요 <br/> |**어플라이언스에** 다른 공유 폴더 필요 <br/> |
|구성  <br/> |VirtualMachineDomain  <br/> |**어플라이언스에** 동일한 도메인 필요 <br/> |PSTN **사이트에** 동일한 도메인 필요 <br/> |
|구성  <br/> |SIPDomains  <br/> |여러 어플라이언스에서 도메인 이름과 **순서가** 동일해야 합니다. <br/> |도메인 이름 및 순서는 PSTN 사이트에서 동일해야 합니다.  <br/> |
|구성  <br/> |사이트 이름  <br/> |**동일** 어플라이언스 전체의 사이트 이름 <br/> |**서로 다른 경우** PSTN 사이트의 사이트 이름 <br/> |
|구성  <br/> |서버 이름  <br/> |**다양한** 어플라이언스 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|구성  <br/> |내부 풀 FQDNS  <br/> |**여러** 어플라이언스에서 동일 <br/> | PSTN 사이트 전체에서 동일 <br/> |
|구성  <br/> |내부 IPS  <br/> |**다양한** 어플라이언스 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|구성  <br/> |외부 FQDN  <br/> |**여러** 어플라이언스에서 동일 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|구성  <br/> |외부 IPS  <br/> |**다양한** 어플라이언스 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|구성  <br/> |PSTN GW 설정  <br/> |**여러** 어플라이언스에서 동일 <br/> |**PSTN** 사이트마다 다를 수 있습니다. <br/> |
|구성  <br/> |DNS 레코드  <br/> |외부 액세스  FQDNS와 **IP** 주소가 동일한 레코드 추가 <br/> |다른 외부  액세스 FQDNS 및 IP 주소가 다른 **레코드** 추가 <br/> |
|설정  <br/> |하이브리드 테넌트  <br/> |HybridPSTNSite 설정  <br/> 폴백에 대한 PeerDestination 설정  <br/> |HybridPSTNSite 설정  <br/> 폴백에 대한 PeerDestination 설정  <br/> |
|설정  <br/> |게이트웨이  <br/> |이 사이트의 MS GW **M:N** 매핑 <br/> |각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결해야 합니다.  <br/> |
|설정  <br/> |사용자  <br/> |UserPSTNSettings 설정  <br/> |UserPSTNSettings 설정  <br/> |
   

