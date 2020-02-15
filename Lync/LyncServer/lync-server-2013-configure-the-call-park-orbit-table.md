---
title: 'Lync Server 2013: 통화 대기 궤도 테이블 구성'
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
ms.openlocfilehash: dbeb465bd9ac4e62a51ab562238db9a6c0828f99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 궤도 테이블 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-10_

통화 대기는 궤도에서 파킹 통화를 사용 합니다. 사용자가 통화를 대기 및 검색할 수 있으려면 통화 대기 궤도 테이블을 구성 해야 합니다. 조직에서 파킹 통화를 위해 예약할 내선 번호의 범위를 지정 하 고 각 범위에 대 한 핸들을 처리할 통화 대기 풀을 지정 하 여 해당 범위에 대 한 라우팅을 정의 해야 합니다. 궤도 범위를 정의 하는 경우에는 모든 궤도를 너무 빨리 다시 사용할 수 없도록 충분 한 궤도을 확보 하는 것이 목표입니다. 통화 대기 응용 프로그램이 배포 된 각 Lync Server 풀에 대해 통화 대기 궤도 범위를 여러 개 만들 수 있습니다. 각 통화 대기 궤도 범위에는 전역적으로 고유한 이름과 고유한 내선 번호가 있어야 합니다.

<div>


> [!IMPORTANT]  
> 궤도 범위는 일반적으로 100 개 이하의 궤도을 포함 합니다. 각 범위는 범위 당 최대 1만 궤도 보다 작으며, 풀 당 5만을 초과 하는 경우를 제외 하면 훨씬 더 커질 수 있습니다. 범위가 너무 작으면 궤도가 보다 빠르게 다시 사용 됩니다.



</div>

사용 중인 궤도 범위에 대해 가상 내선 번호 블록 (사용자 또는 전화가 할당 되지 않은 확장명)을 사용할 수 있습니다.

<div>


> [!NOTE]  
> 직접 연결 된 전화 걸기 (*) 번호를 통화 대기 번호 표에 있는 궤도 번호로 지정 하는 것은 지원 되지 않습니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

[Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

