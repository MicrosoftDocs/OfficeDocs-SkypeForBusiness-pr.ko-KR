---
title: 'Lync Server 2013: 통화 공원에 대 한 정규화 규칙 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Lync Server 2013에서 통화 공원에 대 한 정규화 규칙 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-11_

통화 공원 orbits는 정규화 해서는 안 됩니다. 전화 걸기 계획을 검사 하 여 궤도 번호가 정규화 되지 않았는지 확인 합니다. Orbits의 정규화를 방지 하는 추가 정규화 규칙을 만들어야 하는 경우에는 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 절차에 따라 새 정규화 규칙을 정의 하 여 **일치 하는 패턴** 에서 궤도 범위와 번역 $1 **패턴** 을 구분 **** 하도록 지정 합니다. 예를 들어 통화 공원 궤도 범위가 7000 – 7999 이면 **일치 하는 패턴** 은 **^\\(7 d{3}) $** 이 고 **번역 패턴** 은 **$1**입니다.

<div>


> [!IMPORTANT]  
> 다이얼 플랜의 기본 정규화 규칙에 <STRONG>^ (\d *)</STRONG>이 포함 되어 있지 않은지 확인 합니다. 그렇지 않으면 통화 공원 표준화 규칙이 실행 되지 않습니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

