---
title: 레거시 에지 서버에 파일럿 풀 연결
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62ea7da56e77264a7d8c730d44e7a6ca0372d3f8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503085"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>레거시 에지 서버에 파일럿 풀 연결

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

Lync Server 2013을 배포한 후에는이 사이트에 대 한 페더레이션 경로가 구성 되지 않습니다. Office Communications Server 2007 R2에서 사용 중인 페더레이션 경로를 사용 하려면이 경로를 사용 하도록 Lync Server 2013을 구성 해야 합니다.

Lync Server 2013 사이트에서 BackCompatSite의 디렉터 및에 지 서버를 사용할 수 있도록 설정 하려면 토폴로지 작성기를 사용 하 여 레거시에 지 풀을 연결 합니다.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>토폴로지 작성기를 사용하여 레거시 에지 풀을 연결하려면

1.  토폴로지 작성기에서 파일럿 풀을 열려면

2.  Lync Server 2013 사이트를 선택 합니다.

3.  **동작** 메뉴에서 **속성 편집**을 클릭합니다.

4.  **사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 Office Communications server 2007 r2 디렉터 또는 디렉터를 나열 하지 않은 경우 Office communications Server 2007 r2에 지 서버를 선택 합니다.
    
    ![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")  

5.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.

6.  토폴로지 작성기의 Lync Server 2013 노드에서 **Standard edition Server** 또는 **Enterprise Edition 프런트 엔드 풀**로 이동 하 고 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

7.  **연결**에서 **에지 풀 연결(미디어 구성 요소)** 옆의 확인란을 선택합니다.

8.  목록에서 BackCompatSite에 대한 에지 서버 인터페이스를 선택합니다.
    
    ![속성 편집 대화 상자, 일반 페이지](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")  

9.  **확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.

10. **토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.

11. **동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 **다음**을 클릭합니다.

12. **게시 마법사**가 완료되면 **마침**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

