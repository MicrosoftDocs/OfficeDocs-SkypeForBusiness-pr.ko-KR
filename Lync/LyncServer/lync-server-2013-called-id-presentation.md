---
title: 'Lync Server 2013: 호출 되는 ID 프레젠테이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b4ad6f728f01f0cf9ef1aac6ed57ad22c7ff345
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013에서 호출 되는 ID 프레젠테이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

Lync Server 2010를 사용 하는 경우 호출 된 당사자의 전화 번호 (전화 번호)는 E. 164 형식에서 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, PBX (private branch exchange) 또는 SIP 트렁크)으로 변환 될 수 있습니다. 이 작업을 수행 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 변환 규칙을 하나 이상 정의 해야 합니다.

<div>


> [!IMPORTANT]  
> 트렁크 피어에서 변환 규칙을 구성하는 <EM>대신</EM>, 하나 이상의 변환 규칙을 Enterprise Voice 트렁크 구성에 연결하는 기능을 사용할 수 있습니다. 트렁크 피어에 대한 변환 규칙을 구성한 경우 변환 규칙을 Enterprise Voice 트렁크 구성과 연결하지 마십시오. 두 규칙이 충돌할 수 있기 때문입니다.



</div>

다음 방법 중 하나를 사용하여 변환 규칙을 만들거나 수정할 수 있습니다.

  - **변환 규칙 작성** 도구를 사용 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.

  - 수동으로 정규식을 작성하여 일치 패턴 및 변환 규칙을 정의합니다.

<div>


> [!NOTE]  
> 정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식" <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>을 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Lync Server 2013에서 수동으로 변환 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 발신자 번호 프레젠테이션](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

