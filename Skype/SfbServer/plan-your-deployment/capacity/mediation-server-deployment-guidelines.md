---
title: 중재 서버의 배포 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 이 항목에서는 중재 서버 배포에 대한 계획 지침을 설명합니다.
ms.openlocfilehash: 1b5f628f544cafb358b58d325c5d077aef783a89
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397622"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>중재 서버의 배포 비즈니스용 Skype 서버
 
이 항목에서는 중재 서버 배포에 대한 계획 지침을 설명합니다.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>함께 사용되거나 독립 실행형 중재 서버인가요?

중재 서버는 기본적으로 중앙 사이트의 프런트 엔드 풀에 Standard Edition 서버 또는 프런트 엔드 서버에 함께 있습니다. 처리할 수 있는 PSTN(Public Switched Telephone Network) 통화 수와 풀에 필요한 컴퓨터 수는 다음에 따라 달라 하게 됩니다.
  
- 중재 서버 풀이 제어하는 게이트웨이 피어 수입니다.
    
- 이러한 게이트웨이를 통한 대량 트래픽 기간입니다.
    
- 미디어가 중재 서버를 우회하는 통화의 백분율입니다.
    
계획할 때 미디어 우회를 지원하지 않는 PSTN 통화 및 A/V 회의에 대한 미디어 처리 요구 사항과 지원해야 하는 통화가 많은 통화 수에 대한 신호 상호 작용을 처리하는 데 필요한 처리를 고려해야 합니다. CPU가 충분하지 않은 경우 독립 실행형 중재 서버 풀을 배포해야 합니다. 또한 PSTN 게이트웨이, IP-PBX 및 SBC는 하나의 풀에 함께 있는 중재 서버에 의해 제어되는 하위 집합과 하나 이상의 독립 실행형 풀에 있는 독립 실행형 중재 서버로 분할해야 합니다.
  
중재 서버 풀과 상호 작용할 수 없는 PSTN 게이트웨이, IP-PBX 또는 SBC(Session Border Controller)를 배포한 경우 단일 중재 서버로 구성된 독립 실행형 풀과 연결해야 합니다. PSTN 게이트웨이, IP-PBXs SBC에 필요한 몇 가지는 다음과 같습니다.
  
- 풀의 중재 서버에서 네트워크 계층 DNS(Domain Name System) 부하 분산을 수행하거나, 그렇지 않으면 트래픽을 풀의 모든 중재 서버로 균일하게 라우팅합니다.
    
- 풀에 있는 중재 서버의 트래픽을 수락합니다.
    
비즈니스용 Skype 계획 도구를 사용하여 중재 서버를 프런트 엔드 풀과 함께 함께 사용하여 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 환경이 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.
  
## <a name="central-site-and-branch-site-considerations"></a>중앙 사이트 및 분기 사이트 고려 사항

 중앙 사이트의 중재 서버는 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 데 사용될 수 있습니다. 그러나 SIP 트렁크를 배포하는 경우 각 트렁크가 종료되는 사이트에 중재 서버를 배포해야 합니다. 중재 서버를 중앙 사이트에 두면 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅할 수 있지만 미디어 우회를 사용할 필요는 없지만 미디어 우회를 사용하는 것이 좋습니다. 미디어 우회를 사용하도록 설정할 수 있는 경우 미디어 경로가 신호 경로를 따를 필요는 아니기 때문에 미디어 경로 대기 시간이 줄어들고 결과적으로 미디어 품질이 향상됩니다. 미디어 바이패스는 풀의 처리 부하도 감소시킵니다.
  
> [!NOTE]
> 미디어 우회는 모든 PSTN 게이트웨이, IP-PBX 및 SBC와 상호 연결되지 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX에 대한 몇 가지 테스트를 수행했습니다. 미디어 우회는 통합 통신 개방형 상호 운영성 프로그램에 나열된 제품 및 버전에서만 지원됩니다. Lync Server(테스트된 장치, 인프라 및 도구 탐색)에서 사용자 환경을 지원하고 확장하는 비즈니스용 Skype [있습니다](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
분기 사이트 복구가 필요한 경우에는 SBA(Survivable Branch Appliance) 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합을 분기 사이트에 배포해야 합니다. 분기 사이트 탄력성의 경우 현재 상태 및 회의가 사이트에서 탄력적이지 않다고 가정합니다. 음성에 대한 분기 사이트 계획에 대한 지침은 [Plan for Enterprise Voice resiliency in 비즈니스용 Skype 서버](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
IP-PBX와의 상호 작용의 경우 IP-PBX가 여러 초기 대화 및 RFC 3960 상호 작용과의 초기 미디어 상호 작용을 올바르게 지원하지 않는 경우 IP-PBX에서 Lync 끝점으로의 수신 전화에 대해 인사말의 처음 몇 단어를 잘라 내야 할 수 있습니다. 중앙 사이트의 중재 서버가 신호가 완료되는 데 더 많은 시간이 필요하기 때문에 경로가 분기 사이트에서 종료되는 IP-PBX에 대한 통화를 라우팅하는 경우 이 동작이 더 심각할 수 있습니다. 이 동작이 경험하는 경우 분기 사이트에 중재 서버를 배포하는 것만이 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.
  
끝으로, 중앙 사이트에 TDM PBX가 있거나, IP-PBX가 PSTN 게이트웨이의 필요성을 해소하지 못한 경우 통화 경로에 중재 서버와 PBX를 연결하는 게이트웨이를 배포해야 합니다.
  
> [!NOTE]
> 독립 실행형 중재 서버의 미디어 성능을 향상하려면 이러한 서버의 네트워크 어댑터에서 RSS(수신 쪽 크기 조정)를 사용하도록 설정해야 합니다. RSS를 사용하면 들어오는 패킷을 서버의 여러 프로세서에서 병렬로 처리할 수 있습니다. 자세한 내용은 "Windows 서버의 수신[측 확장 기능](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))"을 참조합니다. RSS를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 어댑터 설명서를 참조하십시오. 
