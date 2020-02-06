---
title: 비즈니스용 Skype 서버의 중재 서버 배포 지침
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 이 항목에서는 중재 서버 배포에 대 한 계획 지침을 설명 합니다.
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816057"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 중재 서버 배포 지침
 
이 항목에서는 중재 서버 배포에 대 한 계획 지침을 설명 합니다.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated 또는 독립 실행형 중재 서버

중재 서버는 기본적으로 중앙 사이트의 프런트 엔드 풀에 있는 Standard Edition Server 또는 프런트 엔드 서버에서 collocated. 처리할 수 있는 PSTN (공개 통신 네트워크) 및 풀에 필요한 컴퓨터 수에 따라 다음이 달라 집니다.
  
- 중재 서버 풀 컨트롤이 제어 하는 게이트웨이 피어 수입니다.
    
- 이러한 게이트웨이를 통한 대용량 트래픽 기간
    
- 미디어에서 중재 서버를 우회 하는 통화의 백분율입니다.
    
계획 하 고 있는 경우에는 PSTN 통화에 대 한 미디어 처리 요구 사항과 미디어 바이패스를 지원 하지 않는 A/V 회의를 고려해 야 하며 지원 해야 하는 사용 중인 통화 시간에 대 한 신호 상호 작용을 처리 하는 데 필요한 처리 과정을 고려 하세요. CPU가 충분 하지 않으면 중재 서버의 독립 실행형 풀을 배포 해야 합니다. 또한 PSTN 게이트웨이, IP-Pbx, SBCs는 하나의 풀에 있는 collocated 중재 서버에서 제어 하는 하위 집합으로 분할 해야 하며 하나 이상의 독립 실행형 풀에는 독립 실행형 중재 서버 여야 합니다.
  
조정 서버 풀과 상호 작용 하는 기능이 없는 PSTN 게이트웨이, IP-Pbx 또는 SBCs (세션 경계 컨트롤러)를 배포한 경우 단일 중재 서버로 구성 된 독립 실행형 풀에 연결 해야 합니다. PSTN 게이트웨이, IP Pbx 또는 SBCs가 수행 해야 하는 작업은 다음과 같습니다.
  
- 풀의 중재 서버에서 네트워크 레이어 DNS (Domain Name System) 로드 균형 조정을 수행 하거나 풀의 모든 중재 서버에 트래픽을 균일 하 게 라우팅 합니다.
    
- 풀의 중재 서버에서 트래픽을 허용 합니다.
    
비즈니스용 Skype 계획 도구를 사용 하 여 collocating가 프런트 엔드 풀을 사용 하는 중재 서버가 로드를 처리할 수 있는지 평가할 수 있습니다. 환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.
  
## <a name="central-site-and-branch-site-considerations"></a>중앙 사이트 및 지점 사이트 고려 사항

 중앙 사이트의 중재 서버를 사용 하 여 지점 사이트에서 IP Pbx 또는 PSTN 게이트웨이에 대 한 통화를 라우팅할 수 있습니다. 그러나 SIP trunks를 배포 하는 경우 각 트렁크가 종료 되는 사이트에 중재 서버를 배포 해야 합니다. 중앙 사이트에서 지점 사이트 경로에 대 한 중재 서버를 보유 하는 경우에는 미디어 바이패스를 사용 하지 않아도 되지만 미디어 우회는 권장 됩니다. 이는 미디어 바이패스를 사용 하도록 설정할 수 있는 경우 미디어 경로 대기 시간을 줄이며, 결과적으로 미디어 경로가 신호 경로를 따르지 않아도 되므로 미디어 품질이 향상 됨을 의미 합니다. 미디어 바이패스는 또한 풀의 처리 로드를 줄입니다.
  
> [!NOTE]
> 미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다. 미디어 바이패스는 [비즈니스용 Skype 환경을 지원 하 고 확장 하는 테스트를 거친 장치, 인프라, 도구](http://partnersolutions.skypeforbusiness.com/solutionscatalog)에 대 한 통합 커뮤니케이션 오픈 상호 운용성 프로그램에 나열 된 제품 및 버전 에서만 지원 됩니다. 
  
지점 사이트의 복원성이 필요한 경우 Survivable Branch 기기 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합이 지점 사이트에 배포 되어야 합니다. 지점 사이트 복원에 대 한 전제 하에는 현재 상태와 회의가 사이트에 탄력적으로 포함 되어 있지 않습니다. 음성에 대 한 지점 사이트 계획에 대 한 지침은 비즈니스용 [Skype 서버에서 엔터프라이즈 음성 복원 계획](../enterprise-voice-solution/enterprise-voice-resiliency.md)을 참조 하세요.
  
Ip pbx와의 상호 작용을 위해 IP-PBX가 여러 초기 대화 및 RFC 3960 상호 작용을 통해 초기 미디어 조작을 올바르게 지원 하지 않는 경우에는 IP PBX에서 Lync 끝점으로 들어오는 통화에 대 한 인사말의 처음 몇 단어를 클리핑 하 게 될 수 있습니다. 중앙 사이트의 중재 서버가 지점 사이트에서 경로가 종료 되는 IP PBX에 대 한 라우팅 호출을 수행 하는 경우, 알림을 보내는 데 시간이 더 필요 하기 때문에 더욱 심각한 문제가 될 수 있습니다. 이 동작이 발생 하는 경우 분기 사이트에서 중재 서버를 배포 하는 것이 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.
  
마지막으로, 중앙 사이트에 TDM PBX가 있거나 IP PBX가 PSTN 게이트웨이를 필요로 하지 않는 경우에는 중재 서버와 PBX를 연결 하는 call 경로에 게이트웨이를 배포 해야 합니다.
  
> [!NOTE]
> 독립 실행형 중재 서버의 미디어 성능을 향상 시키려면 이러한 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은[Windows Server에서 "수신측 스케일링 개선 기능](https://go.microsoft.com/fwlink/p/?LinkId=268731)"을 참조 하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요. 
  

