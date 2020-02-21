---
title: 'Lync Server 2013: 토폴로지 작성기에서 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0c03c286b5d9ad57f1422478bed6b7c3048a73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

다음 단계에 따라 토폴로지 작성기를 사용 하 여 Enterprise Voice를 사용할 수 있도록 설정 된 사용자에 대해 중재 서버를 연결 하 여 공중 전화망 (PSTN)에 대 한 연결을 제공 하는 *피어* 를 정의 합니다. 중재 서버에 대 한 피어는 SIP 트렁크를 구성 하 여 연결 하는 ITSP (인터넷 전화 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (Session Border Controller) 일 수 있습니다.

<div>


> [!NOTE]  
> 이 항목에서는 배포 설명서의 lync server <A href="lync-server-2013-publish-the-topology.md">2013</A> <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard edition server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 내부 프런트 엔드 풀 또는 standard edition server를 배치 된 또는 독립 실행형 중재 서버를 사용 하 여 한 개 이상 중앙 사이트에 설정 했다고 가정 합니다. 이 항목에서는 인프라에서 lync server <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">2013의 Enterprise voice 용 소프트웨어 필수 구성</A> 요소에 설명 된 필수 구성 요소와 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013의 enterprise voice에 대 한 보안 및 구성 필수 구성 요소</A>를 참조 하는 것을 확인 한 것으로 가정 합니다.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>중재 서버의 피어를 정의하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  Lync Server 2013, 사이트 이름, 공유 구성 요소에서 **PSTN 게이트웨이** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 PSTN 게이트웨이**를 클릭 합니다.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  **Define New IP/PSTN Gateway**에서 피어의 FQDN(정규화된 도메인 이름) 또는 IP 주소를 입력하고 **다음**을 클릭합니다.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > TLS (전송 계층 보안)를 전송 유형으로 지정 하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정 해야 합니다.

    
    </div>

4.  새 PSTN 게이트웨이의 IP 주소에 대한 수신 노드(IPv4 또는 IPv6)를 정의하고 **다음**을 클릭합니다.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  PSTN 게이트웨이에 대한 *루트 트렁크*를 정의합니다. 트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.
    
    {중재 서버 FQDN, 중재 서버 수신 대기 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 대기 포트}
    
      - 토폴로지 작성기에서 PSTN 게이트웨이를 정의할 때 토폴로지에 PSTN 게이트웨이를 성공적으로 추가 하려면 루트 트렁크를 정의 해야 합니다.
    
      - 연결된 PSTN 게이트웨이를 제거할 때까지는 루트 트렁크를 제거할 수 없습니다.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  **IP/PSTN 게이트웨이의 수신 대기 포트**에서 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결 될 중재 서버의 SIP 메시지에 대해 사용할 수신 대기 포트를 입력 합니다. 기본적으로 TCP(Transmission Control Protocol)의 경우 포트 5066, PSTN 게이트웨이, PBX 또는 SBC의 TLS(전송 계층 보안)의 경우 포트 5067이 사용됩니다. 분기 사이트의 Sba (survivable 분기 기기에서 기본 포트는 TCP의 경우 5081이 고 TLS의 경우 5082입니다.

7.  **SIP 전송 프로토콜**에서 피어가 사용하는 전송 유형을 클릭하고 **확인**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.

    
    </div>

8.  **연결 된 중재 서버**에서이 PSTN 게이트웨이의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.

9.  **연결 된 중재 서버 포트**에 중재 서버가 게이트웨이에서 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013의 트렁크 지원을 여러 개 사용 하는 경우 여러 PSTN 게이트웨이와 통신 하는 데 사용할 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다. 트렁크를 정의할 때 연결 된 <STRONG>중재 서버 포트</STRONG> 는 중재 서버에서 허용 하는 해당 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다. 이 포트 범위는 Lync Server 2013 및 중재 풀에 정의 되어 있습니다. 관심 있는 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다. <STRONG>수신 대기 포트</STRONG> 필드에서 포트 범위를 지정합니다.

    
    </div>

10. **마침**을 클릭합니다.

<div>


> [!IMPORTANT]  
> 이 단계를 마치기 전에 정의한 피어가 실행 중이고 사용자가 지정한 FQDN 또는 IP 주소를 사용 중인지 확인합니다.



</div>

다음으로, 토폴로지에 피어를 추가 하려면 배포 설명서에서 [Lync Server 2013의 토폴로지 게시](lync-server-2013-publish-the-topology.md) 에 나와 있는 절차를 수행 합니다. Lync Server를 실행 하는 서버에 대 한 파일을 설치 하는 데 데이터를 사용할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 작성 하거나 수정할 때마다 토폴로지를 게시 해야 합니다.

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

