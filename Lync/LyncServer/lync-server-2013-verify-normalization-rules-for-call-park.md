---
title: 'Lync Server 2013: 통화 대기에 대 한 정규화 규칙 확인'
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
ms.openlocfilehash: 1fcde0adac292b8773a81c759c72765f832ce745
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 대기에 대 한 정규화 규칙 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-11_

통화 대기 궤도는 정규화 해서는 안 됩니다. 다이얼 플랜을 검사 하 여 궤도 번호가 정규화 되지 않도록 합니다. 궤도의 정규화를 방지 하는 추가 정규화 규칙을 만들어야 하는 경우에는 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 절차에 따라 새 정규화 규칙을 정의 하 여 **일치 시킬 패턴이** 궤도 범위와 **변환 패턴** 의 **$1**인지 확인 합니다. 예를 들어 통화 대기 번호 범위가 7000-7999 인 경우 **일치 하는 패턴** 은 **^\\(7 d{3}) $** 이 고 **변환 패턴** 은 **$1**입니다.

<div>


> [!IMPORTANT]  
> 다이얼 플랜의 기본 정규화 규칙에 <STRONG>^(\d*)</STRONG>가 포함되지 않았는지 확인합니다. 그렇지 않으면 통화 대기 정규화 규칙이 실행 되지 않습니다.



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

