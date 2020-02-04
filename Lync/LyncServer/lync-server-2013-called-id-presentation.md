---
title: 'Lync Server 2013: ID 프레젠테이션 호출'
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
ms.openlocfilehash: 8dc22438a688239618fc7a73cf3aa30ec614568d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013에서 ID 프레젠테이션 호출

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server 2010을 사용 하면 호출 된 파티의 전화 번호 (전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, 개인 분기 교환 (PBX) 또는 SIP 트렁크)으로 변환할 수 있습니다. 이렇게 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 하나 이상의 번역 규칙을 정의 해야 합니다.

<div>


> [!IMPORTANT]  
> 하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 기능은 트렁크 피어에서 번역 규칙을 구성 하는 <EM>대신</EM> 사용 하도록 설계 되었습니다. 두 규칙이 충돌할 수 있기 때문에 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요.



</div>

다음 방법 중 하나를 사용 하 여 번역 규칙을 만들거나 수정할 수 있습니다.

  - **번역 규칙 작성** 도구를 사용 하 여 시작 숫자, 길이, 제거할 숫자, 추가할 숫자에 대 한 값을 지정한 다음 Lync Server 제어판에서 해당 하는 일치 패턴 및 번역 규칙을 생성 하도록 합니다.

  - 정규식을 수동으로 작성 하 여 일치 패턴 및 번역 규칙을 정의 합니다.

<div>


> [!NOTE]  
> 정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>을 참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Lync Server 2013에서 수동으로 번역 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 발신자 ID 프레젠테이션](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

