---
title: 'Lync Server 2013: Microsoft Lync 배포 방법 결정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f1869cce980f8eb530e1541bd64ead3a7b4258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Lync Server 2013 배포 방법 결정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

Lync를 계획할 때는 먼저 Microsoft Lync: Lync Server 2013 온-프레미스 또는 클라우드에서 Microsoft Office 365을 사용 하 여 Lync Online을 배포 하는 것이 가장 중요 한 결정 사항입니다.

  - **Lync Server 2013 온-프레미스** :이 옵션은 전체 Lync 기능 집합을 제공 하며 배포를 구성, 사용자 지정 및 운영 하는 데 최고의 유연성을 제공 합니다. 모든 서버는 조직에서 온사이트 및 유지 관리 되는 방식으로 설치 됩니다. 온-프레미스 배포는 모든 범위의 Lync Server 기능을 제공 합니다.

  - **클라우드의 Lync Online** Lync Online은 Lync Server의 비즈니스 급 기능을 희생 하지 않고 클라우드 기반 인스턴트 메시징, 현재 상태 및 모임의 비용 및 민첩성을 향상 시킬 수 있는 조직을 위해 설계 되었습니다. Lync Online에서는 Microsoft가 필요한 서버 인프라를 배포 및 유지 관리 하 고 지속적인 유지 관리, 패치 및 업그레이드를 처리 합니다. 온-프레미스 배포에서 사용할 수 있는 일부 기능은 Lync Online에서는 사용할 수 없습니다.

사용자에 게 가장 적합 한 배포 유형은 배포 하려는 작업 부하와 조직의 지역 및 비즈니스 상태에 따라 달라 집니다.

<div>

## <a name="lync-server"></a>Lync Server

온-프레미스 Lync Server 배포는 다음과 같은 시나리오에 가장 적합 합니다.

  - **전체 엔터프라이즈 음성 기능**   PBX를 교체 하거나 고급 통화 기능을 사용 하는 전체 엔터프라이즈 음성 솔루션을 배포 하려는 경우 온-프레미스 Lync Server 배포가 필요 합니다. 온-프레미스는 PBX 시스템 및 트렁크에 대 한 직접 연결 및 응답 그룹 및 통화 대기와 같은 고급 전화 기능을 지원 합니다. Lync Online에서는 현재 이러한 기능을 지원 하지 않습니다.

  - **미디어 품질 제어**   CAC (통화 허용 제어) 및 QoS (서비스 품질) 기능과 같은 모든 범위의 미디어 품질 보증 기능을 사용 하려는 경우에는 온-프레미스 배포를 사용할 수 있습니다.

  - **영구 채팅**   조직에 영구 채팅을 배포 해야 하는 경우 온-프레미스 배포를 선택 해야 합니다.

  - **타사 서버 응용 프로그램**   온-프레미스 배포만 Microsoft 통합 커뮤니케이션 관리 API (c)를 사용 하는 신뢰할 수 있는 타사 응용 프로그램에서 작동할 수 있습니다.

  - **지역별 지원이**   필요한 다국어/다중 지역 회사 여러 국가 또는 지역에 데이터 센터가 있고 지역별로 서버를 배포 하 고 관리 해야 하는 경우에는 온-프레미스 배포가 이러한 유형의 지역별 관리 기능을 제공 하는 것이 가장 좋습니다.

  - ****   사용자는 온-프레미스 Lync Server 배포를 사용 하 여 정책, 보고서 및 업그레이드를 완벽 하 게 제어할 수 있으며, 전체 서버 및 클라이언트 정책, 모니터링 및 기타 보고서와 업그레이드 시기에 액세스할 수 있습니다. Lync Online에서는 정책 설정 및 보고서의 하위 집합을 제공 하며 업그레이드를 허용 하는 제한 된 기간을 제공 합니다.

</div>

<div>

## <a name="lync-online"></a>Lync Online

앞의 목록에 있는 어떤 요소도 중요 하지 않은 경우에는 Lync Online을 선택 하 여 배포 및 관리 편의성을 높일 수 있습니다. Lync Online은 강력한 IM, 현재 상태 및 회의 기능 집합을 제공 하며, 조직의 사용자 간에 IP를 통한 음성 및 화상 통화를 가능 하 게 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

