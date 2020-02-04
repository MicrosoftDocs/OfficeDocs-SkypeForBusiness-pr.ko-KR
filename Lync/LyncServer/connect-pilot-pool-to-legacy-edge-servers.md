---
title: 레거시 에지 서버에 파일럿 풀 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>레거시 에지 서버에 파일럿 풀 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

Lync Server 2013을 배포한 후에는 사이트에 대 한 페더레이션 경로를 구성 해야 합니다. Lync Server 2010에서 사용 중인 페더레이션 경로를 사용 하려면이 경로를 사용 하도록 Lync Server 2013를 구성 해야 합니다.

Lync Server 2013 사이트에서 Lync Server 2010 배포의 디렉터 및 Edge 서버를 사용 하도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 합니다.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 레거시 Edge 풀을 연결 하려면

1.  **토폴로지 작성기**를 엽니다.

2.  **Lync Server** 노드 바로 아래에 있는 사이트를 선택 합니다.

3.  **작업** 메뉴에서 **속성 편집**을 클릭 합니다.

4.  왼쪽 창에서 **페더레이션 경로**를 선택 합니다.

5.  **사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택 하 고 lync server 2010 디렉터를 선택 하거나, 디렉터가 나열 되어 있지 않으면 Lync server 2010 Edge 서버를 선택 합니다.
    
    ![속성 편집, 페더레이션 경로 페이지](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")  

6.  **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.

7.  토폴로지 작성기의 Lync Server 2013 노드에서 **Standard edition Server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 여 해당 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

8.  **연결**에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 옆에 있는 확인란을 선택 합니다.

9.  목록에서 레거시에 지 서버를 선택 합니다.
    
    ![속성 편집 대화 상자, 레거시 에지 선택](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "속성 편집 대화 상자, 레거시 에지 선택")  

10. **확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.

11. **토폴로지 작성기**에서 최상위 노드, **Lync 서버**를 선택 합니다.

12. **작업** 메뉴에서 **토폴로지 게시**를 클릭 하 고 **다음**을 클릭 합니다.

13. **게시 마법사** 가 완료 되 면 **마침을**클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

