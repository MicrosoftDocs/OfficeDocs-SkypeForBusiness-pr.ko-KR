---
title: 에 대한 참조 토폴로지 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 대규모, 중간 규모 및 소규모 비즈니스용 Skype 서버 대한 다이어그램 및 결정을 포함하여 조직의 참조 토폴로지
ms.openlocfilehash: fbc80ddda4a7f208489661e431f83b30d77aea0556a2a21c21144dd437fb4e01
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349890"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>에 대한 참조 토폴로지 비즈니스용 Skype 서버

대규모, 중간 규모 및 소규모 비즈니스용 Skype 서버 대한 다이어그램 및 결정을 포함하여 조직의 참조 토폴로지

가장 적합한 비즈니스용 Skype 서버 토폴로지는 조직의 규모, 배포하려는 작업량 및 고가용성에 대한 기본 설정과 투자 비용에 따라 달라집니다.

이 섹션에서는 각 토폴로지의 여러 가지 결정에 대한 이유를 포함하여 세 가지 예제 참조 토폴로지에 대해 간략하게 설명합니다.

## <a name="reference-topology-for-a-small-organization"></a>소규모 조직에 대한 참조 토폴로지

소규모 조직을 위한 참조 토폴로지에서는 3대의 서버만 배포하여 강력한 고가용성 솔루션을 배포하는 방법을 보여 비즈니스용 Skype 서버.

**소규모 조직을 위한 참조 토폴로지**

![세 개의 서버 다이어그램을 배포하는 참조 토폴로지](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **배포된 Standard Edition 서버 쌍** 이 조직에는 중앙 사이트에 사용자가 4,000명 있습니다. 이러한 서버는 두 개의 Standard Edition 배포한 후 함께 쌍을 이루어 고가용성 및 재해 복구를 가능하게 합니다. 각 서버는 2,000명이 사용자를 저장하지만 모든 사용자에 대한 정보는 두 서버 간에 동기화됩니다. 한 사용자가 다운되는 경우 관리자는 해당 사용자를 장애 조치(fail over)하여 다른 서버에서 서비스를 제공하면 사용자에게 최소한의 방해가 될 수 있습니다. 비즈니스용 Skype 서버 고가용성 및 재해 복구 기능에 대한 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **에지 서버 배포 권장.** 내부 IM, 현재 상태 및 회의에는 에지 서버를 배포하지 않아도 되지만 소규모 배포에도 에지 서버를 배포하는 것이 좋습니다. 에지 비즈니스용 Skype 서버 배포하여 현재 조직의 방화벽 외부에 있는 사용자에게 서비스를 제공하면 조직의 투자를 최대화할 수 있습니다. 이점은 다음과 같습니다.

  - 조직 자체 사용자는 집에서 비즈니스용 Skype 서버 외출하는 경우 이러한 기능을 사용할 수 있습니다.

  - 사용자가 외부 사용자를 모임에 초대할 수 있습니다.

  - 파트너, 공급업체 또는 고객 조직도 비즈니스용 Skype 서버 해당 조직과의 페더전 관계를 형성할 수 있습니다. 그러면 비즈니스용 Skype 서버 페더레이션 조직의 사용자를 인식하여 공동 작업을 향상할 수 있습니다.

  - 사용자는 일부 공용 IM 서비스의 사용자와 인스턴트 메시지를 교환할 수 있습니다.

- **분기 사이트 지속 가능성.** 이 조직은 조직의 Enterprise Voice 기능의 파일럿 비즈니스용 Skype 서버. 일부 사용자는 단독 비즈니스용 Skype 서버 솔루션으로 사용할 수 있습니다. 이러한 Enterprise Voice 파일럿 사용자는 분기 사이트에 있습니다. 분기 사이트에는 중앙 사이트에 대한 안정적인 WAN(Wide Area Network) 링크가 없습니다. 따라서 SSS(Survivable Branch Appliance)가 배포됩니다. 이 배포를 통해 WAN 링크가 다운된 경우 분기 사이트의 사용자는 계속 전화를 걸고 받을 수 있습니다(조직 내의 통화와 PSTN 통화 모두), 음성 메일 기능을 가지며, 두 사용자간 IM(인스턴트 메시징)과 통신할 수 있습니다. 또한 WAN 링크를 사용할 수 없는 경우에도 사용자가 인증을 받을 수 있습니다. 자세한 내용은 [Plan for Enterprise Voice resiliency in 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **Exchange UM 배포** 이 참조 토폴로지에는 UM(Exchange) 서버가 포함되어 Microsoft Exchange Server 실행되지 비즈니스용 Skype 서버.

- **Office Web Apps 서버.** 웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. Office 웹앱 서버를 사용하면 웹 회의에 PowerPoint 수 있습니다.

## <a name="reference-topology-for-a-medium-organization"></a>중간 규모 조직에 대한 참조 토폴로지

고가용성을 지원하고 단일 데이터 센터를 사용하는 참조 토폴로지는 하나의 중앙 사이트가 있는 중소 규모 조직용으로 설계되었습니다. 다음 다이어그램의 토폴로지가 사용자 수가 20,000명인 조직에 대한 토폴로지입니다.

**중간 규모 조직에 대한 참조 토폴로지**

![단일 데이터 센터 다이어그램에 대한 참조 토폴로지](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **프런트 엔드 서버를 더 추가하여 더 많은 사용자를 수용합니다.** 이 다이어그램의 정확한 토폴로지에는 20,000명 사용자에게 지원을 제공하는 세 개의 프런트 엔드 서버가 있습니다. 단일 중앙 사이트와 더 많은 사용자가 있는 경우 풀에 프런트 엔드 서버를 더 추가할 수 있습니다. 풀당 최대 사용자 수는 80,000명(프런트 엔드 서버 12대)입니다.

    그러나 단일 사이트 토폴로지에서는 사이트에 다른 프런트 엔드 풀을 추가하여 훨씬 더 많은 사용자를 지원할 수 있습니다.

- **재해 복구를 추가할 수 있습니다.** 이 조직의 경우 비즈니스용 Skype 서버 서비스의 고가용성은 필수 기능이지만 재해 복구는 필요하지 않습니다. 배포한 프런트 엔드 서버 풀은 고가용성을 제공합니다.

    재해 복구 기능을 추가하기를 원할 경우 다른 데이터 센터를 설정하고 다른 프런트 엔드 풀을 추가한 다음 현재 데이터 센터의 프런트 엔드 풀과 페어링하는 것을 고려할 수 있습니다. 그런 다음 기본 풀에 영향을 주는 재해가 발생하면 관리자가 사용자를 백업 풀로 장애 조치(fail over)할 수 있습니다.

- **백 엔드 서버가 미러링됩니다.** 기본 사용자 기능에 대한 고가용성을 제공하기 위해 조직은 각 프런트 엔드 풀에 대해 미러된 백 엔드 서버 쌍을 배포했습니다.

- **모니터링 서버 데이터베이스 옵션** 이 조직은 통화 및 A/V 회의의 품질을 Enterprise Voice 모니터링을 배포했습니다. 모니터링은 모든 프런트 엔드 서버에 배포됩니다. 모니터링 데이터베이스는 백 엔드 서버와 함께 배치됩니다. 모니터링 데이터베이스가 별도의 서버에 있는 토폴로지도 지원됩니다.

- **에지 서버 고가용성** 이 예제에서는 사용자가 20,000명인 조직에서는 하나의 에지 서버만 성능에 충분합니다. 그러나 고가용성을 제공하기 위해 배포된 두 개의 에지 서버 풀을 배포했습니다.

- **분기 사이트 배포 옵션** 이 토폴로지의 조직은 음성 Enterprise Voice 배포되지 않습니다. 분기 사이트 1에는 중앙 사이트에 대한 탄력적인 WAN(Wide Area Network) 링크가 없습니다. 따라서 중앙 사이트에 대한 WAN 링크가 다운되는 경우를 위해 많은 비즈니스용 Skype 서버 기능을 유지 관리하기 위해 SSI(Survivable Branch Appliance)가 배포되어 있습니다. 그러나 분기 사이트 2에는 탄력적인 WAN 링크가 있으므로 PSTN(Public Switched Telephone Network) 게이트웨이만 필요합니다. 배포된 PSTN 게이트웨이는 미디어 우회를 지원하기 때문에 분기 사이트 2에는 중재 서버가 필요하지 않습니다. 자세한 내용은 [Plan for Enterprise Voice resiliency in 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **DNS 부하 분산**   프런트 엔드 풀, 에지 서버 풀 및 디렉터 풀에는 배포된 SIP 트래픽에 대한 DNS 부하 분산이 적용됩니다. 프런트 엔드 풀 및 에지 서버 풀에는 SIP 트래픽에 대한 DNS 부하 분산이 배포됩니다. 하드웨어 부하 분산 장치는 HTTP 트래픽에만 필요하기 때문입니다. 자세한 내용은 DNS 부하 [분산을 참조하세요.](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)

- **Exchange UM 배포** 이 참조 토폴로지에는 UM(Exchange) 서버가 포함되어 Microsoft Exchange Server 실행되지 비즈니스용 Skype 서버.

- **Office Web Apps 서버.** 웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. Office Web Apps 서버를 사용하면 웹 회의에서 Powerpoint 슬라이드를 제시할 수 있습니다.

- **디렉터 추가 가능.** 이 조직이 서비스 거부 공격에 대한 보안을 강화할 수 있도록 돕고자 하는 경우 이 조직은 또한 이사 풀을 배포할 수 있습니다. Director는 사용자 계정을 비즈니스용 Skype 서버 또는 현재 상태 또는 회의 서비스를 제공하지 않는 별도의 선택적 서버 역할입니다. 이 서버는 에지 서버가 내부 서버로 전송되는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버 역할을 합니다. 감독은 인바운드 요청을 미리 인증하고 사용자의 홈 풀 또는 서버로 리디렉션합니다. 디렉터에서의 사전 인증을 통해 배포에 알려지지 않은 사용자 계정에서 오는 요청을 끊을 수 있습니다. 감독은 DoS(서비스 거부) 공격과 같은 악의적인 트래픽으로부터 프런트 엔드 서버를 보호합니다. 네트워크가 이러한 공격에서 잘못된 외부 트래픽으로 넘쳐나면 트래픽은 감독에서 종료됩니다.

- **System Center Operations Manager를 권장합니다.** 최종 사용자의 서비스 가용성을 보장하기 위해 비즈니스용 Skype 서버 배포의 상태는 모니터링하는 것이 좋습니다. Microsoft에서 무료로 System Center 사용할 수 있는 비즈니스용 Skype Operations Manager 관리 팩을 사용할 수 있습니다. 비즈니스용 Skype 관리 팩을 사용하면 문제가 발생할 때 실시간 경고를 사전 예방적으로 받을 수 있으며 가상 트랜잭션을 실행하여 종단 비즈니스용 Skype 기능을 테스트하고, 서비스 가용성에 대한 보고서를 받을 수 있습니다. 이를 통해 최종 사용자가 문제를 경험하기 전에 배포에 대한 문제를 미리 해결할 수 있습니다.

## <a name="reference-topology-for-a-large-organization"></a>대규모 조직에 대한 참조 토폴로지

여러 데이터 센터를 지원하는 대규모 조직용 참조 토폴로지는 둘 이상의 중앙 사이트가 있는 모든 규모의 조직에 적합합니다. 다음 다이어그램은 사용자 수가 50,000명(중앙 사이트 A에 20,000명, 중앙 사이트 B에 20,000명, 중앙 사이트 C와 분기 사이트에 총 10,000명)인 조직의 토폴로지입니다. 이 다이어그램에 표시된 유형의 토폴로지는 사용자 수에 관계없이 모든 규모의 조직에 적용될 수 있습니다.

이 토폴로지에서는 프런트 엔드 서버 풀에서 제공하는 고가용성 외에도 재해 복구 지원을 추가합니다. 중앙 사이트 A와 B의 프런트 엔드 풀은 함께 쌍으로 됩니다. 이러한 풀 중 하나가 다운될 경우 관리자는 영향을 받지 않은 사이트의 쌍으로 구성된 풀로 영향을 받은 사용자에 대한 서비스를 이동할 수 있습니다.

이 토폴로지는 여러 다이어그램으로 표시되어 있는데, 먼저 개요를 보여 준 다음 중앙 사이트에 대한 상세 보기를 제공합니다.

**여러 데이터 센터가 있는 대규모 조직용 참조 토폴로지의 개요**

![여러 데이터 센터에 대한 참조 토폴로지](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**대규모 조직용 참조 토폴로지: 중앙 사이트 A의 상세 보기**

![토폴로지 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**대규모 조직용 참조 토폴로지: 중앙 사이트 B의 상세 보기**

![토폴로지 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**대규모 조직용 참조 토폴로지: 중앙 사이트 C의 상세 보기**

![토폴로지 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **프런트 엔드 풀이 페어링되어 재해 복구를 사용하도록 설정됩니다.** 사이트 A와 사이트 B의 프런트 엔드 풀은 서로 쌍으로 사용 하여 재해 복구 지원을 제공합니다. 한 사이트의 풀에 오류가 발생하면 관리자가 해당 사이트의 사용자를 다른 사이트의 페어링된 프런트 엔드 풀로 장애 조치(fail over)할 수 있으며, 최소한 사용자의 서비스가 중단될 수 있습니다. 이러한 두 프런트 엔드 풀에는 각각 6개의 서버가 있어 장애 조치(failover) 시 두 풀에 있는 40,000명의 사용자 모두를 충분히 지원할 수 있습니다. 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **백 엔드 서버가 미러링됩니다.** 기본 사용자 기능에 대한 고가용성을 제공하기 위해 조직은 각 프런트 엔드 풀에 대해 미러된 백 엔드 서버 쌍을 배포했습니다. 이는 선택적 토폴로지이며 대신 단일 백 엔드 서버를 배포할 수 있습니다. SQL 및 AlwaysOn 가용성 그룹도 지원됩니다. 자세한 내용은 에서 [백 엔드 서버 고가용성을 비즈니스용 Skype 서버.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

- **분기 Standard Edition 서버 사용** 이 조직에서는 직원 수가 600명 뿐이기 때문에 사이트 C를 분기 사이트로 고려합니다. 그러나 사용자에게는 여러 A/V 회의가 있습니다. 분기 비즈니스용 Skype 서버 배포된 경우 이러한 회의에 대한 미디어는 프런트 엔드 서버가 배포된 중앙 사이트와 WAN(광역 네트워크)을 통해 실행됩니다. 이러한 잠재적인 대역폭 부하를 방지하기 위해 이 사이트에 이러한 회의를 호스팅할 Standard Edition 서버 쌍을 설치했습니다. 또한 Standard Edition 서버가 설치되어 있기 때문에 비즈니스용 Skype 서버 정의에 따라 이 서버는 중앙 사이트로 간주하며 토폴로지 작성기 및 계획 도구에서와 같이 처리됩니다.

    여기서는 Standard Edition 서버 하나만 성능에 충분하지만, 조직에서는 한 서버가 다운될 경우 고가용성을 제공하기 위해 두 서버를 배포하고 쌍으로 연결했습니다.

    사이트 C가 중앙 사이트로 간주되지만 여기에 에지 서버를 배포할 필요는 없습니다. 이 예에서는 사이트 C에서 사이트 A에 배포된 에지 서버를 사용합니다.

- **모니터링 및 보관** 이 조직은 모니터링 및 보관을 둘 다 배포했습니다. 모니터링 또는 보관을 배포하면 모든 프런트 엔드 서버에서 실행됩니다. 이러한 기능의 데이터베이스는 백 엔드 데이터베이스와 함께 또는 별도의 서버에 위치할 수 있습니다. 이 조직은 이러한 데이터베이스를 중앙 사이트 B의 백 엔드 서버와는 별개인 서버에 위치했습니다. 이 데이터베이스는 모든 사이트의 프런트 엔드 서버에서 모니터링 및 보관 데이터를 수신합니다.

- **분기 사이트 배포 옵션** 이 조직에는 실제로 50개가 넘는 분기 사이트가 있습니다. 이 중 2개만 자세한 다이어그램에 표시됩니다. 분기 사이트 1에는 중앙 사이트에 대한 탄력적인 WAN 링크가 없습니다. 따라서 중앙 사이트에 대한 WAN 링크가 다운될 경우 전화 서비스를 제공하기 위해 Survivable Branch Appliance가 배포됩니다. 그러나 분기 사이트 2에는 탄력적인 WAN 링크가 있으므로 PSTN(Public Switched Telephone Network) 게이트웨이만 필요합니다. 배포된 PSTN 게이트웨이는 미디어 우회를 지원하기 때문에 분기 사이트 2에는 중재 서버가 필요하지 않습니다. 분기 사이트에서 설치할 설치를 결정하는 데 대한 자세한 내용은 [Plan for Enterprise Voice resiliency in 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **SIP 트렁크와 중재 서버.** 중앙 사이트 B에는 중재 서버가 프런트 엔드 서버와 함께 배치되어 있지 않습니다. 이는 SIP 트렁크를 사용하는 사이트에는 독립 실행형 중재 서버가 권장되기 때문입니다. 그 밖의 경우에는 대부분 중재 서버를 프런트 엔드 서버와 함께 배치하는 것이 좋습니다. 중재 서버 토폴로지에 대한 자세한 내용은 계획 설명서에서 [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server)를 참조하십시오.

- **영구 채팅이 배포됩니다.** 이 조직은 영구 채팅을 사용하도록 설정하는 데 필요한 서버를 배포했습니다. 풀의 사용자 수에 대한 부하를 처리하고 고가용성을 제공하기 위해 여러 영구 채팅 프런트 엔드 서버를 배포했습니다. 또한 영구 채팅에 대한 준수를 배포하고, 영구 채팅 저장소 및 영구 채팅 준수 저장소를 별도의 서버에 배치했습니다. 이러한 저장소는 함께 함께 사용할 수 있으며 백 엔드 서버와 함께 함께 사용할 수도 있지만 이 조직에서는 더 나은 성능을 제공하기 위해 이러한 저장소를 분리하기로 선택했습니다.

    > [!NOTE]
    > 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.

- **DNS 부하 분산**   프런트 엔드 풀, 에지 서버 풀 및 디렉터 풀에는 배포된 SIP 트래픽에 대한 DNS 부하 분산이 적용됩니다. 프런트 엔드 풀 및 에지 서버 풀은 DNS 부하 분산을 사용 합니다. 이렇게 하면 에지 서버의 내부 인터페이스에 대한 하드웨어 부하 균형 조정이 필요하지 않습니다. 또한 하드웨어 부하 균형 조정은 HTTP 트래픽에만 필요하기 때문에 다른 풀에 대한 하드웨어 부하 균형 조정 기능을 설정하고 유지 관리하는 데 필요한 시간을 크게 줄입니다. 자세한 내용은 (.)를 참조하세요. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM 배포** 비즈니스용 Skype 서버 UM(통합 메시징) 및 Exchange UM의 Exchange 작동합니다. 중앙 사이트 A에는 UM(Exchange) 서버가 포함되어 Microsoft Exchange Server 실행되지 비즈니스용 Skype 서버. 프런트 엔드 Exchange UM 비즈니스용 Skype 서버 프런트 엔드 풀에서 실행됩니다.

    중앙 사이트 B에서는 호스팅된 Exchange를 사용하므로 Exchange UM 서버 기능도 호스팅됩니다.

    UM의 Exchange 대한 자세한 내용은 계획 설명서에서 [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) 및 [Hosted Exchange Unified Messaging Integration을](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration) 참조하십시오.

- **Office Web Apps 서버.** 웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. 단일 Office Web Apps Server 팜을 한 사이트에 배포하여 모든 사이트의 트래픽을 처리할 수도 있고 각 사이트에 배포할 수도 있습니다. Office Web Apps 서버를 사용하면 웹 회의에서 Powerpoint 슬라이드를 제시할 수 있습니다.

- **디렉터 추가 가능.** 이 조직에서 서비스 거부 공격에 대한 보안을 강화하려는 경우 디렉터 풀 하나를 배포할 수 있습니다. Director는 사용자 계정을 비즈니스용 Skype 서버 또는 현재 상태 또는 회의 서비스를 제공하지 않는 별도의 선택적 서버 역할입니다. 이 서버는 에지 서버가 내부 서버로 전송되는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버 역할을 합니다. 감독은 인바운드 요청을 미리 인증하고 사용자의 홈 풀 또는 서버로 리디렉션합니다. 디렉터에서의 사전 인증을 통해 배포에 알려지지 않은 사용자 계정에서 오는 요청을 끊을 수 있습니다. 감독은 DoS(서비스 거부) 공격과 같은 악의적인 트래픽으로부터 프런트 엔드 서버를 보호합니다. 네트워크가 이러한 공격에서 잘못된 외부 트래픽으로 넘쳐나면 트래픽은 감독에서 종료됩니다.

- **System Center Operations Manager를 권장합니다.** 최종 사용자의 서비스 가용성을 보장하기 위해 비즈니스용 Skype 서버 배포의 상태는 모니터링하는 것이 좋습니다. Microsoft에서 무료로 System Center 사용할 수 있는 비즈니스용 Skype Operations Manager 관리 팩을 사용할 수 있습니다. 비즈니스용 Skype 관리 팩을 사용하면 문제가 발생할 때 실시간 경고를 사전 예방적으로 받을 수 있으며 가상 트랜잭션을 실행하여 종단 비즈니스용 Skype 기능을 테스트하고, 서비스 가용성에 대한 보고서를 받을 수 있습니다. 이를 통해 최종 사용자가 문제를 경험하기 전에 배포에 대한 문제를 미리 해결할 수 있습니다.