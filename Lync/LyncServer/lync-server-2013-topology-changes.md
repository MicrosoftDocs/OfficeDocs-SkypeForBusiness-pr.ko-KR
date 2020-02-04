---
title: Lync Server 2013 토폴로지 변경 내용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 변경 내용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

Lync Server 2013에 대 한 토폴로지 요구 사항과 고려 사항은이 섹션에 설명 된 바와 같이 이전 릴리스의 경우와 다릅니다.

<div>

## <a name="new-front-end-pools-architecture"></a>새 프런트 엔드 풀 아키텍처

Lync Server 2013에서는 Enterprise Edition 프런트 엔드 풀의 아키텍처가 분산 시스템 아키텍처로 변경 되었습니다.

이 새로운 아키텍처를 사용 하는 경우 백 엔드 데이터베이스는 더 이상 풀의 실시간 데이터 저장소가 아닙니다. 특정 사용자에 대 한 정보는 풀의 프런트 엔드 서버 3 대에 보관 됩니다. 각 사용자에 대해 한 프런트 엔드 서버는 해당 사용자 정보의 마스터 역할을 하며, 두 개의 다른 프런트 엔드 서버는 복제본으로 역할을 합니다. 프런트 엔드 서버가 중단 되 면 복제본으로 처리 되는 다른 프런트 엔드 서버가 자동으로 마스터로 승격 됩니다.

이는 백그라운드에서 수행 되며, 관리자는 어떤 프런트 엔드 서버가 어떤 사용자에 대 한 마스터 인지 알 필요가 없습니다. 이러한 데이터 저장소 배포는 풀 내의 성능 및 확장성을 개선 하 고 단일 백 엔드 서버의 단일 실패 지점을 제거 합니다.

백 엔드 서버는 사용자 및 회의 데이터에 대 한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 기본 저장소 이기도 합니다.

이러한 개선 사항은 풀을 계획 하 고 유지 관리 하는 방법에도 변화가 있음을 의미 합니다. 프런트 엔드 풀 아키텍처가 디자인 된 모든 복제본을 제공 하기 위해 모든 Enterprise Edition 프런트 엔드 풀에는 3 개 이상의 프런트 엔드 서버가 포함 된 것이 좋습니다. 또한 프런트 엔드 풀에 서버를 추가 하거나, 서버를 제거 하거나, 서버를 업그레이드 하는 경우에는 특정 절차를 따라야 합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.

<div>

## <a name="server-role-topology-changes"></a>서버 역할 토폴로지가 변경 되는 경우

다른 서버에서 이전에 실행 한 일부 서버 역할이 프런트 엔드 서버 역할에 통합 되어 하드웨어 비용을 절약할 수 있습니다.

  - Lync Server 2013에서 A/V 회의 서버는 항상 프런트 엔드 서버와 collocated 됩니다.

  - 이제 모니터링과 아카이빙 모두의 프런트 엔드가 항상 프런트 엔드 서버와 collocated 됩니다. 각 모니터링 및 보관에는 각각 프런트 엔드 풀의 백 엔드 데이터베이스와 동일한 서버에 collocated 될 수 있거나 별도의 백 엔드 서버에 호스팅될 수 있는 별도의 백 엔드 데이터베이스가 필요 합니다.

  - 영구 채팅 서버는 이제 서버 역할입니다. Microsoft Lync Server 2010에서 그룹 채팅 서버는 Microsoft Lync Server 2010 용 타사 신뢰할 수 있는 응용 프로그램입니다. Lync Server 2013에서 영구 채팅 서버 기능은 다음과 같은 세 가지 새로운 서버 역할을 사용 하 여 구현 됩니다.
    
      - **PersistentChatService:** 프런트 엔드 역할로 구현 된 기본 영구 채팅 서버 서비스
    
      - **PersistentChatStore:** 백 엔드 서버 역할
    
      - **PersistentChatComplianceStore:** 영구 채팅 준수를 위한 백 엔드 서버 역할

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

