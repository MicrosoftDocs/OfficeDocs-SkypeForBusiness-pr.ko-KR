---
title: 'Lync Server 2013: 정규화 규칙 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a09f5075ffe8ff267f31333d3dba0f4fffbc41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Lync Server 2013에서 정규화 규칙 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-04-22_

Lync Server 2013 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화를 걸고 있는 전화 번호를 E. 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 건 전화 번호를 가져오고 해당 번호를 Lync Server에서 내부적으로 사용 하는 형식으로 변환 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.

정규화 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하십시오.

정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)을 참조 하십시오.

다음 방법 중 하나를 사용하여 정규화 규칙을 정의하거나 편집할 수 있습니다.

  - **정규화 규칙 작성** 도구를 사용 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.

  - 수동으로 정규식을 작성하여 일치 패턴 및 변환 규칙을 정의합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013에서 다이얼 플랜 수정](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

