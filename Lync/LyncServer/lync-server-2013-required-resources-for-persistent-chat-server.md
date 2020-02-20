---
title: 'Lync Server 2013: 영구 채팅 서버에 필요한 리소스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f59c2d368a9ea94fdd79a6aa0466313ddc43993
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 필요한 리소스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-02-05_

영구 채팅 서버에 대 한 고가용성 및 재해 복구를 수행 하려면 일반적으로 전체 작업에 필요한 것 보다 더 많은 리소스가 필요 합니다. 고가용성 및 재해 복구를 위해 영구 채팅 서버를 구성 하기 전에 표준 영구 채팅 서버 작업에 필요한 사항 외에 다음과 같은 리소스가 있는지 확인 합니다. 추가 구성 정보에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server.md)참조 하십시오.

  - 영구 채팅 서버 서비스의 홈 프런트 엔드가 있는 동일한 물리적 데이터 센터에 있는 단일 전용 데이터베이스 인스턴스입니다. 이 데이터베이스는 기본 영구 채팅 데이터베이스에 대 한 SQL Server 미러 서버 역할을 합니다. 선택적으로 미러 데이터베이스에 대 한 자동화 된 장애 조치 (failover)를 사용 하려는 경우 미러링 모니터로 사용할 추가 SQL Server를 지정 합니다.

  - 다른 실제 데이터 센터에 있는 전용 데이터베이스 인스턴스 하나. 이 데이터베이스는 기본 데이터 센터에 있는 데이터베이스에 대 한 SQL Server 로그 전달 보조 데이터베이스 역할을 합니다.

  - 보조 데이터베이스에 대 한 SQL Server 미러로 사용할 하나의 전용 데이터베이스 인스턴스만 사용 합니다. 선택적으로 추가 SQL Server를 미러링 모니터 서버로 서버에 지정 합니다. 이 두 가지 모두 보조 데이터베이스와 동일한 실제 데이터 센터에 있어야 합니다.

  - 영구 채팅 서버 준수를 사용 하도록 설정 하는 경우에는 세 가지 전용 데이터베이스 인스턴스가 추가로 필요 합니다. 해당 배포는 이전에 영구 채팅 데이터베이스에 대해 설명한 것과 동일 합니다. 준수 데이터베이스는 동일한 SQL Server 인스턴스를 영구 채팅 데이터베이스와 공유 하는 것이 가능 하지만 고가용성 및 재해 복구를 위한 독립 실행형 인스턴스를 사용 하는 것이 좋습니다.

  - SQL Server 로그 전달 트랜잭션 로그에 대해 파일 공유를 만들고 지정 해야 합니다. 영구 채팅 데이터베이스를 실행 하는 두 데이터 센터 모두의 모든 SQL 서버에는이 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 이 공유는 FileStore 역할의 일부로 정의되지 않습니다.

  - 주 서버 파일 공유에서 복사 되는 SQL Server 트랜잭션 로그의 대상 폴더로 사용할 보조 데이터베이스 서버의 파일 공유입니다.

<div>


> [!NOTE]  
> 영구 채팅 서버 풀의 활성 영구 채팅 서버는 토폴로지에 정의 된 다음 홉 Lync 풀과 동일한 표준 시간대에 있어야 합니다.



</div>

다음 그림에서는 전체 영구 채팅 서버 풀을 서로 다른 두 개의 늘인 풀 토폴로지에서 구성 하는 방법에 대 한 예를 제공 합니다.

  - 데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀

  - 데이터 센터가 낮은 대역폭/긴 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀

다음 그림에서는 데이터 센터가 높은 대역폭/짧은 대기 시간을 사용 하 여 지리적으로 분산 된 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.

**데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀**

![영구 채팅 서버 풀 HBW 구성 검사](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "영구 채팅 서버 풀 HBW 구성 검사")

다음 그림에서는 데이터 센터가 낮은 대역폭/긴 대기 시간을 사용 하 여 지리적으로 분산 된 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.

**데이터 센터가 낮은 대역폭/긴 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀**

![영구 채팅 서버 풀 LBW 구성 검사](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "영구 채팅 서버 풀 LBW 구성 검사")

</div>

<span> </span>

</div>

</div>

</div>

