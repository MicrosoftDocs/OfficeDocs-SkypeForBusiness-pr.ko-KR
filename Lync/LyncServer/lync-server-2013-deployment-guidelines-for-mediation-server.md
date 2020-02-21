---
title: 'Lync Server 2013: 중재 서버에 대 한 배포 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcbfec56f4cfee3def2a0ef6deb82934534dbb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013의 중재 서버 배포 지침

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-12_

이 항목에서는 중재 서버 배포에 대 한 계획 지침에 대해 설명 합니다. 이러한 지침을 검토 한 후 계획 도구를 사용 하 여 배포를 결정 하는 최종 맞춤형 토폴로지의 모델로 사용할 수 있는 가능한 대체 토폴로지를 만들고 확인 하는 것이 좋습니다.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>배치 된 또는 독립 실행형 중재 서버

중재 서버는 기본적으로 중앙 사이트 프런트 엔드 풀의 Standard Edition Server 또는 프런트 엔드 서버에 배치됩니다. 처리할 수 있는 PSTN (공중 전화망) 통화 수 및 풀에 필요한 컴퓨터 수는 다음에 따라 달라 집니다.

  - 중재 서버 풀에서 제어 하는 게이트웨이 피어 수

  - 이러한 게이트웨이를 통한 고용량 트래픽 기간

  - 해당 미디어에서 중재 서버를 바이패스 하는 통화의 비율입니다.

계획할 때는 PSTN 통화에 대 한 미디어 처리 요구 사항과 미디어 바이패스를 위해 구성 되지 않은 A/V 회의 및 지원 해야 하는 사용량이 많은 시간에 대 한 신호 상호 작용을 처리 하는 데 필요한 처리를 고려해 야 합니다. CPU가 충분 하지 않으면 중재 서버의 독립 실행형 풀을 배포 해야 합니다. 및 PSTN 게이트웨이, IP-Pbx 및 자회사는 하나의 풀에 있는 배치 된 중재 서버 및 하나 이상의 독립 실행형 풀에 독립 실행형 중재 서버에 의해 제어 되는 하위 집합으로 분할 해야 합니다.

다음을 포함 하 여 중재 서버 풀과 상호 작용 하기 위한 올바른 기능을 지원 하지 않는 PSTN 게이트웨이, IP-PBX 또는 sbc (Session Border Controller)를 배포한 경우에는이를 구성 하는 독립 실행형 풀에 연결 해야 합니다. 단일 중재 서버의 경우:

  - 풀의 중재 서버 간에 네트워크 계층 DNS (Domain Name System) 부하 분산을 수행 합니다 (또는 풀의 모든 중재 서버에 트래픽을 균일 하 게 라우팅하는 경우).

  - 풀에 있는 중재 서버의 트래픽 허용

Microsoft Lync Server 2013, 계획 도구를 사용 하 여 배치 중재 서버가 프런트 엔드 풀과의 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>중앙 사이트 및 분기 사이트 고려 사항

중앙 사이트의 중재 서버는 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 데 사용될 수 있습니다. 그러나 SIP 트렁크를 배포한 경우에는 각 트렁크가 종료되는 사이트에 중재 서버를 배포해야 합니다. 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 중재 서버를 중앙 사이트에 배포한 경우에는 미디어 바이패스를 사용할 필요가 없습니다. 하지만 미디어 바이패스를 사용하도록 설정할 수 있는 경우 미디어 바이패스를 사용하면 미디어 경로가 더 이상 신호 경로를 따를 필요가 없어 미디어 경로 대기 시간이 줄어들므로 미디어 품질이 향상됩니다. 미디어 바이패스는 풀의 처리 부하도 감소시킵니다.

<div>


> [!NOTE]  
> 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>나열 된 제품 및 버전 에서만 지원 됩니다.



</div>

분기 사이트 복구가 필요한 경우에는 SBA(Survivable Branch Appliance) 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합을 분기 사이트에 배포해야 합니다. 분기 사이트 복구에 대 한 가정에는 현재 상태 및 회의가 사이트에서 탄력적으로 발생 하지 않는다는 것입니다. 음성에 대 한 분기 사이트 계획에 대 한 지침은 [Lync Server 2013에서 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.

Ip-https와 상호 작용 하는 경우, IP-PBX가 여러 초기 대화 및 RFC 3960 상호 작용과 함께 초기 미디어 상호 작용을 올바르게 지원 하지 않으면 IP-PBX에서 Lync 끝점으로 들어오는 호출에 대해 인사말의 처음 몇 단어를 클리핑 해야 할 수 있습니다. 중앙 사이트의 중재 서버가 지점 사이트에서 경로가 종료 되는 IP PBX에 대 한 호출을 라우팅하는 경우, 신호가 완료 되는 데 더 많은 시간이 필요 하기 때문에이 동작이 더 심각 해질 수 있습니다. 이 문제가 발생 하는 경우 분기 사이트에 중재 서버를 배포 하는 것은 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.

끝으로, 중앙 사이트에 TDM PBX가 있거나, IP-PBX가 PSTN 게이트웨이의 필요성을 해소하지 못한 경우 통화 경로에 중재 서버와 PBX를 연결하는 게이트웨이를 배포해야 합니다.

<div>


> [!NOTE]  
> 독립 실행형 중재 서버의 미디어 성능을 향상 시키려면 이러한 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다. RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다. 자세한 내용은 Windows Server의 "수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>하세요. RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

