---
title: 'Lync Server 2013: 토폴로지 작성기에서 추가 trunks 정의'
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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 작성기에 추가 trunks 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

토폴로지 작성기를 사용 하 여 *피어* 를 중재 서버와 연결할 수 있는 추가 트렁크를 정의 하려면 다음 단계를 따르세요. 피어는 PSTN (공개 통신 네트워크) 연결을 통해 엔터프라이즈 음성을 사용할 수 있는 사용자를 제공 합니다. 피어는 ITSP (인터넷 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (세션 경계 컨트롤러) 일 수 있습니다. 트렁크는 중재 서버와 피어 간에이 연결을 정의 합니다. 중재 서버 마다 여러 trunks를 정의할 수 있습니다. 중재 서버는 여러 피어와 연결 될 수 있습니다.

트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.

{중재 서버 FQDN, 중재 서버 수신 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 포트}

<div>


> [!NOTE]  
> 이 항목에서는 배포 설명서의 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013에서 토폴로지 작성기의 게이트웨이 정의</A> 에 설명 된 대로 하나 이상의 collocated 또는 독립 실행형 중재 서버 또는 풀을 사용 하 여 PSTN 게이트웨이 및 루트 트렁크를 설정 하는 것으로 가정 합니다.



</div>

<div>


> [!NOTE]  
> 이 항목에서는 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013에서 프런트 엔드 풀 또는 Standard edition 서버 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프론트 엔드 풀이나 standard edition server를 설치 하 고 배포 설명서의 <A href="lync-server-2013-publish-the-topology.md">lync server 2013에서 토폴로지를 게시</A> 한다고 가정 합니다.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  Lync Server 2013, 사이트 이름, **공유 구성 요소**에서 **Trunks** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 트렁크**를 클릭 합니다.
    
    ![Lync Server 토폴로지 작성기 파일 구조 화면](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 토폴로지 작성기 파일 구조 화면")

3.  **새 트렁크 정의**에서 트렁크를 고유 하 게 식별 하는 대화명을 지정 합니다. 두 개의 trunks 같은 이름을 사용할 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > 전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다.

    
    </div>

4.  **연결 된 PSTN 게이트웨이에서**이 트렁크와 연결할 pstn 게이트웨이 피어를 선택 합니다.
    
    ![트렁크의 PSTN 게이트웨이 피어에 대한 속성 설정](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "트렁크의 PSTN 게이트웨이 피어에 대한 속성 설정")

5.  **Pstn 게이트웨이의 수신 대기 포트**에서 피어 (pstn 게이트웨이, IP-PBX 또는 SBC)가이 트렁크와 연결할 중재 서버에서 SIP 메시지를 수신 하는 수신 대기 포트를 입력 합니다. 기본 피어 포트는 TCP (전송 제어 프로토콜) 및 TLS (전송 계층 보안) 용 5067의 5066입니다. 기본 Survivable Branch 기기 포트는 TCP 및 TLS 용 5082의 5081입니다.

6.  **SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.

    
    </div>

7.  **연결 된 중재 서버**에서이 피어의 루트 트렁크에 연결할 중재 서버 풀을 선택 합니다.

8.  **연결 된 중재 서버 포트**에서 중재 서버가 피어에서 SIP 메시지를 수신할 수신 대기 포트를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013의 여러 트렁크 지원 기능을 사용 하는 경우 다른 트렁크 이름을 사용 하는 두 개의 trunks 동일한 <STRONG>연결 된 중재 서버 포트</STRONG> 와 <STRONG>IP/PSTN 게이트웨이에 대 한 수신 대기 포트</STRONG> 를 사용 하 여 구성할 수 없습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013의 여러 트렁크 지원 기능을 사용 하면 여러 피어와 통신 하기 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 <STRONG>연결 된 중재 서버 포트</STRONG> 번호는 중재 서버에서 허용 하는 해당 프로토콜에 대 한 수신 대기 포트 범위 내에 있어야 합니다. 이 포트 범위는 Lync Server 2013 및 중재 서버 풀 아래에 정의 되어 있습니다. 관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다. <STRONG>수신 대기 포트</STRONG> 필드에 포트 범위를 지정 합니다.

    
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

