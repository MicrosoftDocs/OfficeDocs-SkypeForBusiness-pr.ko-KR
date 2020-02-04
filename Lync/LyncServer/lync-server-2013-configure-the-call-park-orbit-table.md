---
title: 'Lync Server 2013: 통화 대기 번호 테이블 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fb90feb9f12f8c2776518fa8fefffae7ff003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Lync Server 2013에서 통화 대기 번호 테이블 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-10_

통화 공원는 orbits 통화를 사용 합니다. 사용자가 전화를 걸고 검색할 수 있으려면 통화 공원 표를 구성 해야 합니다. 조직에서 파킹 통화를 위해 예약 하는 내선 번호 범위 (orbits)를 지정 하 고 각 범위에 대 한 통화 공원 풀 핸들을 지정 하 여 해당 범위에 대 한 라우팅을 정의 해야 합니다. 궤도 범위를 정의 하는 경우 orbits 충분 한 회전을 사용 하는 것이 목표는 하지만, 사용자 또는 다른 서비스에 대해 제공 되는 확장 수를 제한 하는 것이 여러 orbits 되지 않도록 하는 것입니다. 통화 공원 응용 프로그램이 배포 된 각 Lync Server 풀에 대해 여러 통화 공원 궤도 범위를 만들 수 있습니다. 각 통화 공원 궤도 범위에는 전역 고유 이름과 고유한 확장명 집합이 있어야 합니다.

<div>


> [!IMPORTANT]  
> 궤도 범위는 일반적으로 100 이하의 orbits를 포함 합니다. 각 범위는 범위 당 최대 1만 orbits 보다 작고 orbits 5만 보다 적은 수의 용량을 보유 한 경우에 한 하 여 훨씬 더 커질 수 있습니다. 범위가 너무 작으면 orbits 보다 빠르게 다시 사용 됩니다.



</div>

궤도 범위에 대 한 가상 확장 블록 (사용자 또는 전화 번호를 지정 하지 않은 확장명)을 사용 합니다.

<div>


> [!NOTE]  
> 직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

[Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

