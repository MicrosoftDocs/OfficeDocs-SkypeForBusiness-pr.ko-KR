---
title: Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1adafdb90b9ea42d3694410b2103ef0e46aa70b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

페더레이션을 호스트 하는 데 사용 된 오류가 발생 한에 지 풀이 다시 온라인 상태가 된 후에이 절차를 사용 하 여 Lync Server 페더레이션 경로 및/또는 XMPP 페더레이션 경로를 장애 복구 하 여 복원 된이에 지 풀을 다시 사용 합니다.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>복원 된에 지 풀로 페더레이션 장애 복구

1.  이제 다시 사용할 수 있는에 지 풀에서에 지 서비스를 시작 합니다.

2.  복원 된에 지 서버를 사용 하도록 Lync Server 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.
    
      - 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **에지 풀**을 확장하고 현재 페더레이션에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집**을 선택합니다.
    
      - **일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인**을 클릭합니다.
    
      - 에 **지 풀**을 확장 한 다음 페더레이션에 사용할 원래에 지 서버 또는에 지 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **에지 속성**을 선택합니다.
    
      - **일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인**을 클릭합니다.
    
      - **작업**을 클릭하고, **토폴로지**, **게시**를 차례로 클릭합니다. **토폴로지 게시** 프롬프트가 표시되면 **다음**을 클릭합니다. 게시가 완료되면 **마침**을 클릭합니다.
    
      - 에지 서버에서 Lync Server 배포 마법사를 엽니다. **Lync Server 시스템 설치 또는 업데이트**를 클릭한 후 **Lync Server 구성 요소 설치 또는 제거**를 클릭합니다. **다시 실행**을 클릭합니다.
    
      - Lync Server 구성 요소 설치에서 **다음**을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 **로그 보기**를 클릭하여 사용 가능한 로그 파일을 확인합니다. **마침**을 클릭하여 배포를 완료합니다.

3.  복원 된에 지 서버를 사용 하도록 XMPP 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.
    
      - 다음 cmdlet을 실행 하 여 xmpp 페더레이션을 호스팅할에 지 풀에 대 한 XMPP 페더레이션 경로를 다시 가리키도록 합니다 (이 예에서는 EdgeServer1).
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스트 하는에 지 풀이 포함 된 사이트이 고 EdgeServer1.contoso.com는 해당 풀에 있는에 지 서버의 FQDN입니다.
    
      - 이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.
        
            _xmpp-server._tcp.contoso.com
    
      - 외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.
    
      - 이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.

4.  오류가 발생 하 여 복원 된에 지 풀이 포함 된 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있으면 이러한 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트 하 여 로컬 사이트에서에 지 풀을 다시 사용 해야 합니다. 자세한 내용은 [Lync Server 2013에서 프런트 엔드 풀과 연결 된에 지 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하십시오.

5.  오류가 발생 한에 지 풀과 동일한 사이트의 프런트 엔드 풀에도 오류가 발생 한 경우에는 Invoke – Invoke-cspoolfailback을 사용 하 여 프런트 엔드 풀을 장애 조치할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013의에 지 서버 재해 복구](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

