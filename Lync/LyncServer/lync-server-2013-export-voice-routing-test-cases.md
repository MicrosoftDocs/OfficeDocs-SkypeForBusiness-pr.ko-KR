---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e47158d9ea3da6f04a1424026c7edb73c1d482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

테스트 사례를 통해 조직의 음성 경로를 테스트 하는 데 사용할 수 있는 번호와 사용할 다이얼 플랜 및 음성 정책 등을 정의 하 고 Lync Server가 해당 조건을 지정 하 여 제공 된 번호를 확인할 수 있습니다. PSTN 네트워크로 라우팅 했습니다.

Lync Server 제어판을 사용 하 여 만들 수 있는 테스트 사례는 일반적으로 해당 사례가 처음 만들어지고 실행 된 서버에만 저장 됩니다. 그러나 이러한 테스트 사례를 XML 파일로 내보낸 다음 (vtest 확장명 사용) 다른 서버에서 가져올 수 있습니다. 이렇게 하면 토폴로지의 여러 지점에 있는 여러 컴퓨터에서 동일한 테스트를 실행할 수 있습니다.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>음성 라우팅 테스트 사례를 내보내려면

1.  Lync Server 제어판에서 **음성 라우팅을** 클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.

2.  **음성 라우팅 테스트** 탭에서 내보낼 테스트 사례 (또는 테스트 사례)를 선택 합니다. 여러 테스트 사례를 선택 하려면 내보낼 첫 번째 사례를 클릭 한 다음 Ctrl 키를 누른 상태에서 내보낼 추가 사례를 선택 합니다.

3.  **작업**을 클릭 한 다음 **테스트 사례 내보내기를**클릭 합니다.

4.  **다른 이름으로 저장** 대화 상자에서 내보낸 테스트 사례를 저장할 폴더를 선택 하 고 **파일 이름** 상자에 결과 XML 파일의 이름을 입력 합니다. 여러 테스트 사례를 내보내는 경우 이러한 모든 테스트 사례가 단일 XML 파일에 저장 됩니다.

5.  테스트 사례를 저장 하려면 **저장**을 클릭 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

