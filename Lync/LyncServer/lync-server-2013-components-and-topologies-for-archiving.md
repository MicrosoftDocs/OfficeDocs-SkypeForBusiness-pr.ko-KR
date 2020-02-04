---
title: 'Lync Server 2013: 보관의 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013의 보관의 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

Lync Server 2013 IM 및 회의 콘텐츠를 보관 하려는 경우 Lync Server에서 보관을 구현할 수 있습니다.

<div>

## <a name="archiving-components"></a>구성 요소 보관

보관 기능은 다음 구성 요소를 포함 합니다.

  - **보관 에이전트**. 보관 에이전트 (통합 데이터 수집 에이전트도 라고도 함)는 모든 프런트 엔드 풀 및 Standard Edition 서버에 자동으로 설치 되 고 활성화 됩니다. 보관 에이전트는 자동으로 활성화 되지만, 보관이 사용 되 고 적절 하 게 구성 될 때까지 메시지가 실제로 캡처되지 않습니다.

  - **데이터 저장소 보관**. Lync Server 2013의 데이터 저장소는 다음 중 하나가 될 수 있습니다.
    
      - Exchange 2013 저장소. Microsoft Exchange 통합 옵션을 사용 하도록 설정 하는 경우 Exchange 2013 서버에 있는 사용자 사서함이 보관 된 데이터에 Exchange 2013 저장소를 사용 하지만 사서함이 원본 위치 유지에 저장 되어 있는 경우에만 가능 합니다.
    
      - SQL Server 저장소. 배포에서 Lync Server 2013에 있는 사용자가 있는 경우 지원 되는 버전의 SQL Server를 실행 하는 보관 데이터베이스를 설정 하 여 해당 사용자의 보관을 사용 하도록 설정할 수 있습니다.

또한 보관에는 파일 저장소가 필요 하지만, 보관에는 프런트 엔드 서버 또는 스탠더드 버전 서버와 동일한 파일 저장소를 사용 합니다.

보관을 위한 하드웨어 및 소프트웨어 요구 사항 목록은 제공 가능성 설명서의 lync server 2013에서 Lync Server 2013 및 [서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.

</div>

<div>

## <a name="supported-topologies"></a>지원 되는 토폴로지

보관 지원이 필요한 사용자가 있는 각 풀에 보관을 배포 합니다. 엔터프라이즈 버전 풀이나 Standard Edition 서버의 프런트 엔드 서버에서 보관을 실행 합니다. 보관 데이터 저장소는 다음이 될 수 있습니다.

  - Exchange 2013 저장소와 통합

  - 별도의 SQL Server 데이터베이스를 사용 하 여 배포

Exchange 2013 배포에 Lync Server 배포의 모든 사용자가 포함 되어 있지 않은 경우 Exchange 2013 서버에서 사서함이 홈 상태인 사용자에 대해 Microsoft Exchange 통합을 사용 하 고 다른 모든 컴퓨터에 대해 별도의 SQL Server 데이터베이스를 배포 해야 합니다. Lync 사용자는 보관에 사용할 수 있습니다.

</div>

<div>

## <a name="supported-collocation"></a>지원 되는 Collocation

Lync Server 2013는 특정 서버에서 여러 구성 요소를 실행 하 여 하드웨어 비용을 절약 하 고 (소규모 조직의 경우) 다른 서버에서 개별 구성 요소를 실행 하 여 유연성 있게 사용할 수 있는 다양 한 collocation 시나리오를 지원 합니다 (규모가 큰 경우 확장성 및 성능이 필요한 조직 구성 요소를 collocate 여부를 결정 하기 전에 확장성 요인을 고려해 야 합니다.

보관은 풀 또는 스탠더드 버전 서버의 프런트 엔드 서버에 배포 됩니다. Collocated 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.

저장소를 Exchange 2013 저장소와 통합 하는 대신 별도의 SQL Server 데이터베이스를 사용 하는 경우 다음 중 하나를 사용 하 여 보관 데이터베이스를 collocate 수 있습니다.

  - 모니터링 데이터베이스

  - Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스

<div>


> [!NOTE]  
> 보관 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다. 그러나 다른 데이터베이스와 보관 데이터베이스를 collocating 하는 경우에는 여러 사용자에 게 메시지를 보관 하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 점에 주의 해야 합니다. 이 때문에 백 엔드 데이터베이스를 사용 하는 경우 보관 데이터베이스를 collocating 하지 않는 것이 좋습니다.



</div>

모니터링 데이터베이스, 백 엔드 데이터베이스 또는 둘 다를 사용 하 여 보관 데이터베이스를 collocate 경우 데이터베이스 전체 또는 일부에 대해 단일 SQL 인스턴스를 사용 하거나, 다음과 같이 각 데이터베이스에 대해 별도의 SQL 인스턴스를 사용할 수 있습니다. 큰

  - 각 SQL 인스턴스에는 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스 및 단일 보관 데이터베이스만 포함 될 수 있습니다.

모든 서버 역할 및 데이터베이스의 collocation에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

