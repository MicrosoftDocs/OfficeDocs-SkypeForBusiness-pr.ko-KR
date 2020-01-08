---
title: 'Lync Server 2013: Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

Lync Server federation 구성 된 Edge 풀이 작동 하지 않으면 페더레이션에서 다른 Edge 풀을 사용 하 여 페더레이션을 변경 해야 합니다.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Lync Server Federation에 사용 되는 Edge 풀을 통한 장애 조치

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀**을 확장 한 다음, 현재 페더레이션에 대해 구성 된 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.

2.  **일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다. **확인**을 클릭합니다.

3.  **Edge 풀**을 확장 한 다음 현재 페더레이션에 사용할 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.

4.  **일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다. **확인**을 클릭합니다.

5.  **작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다. **토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다. 게시가 완료 되 면 **마침을**클릭 합니다.

6.  Edge 서버에서 Lync Server 배포 마법사를 엽니다. **Lync Server 시스템 설치 또는 업데이트**를 클릭 한 다음 **설정 또는 Lync Server 구성 요소 제거**를 클릭 합니다. **다시 실행**을 클릭 합니다.

7.  Lync Server 구성 요소를 설정 하 고 **다음**을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다. **마침을** 클릭 하 여 배포를 완료 합니다.
    
    실행 중인 프런트 엔드 서버가 실패 한 Edge 풀을 포함 하는 사이트에 포함 되어 있는 경우, 현재 실행 중인 원격 사이트의 Edge 풀을 사용 하도록 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 해야 합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 풀에 연결 된 Edge 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013의 에지 서버 재해 복구](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

