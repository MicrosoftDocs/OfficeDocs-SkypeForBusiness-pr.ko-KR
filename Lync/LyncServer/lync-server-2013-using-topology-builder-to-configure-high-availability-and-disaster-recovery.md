---
title: 토폴로지 작성기로 재해 복구 및 고가용성 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 작성기로 재해 복구 및 고가용성 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

토폴로지 작성기 내에서 다음 단계를 수행 하 여 영구 채팅 서버에 대 한 고가용성 및 재해 복구를 구성 합니다.

1.  미러 데이터베이스와 로그 전달 보조 데이터베이스 SQL Server 저장소를 추가 합니다.

2.  영구 채팅 서버 서비스 속성을 다음으로 편집 합니다.
    
    1.  기본 데이터베이스에 대해 미러링을 사용 하도록 설정 합니다.
    
    2.  기본 미러 SQL Server 저장소를 추가 합니다.
    
    3.  SQL Server 로그 전달 데이터베이스를 사용 하도록 설정 합니다.
    
    4.  SQL Server 로그 전달 보조 SQL Server 저장소를 추가 합니다.
    
    5.  보조 데이터베이스에 대 한 SQL Server 저장소 미러를 추가 합니다.
    
    6.  토폴로지를 게시 합니다.

</div>

<span> </span>

</div>

</div>

</div>

