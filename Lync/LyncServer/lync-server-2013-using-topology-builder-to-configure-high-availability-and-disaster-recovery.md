---
title: 토폴로지 작성기를 사용 하 여 고가용성 및 재해 복구 구성
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
ms.openlocfilehash: 21e240e8fd597f1fe8a2669df45d674be7a7bef1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508655"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>토폴로지 작성기를 사용 하 여 Lync Server 2013에서 고가용성 및 재해 복구 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

토폴로지 작성기 내에서 다음 단계를 수행 하 여 영구 채팅 서버에 대 한 고가용성 및 재해 복구를 구성 합니다.

1.  미러 데이터베이스 및 로그 전달 보조 데이터베이스 SQL Server 저장소를 추가 합니다.

2.  영구 채팅 서버 서비스 속성을 다음과 같이 편집 합니다.
    
    1.  주 데이터베이스에 대한 미러링을 사용하도록 설정합니다.
    
    2.  기본 미러 SQL Server 저장소를 추가 합니다.
    
    3.  SQL Server 로그 전달 데이터베이스를 사용 하도록 설정 합니다.
    
    4.  SQL Server 로그 전달 보조 SQL Server 저장소를 추가 합니다.
    
    5.  보조 데이터베이스에 대 한 SQL Server 저장소 미러를 추가 합니다.
    
    6.  토폴로지를 게시합니다.

</div>

<span> </span>

</div>

</div>

</div>

