---
title: 'Lync Server 2013: 백업 및 복원 전략 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Lync Server 2013에 대 한 백업 및 복원 전략 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-26_

Lync Server에 대 한 백업 및 복원 계획을 개발 하려면 먼저 조직의 목표에 맞는 전략을 개발 해야 합니다. 효과적인 백업 및 복원 전략을 개발 하려면 다음이 필요 합니다.

  - 비즈니스 우선 순위 설정

  - 백업 및 복원 요구 사항을 식별 합니다.

<div>

## <a name="establishing-business-priorities"></a>비즈니스 우선 순위 설정

조직의 비즈니스 우선 순위를 평가 합니다. 일반적으로 백업 및 복원 전략에 영향을 주는 주요 비즈니스 우선 순위는 다음과 같습니다.

  - 비즈니스 연속성 요구 사항

  - 데이터 완전성

  - 데이터 중요도

  - 이식성 요구 사항

  - 비용 제약 조건

고객을 위해 개발 하는 Sla (서비스 수준 계약)를 결정 하기 위해 이러한 도움말과 같은 비즈니스 요구 사항. 서비스 수준 계약은 백업 및 복구 전략에 큰 영향을 줍니다.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>백업 및 복원 요구 사항 식별

비즈니스 우선 순위와 서비스 수준 계약은 Lync Server의 백업 및 복원에 대 한 조직의 요구 사항을 결정 하는 데 작용 합니다. 다음에 대 한 요구 사항을 확인 하 고 문서화 합니다.

  - **백업의 빈도 백업**   빈도 모범 사례에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원에 대](lync-server-2013-best-practices-for-backup-and-restoration.md)한 모범 사례를 참조 하세요.

  - **백업 및 복원 도구**   에는 도구를 사용 하는 사용자 및 해당 컴퓨터를 포함 합니다. 이 항목에서 설명 하는 도구와 필요한 권한에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)을 참조 하세요.

  - **백업 위치**   는 백업이 로컬로 유지 되는지, 아니면 보안 및 접근성을 고려 하 여 수행 하는지 여부를 확인 합니다. 백업에 사용할 미디어를 지정 합니다.

  - **하드웨어 및 소프트웨어 요구 사항은**   백업 저장 및 백업 및 복원 지원에 필요한 소프트웨어 및 네트워크 연결을 비롯 한 특정 하드웨어 및 소프트웨어 요구 사항을 식별 하 고 문서화 합니다. 하드웨어 및 소프트웨어 요구 사항을 개발할 때 다음의 다양 한 복원 시나리오에 유의 하세요.

  - **복원 시나리오**   다음 시나리오의 복원 프로세스는 다음과 같습니다.
    
      - Lync 서버 풀이 실패 합니다. 이 시나리오에서는 풀의 각 서버를 다시 만들어야 합니다.
    
      - 스탠더드 버전 서버는 작동 하지 않습니다. 이 시나리오에서는 새 컴퓨터 또는 깨끗 한 컴퓨터에서 서버를 다시 빌드하여 데이터베이스를 복원 해야 합니다.
    
      - 중앙 관리 저장소의 손실. 최소한이 시나리오에서는 중앙 관리 저장소를 복원 하 고 게시 해야 합니다.
    
      - 중앙 관리 저장소가 정상적으로 작동 하는 경우 백 엔드 서버의 손실 이 시나리오에서는 새 컴퓨터 또는 깨끗 한 컴퓨터에서 서버를 다시 빌드하여 데이터베이스를 복원 해야 합니다.
    
      - Lync 서버 풀의 구성원 인 서버가 실패 합니다. 이 시나리오에서는 신규 또는 깨끗 한 컴퓨터에서 서버를 다시 만들어야 합니다.
    
      - 파일 저장소가 실패 합니다. 이 시나리오에서는 파일 서버 또는 파일 클러스터를 복원 해야 합니다.
    
      - 보관, 모니터링 또는 영구 채팅 데이터베이스에 오류가 발생 했습니다. 이 시나리오에서는 데이터베이스를 다시 만들어야 하며 데이터를 조직에 중요 한 경우 데이터를 복원 해야 합니다. Lync Server를 다시 설치 하 고 실행 하는 데는 보관, 모니터링 및 영구 채팅 데이터가 필요 하지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

