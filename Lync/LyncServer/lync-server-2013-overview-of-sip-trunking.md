---
title: 'Lync Server 2013: SIP 트렁크 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e71a1f02fda14c2bcbb54aaec5e12307421090e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

SIP 트렁크 구축은 조직의 통신을 단순화 하 고 실시간 통신에 대 한 최신 향상을 준비 하기 위한 커다란 단계가 될 수 있습니다. SIP 트렁크의 주요 장점 중 하나는 이전에는 TDM (시간 구분 위치 멀티플렉싱)와 반대로 중앙 사이트에서 조직의 연결을 PSTN (공중 전화망)에 통합할 수 있다는 것입니다. 각 분기 사이트에서 별도의 트렁크가 필요 합니다.

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server의 SIP 트렁크

Lync Server 2013 SIP 트렁크 기능을 사용 하면 다음을 사용할 수 있습니다.

  - 회사 방화벽 내부 또는 외부에 있는 enterprise 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 E. 164 규격 번호로 지정 된 시내 전화 또는 시외 전화를 걸 수 있습니다.

  - 모든 PSTN 구독자는 해당 enterprise 사용자와 연결 된 직접 안쪽 전화 걸기 (즉) 번호를 사용 하 여 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.

</div>

<div>

## <a name="cost-savings"></a>비용 절감

SIP 트렁크과 관련 된 비용 절감 금액은 상당히 크게 증가할 수 있습니다.

  - 일반적으로 SIP 트렁크를 통한 장거리 통화 비용이 많이 듭니다.

  - 관리 효율성 비용을 절감 하 고 배포의 복잡성을 줄일 수 있습니다.

  - SIP 트렁크를 ITSP에 직접 연결 하면 BRI (기본 속도 인터페이스) 및 PRI (기본 속도 인터페이스) 수수료를 제거할 수 있습니다. TDM 트렁크에서는 서비스 공급자가 1 분 동안 통화를 충전 합니다. SIP 트렁크 비용은 비교적 작고 경제적으로 구입할 수 있는 대역폭 사용량을 기반으로 할 수 있습니다. 실제 비용은 선택한 ITSP의 서비스 모델에 따라 달라 집니다.

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 트렁크 및 PSTN 게이트웨이 또는 IP-PBX 호스팅

SIP 트렁크가 서비스 공급자에 직접 연결 하기 때문에 PSTN 게이트웨이 및 해당 관리 비용 및 복잡도를 없앨 수 있습니다. SIP 트렁크를 사용 하면 유지 관리 및 관리가 줄어들어 비용 절감 효과를 크게 절감할 수 있습니다.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>확장 된 VoIP 서비스

음성 기능은 종종 SIP 트렁크 배포의 주요 동기 이지만 음성 지원은 첫 번째 단계에 불과합니다. SIP 트렁크를 사용 하 여 VoIP 기능을 확장 하 고 Lync Server 2013을 사용 하 여 보다 다양 한 서비스 집합을 제공할 수 있습니다. 예:

  - 향상 된 현재 상태 검색 (Lync Server 2013을 실행 하지 않는 장치)을 사용 하면 휴대폰을 보다 효율적으로 통합 하 여 사용자가 휴대폰 통화 상태 인지 확인할 수 있습니다.

  - E9-1-1 긴급 통화를 통해 911 통화에 응답 하 여 전화 번호에서 발신자의 위치를 확인할 수 있습니다.

<div>


> [!NOTE]  
> 사용자가 지원 하 고 조직에 대해 사용 하도록 설정할 수 있는 서비스 목록은 ITSP에 문의 하세요.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

