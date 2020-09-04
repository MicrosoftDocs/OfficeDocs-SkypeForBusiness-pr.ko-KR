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
description: 클라우드 커넥터 Edition에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358924"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>클라우드 커넥터에서 여러 사이트 배포

> [!Important] 
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.

클라우드 커넥터 Edition에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.
  
이 섹션에서는 여러 PSTN (공중 전화망) 사이트를 배포 하는 방법에 대해 설명 합니다. 단일 사이트를 배포 하는 것과 동일한 단계를 사용 하 여 한 번에 하나씩 사이트를 배포 합니다. 이 항목에서는 여러 사이트 배포의 사이트 간 고려 사항 및 차이점에 대해 설명 합니다. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>여러 PSTN (공중 전화망) 사이트

다음은 다양 한 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 Connector Edition을 배포 하는 예제 구성입니다. 배포를 시작 하기 전에 구성 설정이 올바른지 확인 하십시오.
  
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

추가 하려는 각 PSTN 사이트에 대해 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md)의 단계를 따릅니다.
  
> [!IMPORTANT]
> HA (고가용성)를 준비 하기 위한 공유 폴더는 PSTN 사이트 별로 동일 합니다. PSTN 사이트 간에 공유 폴더가 달라 **야 합니다** . 여러 사이트에 같은 공유 폴더를 사용 하지 마십시오. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>다중 사이트 배포에 비해 HA (고가용성)가 적용 되는 단일 사이트
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

다음 표에는 단일 사이트에서 HA를 지원 하 고 여러 사이트를 배포할 때의 차이점이 나와 있습니다.
  
|**종류**|**항목**|**HA를 사용한 단일 사이트**|**다중 사이트**|
|:-----|:-----|:-----|:-----|
|구성  <br/> |기기 호스트 이름 <br/> |**여러** 기기에서 다름 <br/> |PSTN 사이트에서 **다름** <br/> |
|설정  <br/> |공유 폴더  <br/> |기기에서 **같은** 공유 폴더 필요 <br/> |여러 기기에서 **다른** 공유 폴더 필요 <br/> |
|구성  <br/> |VirtualMachineDomain  <br/> |모든 기기에 **동일한** 도메인 필요 <br/> |PSTN 사이트에서 **동일한** 도메인 필요 <br/> |
|구성  <br/> |SIPDomains  <br/> |도메인 이름 및 순서는 모든 기기에서 **동일** 해야 함 <br/> |도메인 이름 및 순서는 PSTN 사이트에서 **동일** 해야 합니다. <br/> |
|구성  <br/> |사이트 이름  <br/> |**동일** 기기 간의 사이트 이름 <br/> |**다양** PSTN 사이트 간의 사이트 이름 <br/> |
|구성  <br/> |서버 이름  <br/> |**여러** 기기에서 다름 <br/> |PSTN 사이트에서 **다름** <br/> |
|구성  <br/> |내부 풀 Fqdn  <br/> |여러 기기에서 **동일** <br/> |PSTN 사이트에서 **동일** <br/> |
|구성  <br/> |내부 Ip  <br/> |**여러** 기기에서 다름 <br/> |PSTN 사이트에서 **다름** <br/> |
|구성  <br/> |외부 FQDN  <br/> |여러 기기에서 **동일** <br/> |PSTN 사이트에서 **다름** <br/> |
|구성  <br/> |외부 Ip  <br/> |**여러** 기기에서 다름 <br/> |PSTN 사이트에서 **다름** <br/> |
|구성  <br/> |PSTN GW 설정  <br/> |여러 기기에서 **동일** <br/> |PSTN 사이트에서 **다름** <br/> |
|구성  <br/> |DNS 레코드  <br/> |**동일한** 외부 액세스 fqdn 및 **서로 다른** IP 주소를 사용 하 여 레코드 추가 <br/> |**다른** 외부 액세스 fqdn 및 **서로 다른** IP 주소를 사용 하 여 레코드 추가 <br/> |
|설정  <br/> |하이브리드 테 넌 트  <br/> |Set HybridPSTNSite  <br/> 대체에 대해 PeerDestination 설정  <br/> |Set HybridPSTNSite  <br/> 대체에 대해 PeerDestination 설정  <br/> |
|설정  <br/> |게이트웨이  <br/> |이 사이트의 MS GW **M:n** 매핑 <br/> |각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 해야 합니다.  <br/> |
|설정  <br/> |사용자  <br/> |Set UserPSTNSettings  <br/> |Set UserPSTNSettings  <br/> |
   

