---
title: Standard Edition 서버 배포의 Lync Server 2013 서버 배치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e50aa9339d992e73cf4e5b32b1e49fc2a144e67
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510315"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013에 대 한 Standard Edition server 배포의 서버 배치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-20_

이 섹션에서는 Lync Server 2013 Standard Edition server 배포에서 함께 배치할 수 있는 서버 역할, 데이터베이스 및 파일 공유에 대해 설명 합니다.

<div>

## <a name="server-roles"></a>서버 역할

Lync Server 2013에서는 A/V 회의 서비스, 중재 서비스, 모니터링 및 보관을 Standard Edition Server에 배치 된, 사용 하도록 설정 하려면 추가 구성이 필요 합니다. 중재 서비스는 별도의 서버에 배포하도록 선택할 수 있습니다.

신뢰할 수 있는 응용 프로그램 서버를 Standard Edition 서버와 함께 배치할 수 있습니다.

다음 서버 역할을 각각의 개별 컴퓨터에 배포해야 합니다.

  - Director

  - 에지 서버

  - 중재 서버(Standard Edition 서버와 함께 배치되지 않은 경우)

  - Office Web Apps 서버

</div>

<div>

## <a name="databases"></a>데이터베이스

기본적으로 SQL Server Express 백 엔드 데이터베이스는 Standard Edition 서버에 배치됩니다. 개별 컴퓨터로 이동할 수 없습니다. 한 가지 예외를 제외 하면 Standard Edition 서버에서 다른 데이터베이스를 함께 배치할 수 없습니다. Standard Edition 서버에 영구 채팅 서버를 배포 하도록 선택한 경우 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 동일한 Standard Edition 서버에 함께 배치할 수 있습니다.

단일 데이터베이스 서버에 다음과 같은 각 데이터베이스를 함께 배치할 수 있습니다.

  - 모니터링 데이터베이스

  - 보관 데이터베이스

  - Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스

단일 SQL 인스턴스에서 이러한 모든 데이터베이스를 함께 배치하거나 각 데이터베이스에 대해 개별 SQL 인스턴스를 사용할 수 있지만 다음과 같은 제한 사항이 있습니다.

  - 각 SQL 인스턴스는 단일 백 엔드 데이터베이스(Enterprise Edition 프런트 엔드 풀용), 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스만 포함할 수 있습니다.

  - 데이터베이스 서버는 두 개 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행 하는 하나의 서버, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스를 지원할 수 없지만 데이터베이스에 동일한 SQL Server 인스턴스 또는 개별 SQL Server 인스턴스가 사용 되는지 여부에 관계 없이 각 항목 중 하나를 지원할 수 있습니다.

이 섹션의 뒷부분에서 설명하는 대로 파일 공유를 데이터베이스와 함께 배치할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서는 배포의 일부 또는 모든 사용자에 대해 모니터링 및 보관 저장소와 Exchange 2013 저장소를 통합 하는 옵션을 사용할 수 있습니다. Lync Server를 실행 하는 서버 또는 구성 요소는 Exchange 저장소와 동일한 서버에 배포할 수 없습니다.



</div>

<div>


> [!IMPORTANT]  
> 데이터베이스 배치가 지원되기는 하지만, 데이터베이스는 크기가 빠르게 커질 수 있습니다. 예를 들어 보관 데이터베이스를 다른 데이터베이스와 함께 배치하도록 고려할 때 여러 사용자의 메시지를 보관하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있음을 염두에 두어야 합니다. 따라서 여러 데이터베이스, 특히 보관 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 엔터프라이즈 풀의 백 엔드 데이터베이스와 배치 않는 것이 좋습니다.



</div>

</div>

<div>

## <a name="file-shares"></a>파일 공유

파일 공유는 개별 서버이거나 다음 중 일부 또는 전체와 동일한 서버에 배치될 수 있습니다.

  - Enterprise Edition 프런트 엔드 풀의 백 엔드 서버를 포함하는 데이터베이스 서버

  - 보관 데이터베이스

  - 모니터링 데이터베이스

  - 영구 채팅 데이터베이스

  - 영구 채팅 준수 데이터베이스

단일 파일 공유를 여러 프런트 엔드 풀 및 Standard Edition 서버(모두 동일 사이트에 포함됨)에 대해 사용할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서 모니터링 및 보관은 Lync Server 파일 공유를 Standard Edition 서버로 사용 합니다.



</div>

</div>

<div>

## <a name="other-components"></a>기타 구성 요소

Lync server 2013 서버 역할이 있는 페더레이션 사용자에 대해 웹 콘텐츠 공유를 지원 하려면 역방향 프록시 서버 2013를 함께 배치할 수는 없지만이 구성 요소는 배포에 필요 합니다. 그러나 조직의 다른 응용 프로그램에 사용 되는 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다.

모든 Lync Server 2013 역할을 사용 하 여 모든 Exchange UM 구성 요소 또는 SharePoint 구성 요소를 함께 배치할 수는 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

