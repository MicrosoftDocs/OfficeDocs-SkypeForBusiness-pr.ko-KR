---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d871379f9c9be161aec879b7ca8da16ac40e2b5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

테스트 사례를 통해 조직에서 음성 경로를 테스트할 수 있습니다. 전화를 걸고 사용할 번호와 다이얼 플랜 및 음성 정책을 함께 정의 하 고 Lync Server가 제공 된 번호를 확인할 수 있는지 확인 합니다. PSTN 네트워크로 경로를 설정 했습니다.

Lync Server 제어판을 사용 하 여 만들 수 있는 테스트 사례는 일반적으로 대/소문자를 처음 만든 후 실행 한 서버에만 저장 됩니다. 하지만 이러한 테스트 사례를 XML 파일(.vtest 확장명)로 내보내고 다른 서버에서 가져올 수 있습니다. 이러한 방식을 통해 토폴로지의 여러 지점에 있는 서로 다른 컴퓨터에서 동일한 테스트를 실행할 수 있습니다.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>음성 라우팅 테스트 사례를 내보내려면

1.  Lync Server 제어판에서 **음성 라우팅을** 클릭 하 고 **음성 라우팅 테스트**를 클릭 합니다.

2.  **음성 라우팅 테스트** 탭에서 내보낼 테스트 사례를 선택합니다. 여러 테스트 사례를 선택하려면 내보낼 첫 번째 테스트 사례를 클릭한 후 Ctrl 키를 누른 상태로 내보낼 다른 테스트 사례를 계속 선택합니다.

3.  **동작**에서 **테스트 사례 내보내기**를 클릭합니다.

4.  **다른 이름으로 저장** 대화 상자에서 내보낸 테스트 사례를 저장할 폴더를 선택하고 **파일 이름** 상자에 결과 XML 파일의 이름을 입력합니다. 여러 테스트 사례를 내보낼 경우 모든 테스트 사례가 단일 XML 파일로 저장됩니다.

5.  테스트 사례를 저장하려면 **저장**을 클릭합니다.

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

