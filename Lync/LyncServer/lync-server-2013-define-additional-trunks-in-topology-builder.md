---
title: 'Lync Server 2013: 토폴로지 작성기에서 추가 트렁크 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8e5650492cc51b024b03cc0c92f64ff46d818b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504645"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 작성기에서 추가 트렁크 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

다음 단계에 따라 토폴로지 작성기를 사용 하 여 *피어* 를 중재 서버에 연결할 수 있는 추가 트렁크를 정의 합니다. 피어는 공중 전화망 (PSTN)에 대 한 연결을 사용 하 여 Enterprise Voice를 사용할 수 있도록 하는 사용자를 제공 합니다. 피어는 ITSP (인터넷 전화 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (Session Border Controller) 일 수 있습니다. 트렁크는 중재 서버와 피어 간에이 연결을 정의 합니다. 중재 서버 마다 여러 트렁크를 정의할 수 있습니다. 중재 서버는 여러 피어와 연결 될 수 있습니다.

트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.

{중재 서버 FQDN, 중재 서버 수신 대기 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 대기 포트}

<div>


> [!NOTE]  
> 이 항목에서는 배포 설명서에서 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013의 토폴로지 작성기</A> 에서 기술 정의에 설명 된 대로 하나 이상의 배치 된 또는 독립 실행형 중재 서버 또는 풀을 사용 하 여 PSTN 게이트웨이 및 루트 트렁크를 설정 했다고 가정 합니다.



</div>

<div>


> [!NOTE]  
> 이 항목에서는 배포 설명서의 lync server <A href="lync-server-2013-publish-the-topology.md">2013</A> <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard edition server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프런트 엔드 풀 또는 standard edition 서버를 적어도 하나의 중앙 사이트에 설정 했다고 가정 합니다.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>중재 서버와 게이트웨이 피어 사이에 추가 트렁크를 정의 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  Lync Server 2013, 사이트 이름, **공유 구성 요소**에서 **트렁크** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 트렁크**를 클릭 합니다.
    
    ![Lync Server 토폴로지 작성기 파일 구조 화면](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 토폴로지 작성기 파일 구조 화면")

3.  **새 트렁크 정의**에서 트렁크를 고유 하 게 식별 하는 이름을 지정 합니다. 이름이 같은 두 트렁크를 사용할 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > TLS (전송 계층 보안)를 전송 유형으로 지정 하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정 해야 합니다.

    
    </div>

4.  **연결 된 pstn 게이트웨이에서**이 트렁크와 연결할 PSTN 게이트웨이 피어를 선택 합니다.
    
    ![트렁크에 대 한 PSTN 게이트웨이 피어에 대 한 속성 설정](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "트렁크에 대 한 PSTN 게이트웨이 피어에 대 한 속성 설정")

5.  **Pstn 게이트웨이의 수신 대기 포트**에서 피어 (pstn 게이트웨이, IP-PBX 또는 SBC)가이 트렁크와 연결할 중재 서버 로부터 SIP 메시지를 받을 수신 대기 포트를 입력 합니다. 기본 피어 포트는 TCP (전송 제어 프로토콜)의 경우 5066이 고 TLS (전송 계층 보안)의 경우 5067입니다. 기본 Sba (survivable Branch 기기 포트는 TCP의 경우 5081이 고 TLS의 경우 5082입니다.

6.  **SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.

    
    </div>

7.  **연결 된 중재 서버**에서이 피어의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.

8.  **연결 된 중재 서버 포트**에 중재 서버가 피어에서 SIP 메시지를 받을 수신 대기 포트를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013에서 여러 트렁크 지원을 사용 하는 경우 서로 다른 트렁크 이름을 사용 하는 두 개의 트렁크를 <STRONG>IP/PSTN 게이트웨이와</STRONG> 동일한 <STRONG>연결 된 중재 서버 포트</STRONG> 및 수신 대기 포트로 구성할 수 없습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013의 트렁크 지원을 여러 개 사용 하는 경우 여러 피어와 통신 하기 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 <STRONG>연결 된 중재 서버 포트</STRONG> 번호는 중재 서버에서 허용 하는 해당 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다. 이 포트 범위는 Lync Server 2013 및 중재 서버 풀에 정의 되어 있습니다. 관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다. <STRONG>수신 대기 포트</STRONG> 필드에서 포트 범위를 지정합니다.

    
    </div>

9.  **확인**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 토폴로지 작성기에서 트렁크 수정](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

