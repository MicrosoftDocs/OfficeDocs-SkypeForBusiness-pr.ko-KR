---
title: 클라우드 커넥터에 여러 사이트 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 클라우드 커넥터 에디션에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.
ms.openlocfilehash: ba6b76366b65a9febb9fab06e7cfb0fad759e5ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190848"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>클라우드 커넥터에 여러 사이트 배포
 
클라우드 커넥터 에디션에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.
  
이 섹션에서는 여러 PSTN (공개 교환 전화 네트워크) 사이트를 배포 하는 방법을 설명 합니다. 사이트는 단일 사이트 배포와 동일한 단계를 사용 하 여 한 번에 하나씩 배포 됩니다. 이 항목에서는 여러 사이트 배포의 사이트 간 고려 사항 및 차이점에 대해 설명 합니다. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>여러 PSTN (공개 교환 전화 네트워크) 사이트

다음은 다양 한 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 예제 구성을 보여 줍니다. 배포를 시작 하기 전에 구성 설정이 올바른지 확인 하세요.
  
PSTN 사이트 1
  
```
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
  
```
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

추가 하려는 각 PSTN 사이트에 대해 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md)의 단계를 따르세요.
  
> [!IMPORTANT]
> HA (고가용성)를 준비 하는 공유 폴더는 PSTN 사이트 별로입니다. 공유 폴더는 PSTN 사이트 간에 달라 **야 합니다** . 여러 사이트에 같은 공유 폴더를 사용 하지 마세요. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>멀티 사이트 배포에 비해 HA (고가용성)가 포함 된 단일 사이트
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

다음 표에는 HA 지원과 다중 사이트 배포의 단일 사이트 간 차이점이 나와 있습니다.
  
|**범주만**|**항목과**|**HA를 사용 하는 단일 사이트**|**다중 사이트**|
|:-----|:-----|:-----|:-----|
|구성할  <br/> |기기 호스트 이름 <br/> |가전 기기에서 **다름** <br/> |PSTN 사이트에서 **다름** <br/> |
|Setup.exe  <br/> |공유 폴더  <br/> |기기에서 **같은** 공유 폴더 필요 <br/> |기기 간에 **다른** 공유 폴더가 필요 합니다. <br/> |
|구성할  <br/> |VirtualMachineDomain  <br/> |모든 기기에 **같은** 도메인이 필요 합니다. <br/> |PSTN 사이트에서 **같은** 도메인이 필요 합니다. <br/> |
|구성할  <br/> |SIPDomains  <br/> |도메인 이름 및 주문은 기기에서 **동일** 해야 합니다. <br/> |도메인 이름 및 주문은 PSTN 사이트에서 **동일** 해야 합니다. <br/> |
|구성할  <br/> |사이트 이름  <br/> |**같은** 기기 간의 사이트 이름 <br/> |**다른** PSTN 사이트 간 사이트 이름 <br/> |
|구성할  <br/> |서버 이름  <br/> |가전 기기에서 **다름** <br/> |PSTN 사이트에서 **다름** <br/> |
|구성할  <br/> |내부 풀 Fqdn  <br/> |기기에서 **동일** 하 게 <br/> |PSTN 사이트에서 **동일** <br/> |
|구성할  <br/> |내부 Ip  <br/> |가전 기기에서 **다름** <br/> |PSTN 사이트에서 **다름** <br/> |
|구성할  <br/> |외부 FQDN  <br/> |기기에서 **동일** 하 게 <br/> |PSTN 사이트에서 **다름** <br/> |
|구성할  <br/> |외부 Ip  <br/> |가전 기기에서 **다름** <br/> |PSTN 사이트에서 **다름** <br/> |
|구성할  <br/> |PSTN GW 설정  <br/> |기기에서 **동일** 하 게 <br/> |PSTN 사이트에서 **다름** <br/> |
|구성할  <br/> |DNS 레코드  <br/> |**동일한** 외부 액세스 fqdn 및 **다른** IP 주소를 사용 하 여 레코드 추가 <br/> |**다른** 외부 액세스 fqdn 및 **다른** IP 주소를 사용 하 여 레코드 추가 <br/> |
|Setup.exe  <br/> |하이브리드 테 넌 트  <br/> |Set HybridPSTNSite  <br/> Fallback에 대 한 PeerDestination 설정  <br/> |Set HybridPSTNSite  <br/> Fallback에 대 한 PeerDestination 설정  <br/> |
|Setup.exe  <br/> |게이트웨이와  <br/> |이 사이트의 MS GW **M:n** 매핑 <br/> |각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 되어야 합니다.  <br/> |
|Setup.exe  <br/> |클릭할  <br/> |Set UserPSTNSettings  <br/> |Set UserPSTNSettings  <br/> |
   

