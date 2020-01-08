---
title: Lync Server 2013 Standard Edition 서버 배포의 서버 배치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013에 대한 Standard Edition 서버 배포의 서버 배치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-20_

이 섹션에서는 Lync Server 2013 Standard Edition server 배포에서 collocate 수 있는 서버 역할, 데이터베이스 및 파일 공유에 대해 설명 합니다.

<div>

## <a name="server-roles"></a>서버 역할

Lync Server 2013에서 A/V 회의 서비스, 중재 서비스, 모니터링, 보관은 스탠더드 버전 서버에서 collocated, 사용 하도록 설정 하려면 추가 구성이 필요 합니다. 별도의 서버에 중재 서비스를 배포 하도록 선택할 수 있습니다.

스탠더드 버전 서버를 사용 하 여 신뢰 하는 응용 프로그램 서버를 collocate 수 있습니다.

각각 별도의 컴퓨터에 배포 해야 하는 서버 역할은 다음과 같습니다.

  - Director

  - Edge 서버

  - 중재 서버 (스탠더드 버전 서버와 collocated 되지 않는 경우)

  - Office Web Apps 서버

</div>

<div>

## <a name="databases"></a>Databases

기본적으로 SQL Server Express 백 엔드 데이터베이스는 스탠더드 버전 서버에서 collocated 됩니다. 별도의 컴퓨터로 이동할 수 없습니다. 한 가지 예외는 스탠더드 버전 서버에서 다른 데이터베이스를 collocate 수 없습니다. Standard Edition server에 영구 채팅 서버를 배포 하기로 선택 하면 영구 채팅 데이터베이스와 영구 채팅 준수 데이터베이스를 동일한 스탠더드 버전 서버에 collocate 수 있습니다.

다음의 각 데이터베이스를 단일 데이터베이스 서버에 collocate 수 있습니다.

  - 모니터링 데이터베이스

  - 보관 데이터베이스

  - Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스

이러한 데이터베이스의 일부 또는 전부를 단일 SQL 인스턴스에서 collocate 하거나 각각 별도의 SQL 인스턴스를 사용 하 여 다음과 같은 제한 사항이 있습니다.

  - 각 SQL 인스턴스에는 단일 백 엔드 데이터베이스 (Enterprise Edition 프런트 엔드 풀 용), 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스가 포함 될 수 있습니다.

  - 데이터베이스 서버는 둘 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행 하는 서버, 모니터링을 실행 하는 서버 1 개, 단일 영구 채팅 데이터베이스, 단일 영구 채팅 준수 데이터베이스를 지원할 수 있지만, 데이터베이스에서 SQL Server의 동일한 인스턴스를 사용 하는지 아니면 SQL Server의 인스턴스가 서로 다른 지에 관계 없이

이 섹션의 뒷부분에 설명 된 대로 데이터베이스와 파일 공유를 collocate 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서 배포의 일부 또는 모든 사용자에 대 한 Exchange 2013 저장소와 모니터링 및 보관 저장소를 통합 하는 옵션이 있습니다. Exchange 저장소와 동일한 서버에서 Lync Server 또는 구성 요소를 실행 하는 서버는 배포할 수 없습니다.



</div>

<div>


> [!IMPORTANT]  
> 데이터베이스의 collocation이 지원 되기는 하지만 데이터베이스 크기가 금방 커질 수 있습니다. 예를 들어 다른 데이터베이스와 보관 데이터베이스를 collocating 하는 경우, 여러 사용자에 게 메시지를 보관 하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 것에 주의 해야 합니다. 이러한 이유로, 엔터프라이즈 풀의 백 엔드 데이터베이스에는 여러 데이터베이스 (특히 보관 데이터베이스, 지속적인 채팅 데이터베이스, 지속적인 채팅 준수 데이터베이스)를 collocating 하지 않는 것이 좋습니다.



</div>

</div>

<div>

## <a name="file-shares"></a>파일 공유

파일 공유는 별도의 서버 이거나 다음 중 일부 또는 모두와 동일한 서버에서 collocated 수 있습니다.

  - 엔터프라이즈 에디션 프런트 엔드 풀의 백 엔드 서버를 포함 하는 데이터베이스 서버

  - 보관 데이터베이스

  - 모니터링 데이터베이스

  - 영구 채팅 데이터베이스

  - 영구 채팅 준수 데이터베이스

단일 파일 공유는 여러 프런트 엔드 풀, Standard Edition 서버 (동일한 사이트에서 모두)에 사용할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서 모니터링 및 보관은 Lync Server 파일 공유를 Standard Edition 서버로 사용 합니다.



</div>

</div>

<div>

## <a name="other-components"></a>다른 구성 요소

Lync server 2013 구성 요소가 아닌 역방향 프록시 서버는 collocate 수 없지만, Lync Server 2013 서버 역할을 사용 하는 페더레이션 사용자의 웹 콘텐츠 공유를 지원 하려면 배포에 필요 합니다. 그러나 다른 응용 프로그램에 사용 되는 조직의 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 리버스 프록시 지원을 구현할 수 있습니다.

모든 Lync Server 2013 역할을 사용 하 여 Exchange UM 구성 요소 또는 SharePoint 구성 요소를 collocate 수 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

