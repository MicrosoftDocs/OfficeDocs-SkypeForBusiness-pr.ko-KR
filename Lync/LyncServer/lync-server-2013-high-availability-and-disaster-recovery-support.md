---
title: 'Lync Server 2013: 고가용성 및 재해 복구 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5251b9f0790c39aa3ca03492e50517a177d340
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Lync Server 2013의 고가용성 및 재해 복구 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-25_

Lync Server 2013에서는 풀링을 통한 서버 중복성으로 고가용성을 제공 합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다. 이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다. 서버 역할에 대 한 자세한 내용은 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md)을 참조 하십시오.

Lync Server 2013 또한 풀 페어링을 사용 하도록 설정 하 여 재해 복구 조치를 제공 합니다. 이 토폴로지를 배포 하는 경우 각 풀이 별도의 데이터 센터에 있는 쌍의 각 풀과 별도의 지리적 영역에 있는 프런트 엔드 풀 쌍을 지정 합니다. 풀 또는 사이트가 다운 되 면 해당 풀의 사용자가 해당 쌍의 다른 풀을 사용 하도록 리디렉션하여 서비스 중단을 최소화할 수 있습니다.

Lync Server 2013 또한 백 엔드 서버 고가용성을 지원 합니다. 프런트 엔드 풀에 대해 두 개의 백 엔드 서버를 배포 하 고 백 엔드 서버에서 실행 되는 모든 Lync 데이터베이스에 대해 동기 SQL Server 미러링을 설정 하는 선택적 토폴로지입니다.

풀 페어링 및 백 엔드 서버 미러링에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 서버 역할](lync-server-2013-server-roles.md)  
[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

