---
title: Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

페더레이션을 호스트 하는 데 사용 되는 실패 한 쪽 풀이 온라인 상태가 되 면이 절차를 사용 하 여 Lync Server 페더레이션 경로 및/또는 XMPP 페더레이션 경로를 다시 사용 하 여 복원 된이 Edge 풀을 사용할 수 있습니다.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>복원 된 Edge 풀로의 페더레이션을 장애 복구

1.  지금 다시 사용할 수 있는 Edge 풀에서 Edge 서비스를 시작 합니다.

2.  복원 된 Edge 서버를 사용 하기 위해 Lync Server 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.
    
      - 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀**을 확장 한 다음, 현재 페더레이션에 대해 구성 된 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.
    
      - **일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다. **확인**을 클릭합니다.
    
      - **Edge 풀**을 확장 한 다음 페더레이션에 사용할 원본 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.
    
      - **일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다. **확인**을 클릭합니다.
    
      - **작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다. **토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다. 게시가 완료 되 면 **마침을**클릭 합니다.
    
      - Edge 서버에서 Lync Server 배포 마법사를 엽니다. **Lync Server 시스템 설치 또는 업데이트**를 클릭 한 다음 **설정 또는 Lync Server 구성 요소 제거**를 클릭 합니다. **다시 실행**을 클릭 합니다.
    
      - Lync Server 구성 요소를 설정 하 고 **다음**을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다. **마침을** 클릭 하 여 배포를 완료 합니다.

3.  XMPP 페더레이션 경로를 장애 복구 하 여 복원 된 Edge 서버를 사용 하려는 경우 다음을 수행 합니다.
    
      - 다음 cmdlet을 실행 하 여 XMPP 페더레이션 경로를 다시 지정 합니다. 이제 XMPP 페더레이션 (이 예제에서는 EdgeServer1)을 호스트 하는 Edge 풀을 가리킵니다.
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer1.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.
    
      - 이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다. 이 SRV 레코드의 포트 값은 5269 이어야 합니다.
        
            _xmpp-server._tcp.contoso.com
    
      - 외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.
    
      - 이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.

4.  실패 한 Edge 풀을 포함 하는 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있는 경우에는 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 하 여 로컬 사이트의 Edge 풀을 다시 사용 해야 합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 풀에 연결 된 Edge 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하세요.

5.  실패 한 Edge 풀과 동일한 사이트의 프런트 엔드 풀에도 실패 한 경우에는 Invoke – CsPoolFailback를 사용 하 여 프런트 엔드 풀을 실패할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013의 에지 서버 재해 복구](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

