---
title: 'Lync Server 2013: SIP 트렁크 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

SIP 트렁크 구축은 조직의 통신을 단순화 하 고 실시간 통신에 대 한 최신 개선 사항을 준비 하는 데 큰 도움이 될 수 있습니다. SIP 트렁크의 주요 이점 중 하나는 해당 조직의 연결을 중앙 사이트의 PSTN (공개 통신 네트워크)에 통합할 수 있다는 것입니다. 일반적으로 TDM (시간 구분 멀티플렉싱) 트렁크와 달리 각 지점 사이트에서 별도의 트렁크가 필요 합니다.

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server의 SIP 트렁크

Lync Server 2013 SIP 트렁크 접근 권한 값은 다음을 가능 하 게 합니다.

  - 회사 방화벽 내부나 외부에 있든 상관 없이 enterprise 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 E-164 규격 번호로 지정 된 시내 전화 또는 시외 통화를 만들 수 있습니다.

  - 모든 PSTN 구독자는 해당 엔터프라이즈 사용자와 연결 된 직접적인 안쪽 전화 걸기 (시작) 번호를 사용 하 여 회사 방화벽 내부나 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.

</div>

<div>

## <a name="cost-savings"></a>비용 절감

SIP 트렁크 관련 된 비용 절감 효과는 매우 중요 합니다.

  - 장거리 통화는 일반적으로 SIP 트렁크를 통해 더욱 저렴 한 비용을 부과 합니다.

  - 관리 효율성 비용을 절감 하 고 배포의 복잡성을 줄일 수 있습니다.

  - BRI (기본 속도 인터페이스) 및 주 SP에 대 한 SIP 트렁크를 직접 저렴 한 가격으로 연결 하는 경우에는이를 제거할 수 있습니다. TDM 트렁크에서 서비스 공급자는 1 분 통화에 대 한 요금을 부과 합니다. SIP 트렁크 비용은 저렴 하 고 경제적으로 구매할 수 있는 대역폭 사용량을 기준으로 할 수 있습니다. 실제 비용은 선택한 ITSP의 서비스 모델에 따라 달라 집니다.

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 트렁크 및 PSTN 게이트웨이 또는 ip-pbx 호스팅

SIP trunks는 서비스 공급자에 직접 연결 되므로 PSTN 게이트웨이와 해당 관리 비용 및 복잡도를 없앨 수 있습니다. SIP 트렁크를 사용 하면 유지 관리 및 관리 감소를 통해 비용을 크게 절약할 수 있습니다.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>확장 된 VoIP 서비스

음성 기능은 종종 SIP 트렁크를 배포 하는 주요 동기 이지만, 음성 지원은 첫 번째 단계에 불과합니다. SIP 트렁크을 사용 하면 VoIP 기능을 확장 하 고 Lync Server 2013에서 다양 한 서비스 집합을 제공할 수 있습니다. 예를 들면 다음과 같습니다.

  - Lync Server 2013을 실행 하 고 있지 않은 장치에 대 한 향상 된 현재 상태 감지 기능은 사용자가 휴대폰 전화를 걸 때 볼 수 있도록 휴대 전화와 보다 나은 통합 기능을 제공 합니다.

  - E9-1-1-긴급 통화 911 전화를 받은 기관에서 전화 번호에서 발신자의 위치를 확인할 수 있습니다.

<div>


> [!NOTE]  
> 지원 되는 서비스 목록에 대 한 자세한 내용을 문의 하 여 조직에 대해 사용 하도록 설정할 수 있습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

