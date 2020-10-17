---
title: 'Lync Server 2013: 토폴로지 작성기에서 중재 서버 정의'
description: 'Lync Server 2013: 토폴로지 작성기에서 중재 서버를 정의 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2159b06c5587a17d24928febc11a883bc1520778
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567794"
---
# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 작성기에서 중재 서버 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-25_

토폴로지 작성기를 사용 하 여 독립 실행형 중재 서버 또는 이전에 Enterprise Voice를 배포 하지 않은 사이트의 프런트 엔드 풀이 있는 풀 배치 된을 정의 하려면이 항목의 단계를 수행 합니다.

Administrators 그룹의 구성원 계정을 사용하여 토폴로지를 정의할 수 있습니다.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>프런트 엔드 풀에 대 한 중재 서버 배치 된 정의

토폴로지 작성기를 사용 하 여 엔터프라이즈 음성이 이전에 배포 되지 않은 사이트의 프런트 엔드 풀로 중재 서버 배치 된를 정의 하려면이 항목의 단계를 수행 합니다.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>프런트 엔드 풀에 중재 서버를 추가 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기의 콘솔 트리에서 프런트 엔드 풀을 정의할 사이트의 이름을 확장 합니다.

3.  콘솔 트리에서 원하는 프런트 엔드 풀 유형을 마우스 오른쪽 단추로 클릭 하 고 **새 프런트 엔드 풀 ...** 을 클릭 합니다.

4.  **배치된 서버 역할 선택** 페이지에 도달할 때까지 **새 프런트 엔드 풀 정의** 마법사를 진행합니다.

5.  **배치 된 서버 역할 선택**에서 **함께 배치할 중재 서버**옵션을 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>선택한 프런트 엔드 풀 유형이 Enterprise Edition 이면 해당 프런트 엔드 풀의 모든 프런트 엔드 서버에 중재 서버 구성 요소를 설치 합니다.</P>
    > <LI>
    > <P>중재 서버에서 사용 되는 <STRONG>다음 홉 풀</STRONG> 은 중재 서버가 배치 된 되는 프런트 엔드 풀이 됩니다.</P>
    > <LI>
    > <P>중재 서버에서 사용 되는에 <STRONG>지 풀</STRONG> 은 중재 서버가 배치 된 프런트 엔드 풀과 연결 된 동일한에 지 풀입니다.</P></LI></UL>

    
    </div>

6.  이 프런트 엔드 풀을 사용 하 여 Microsoft Office Communications Server 2007 2 r 2의 통화를 PSTN으로 라우팅하도록 **기본값으로 설정** 을 클릭 합니다.

7.  하나 이상의 피어를 프런트 엔드 풀에 연결 하는 작업이 끝나면 **마침을** 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > Enterprise Voice 배포 프로세스의 다음 단계로 진행 하기 전에 중재 서버 풀 (즉, 중재 서버 구성 요소가 배치 된 인 프런트 엔드 풀)이 지정한 Fqdn을 사용 하 고 있는지 확인 합니다.

    
    </div>

8.  그런 다음 필요에 따라 중재 서버의 수신 대기 포트를 수정 하는 다음 단계를 진행 하기 전에 배포 가이드 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 중재 서버를 토폴로지에 추가 합니다. 토폴로지 작성기를 사용 하 여 토폴로지를 정의 하거나 수정할 때마다 토폴로지를 게시 해야 합니다.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>독립 실행형 중재 서버 정의

엔터프라이즈 음성이 이전에 배포 되지 않은 사이트에서 토폴로지 작성기를 사용 하 여 독립 실행형 중재 서버 또는 풀을 정의 하려면이 항목의 단계를 수행 하세요.

이 사이트의 프런트 엔드 풀에 배치 된 중재 서버를 이미 배포한 경우 [Lync server 2013에서 트렁크 구성을](lync-server-2013-configuring-trunks.md)진행 하기 전에이 섹션을 건너뛰고 [lync Server 2013에서 중재 서버용 파일을 설치할](lync-server-2013-install-the-files-for-mediation-server.md) 수 있습니다.

<div>


> [!NOTE]  
> 이 섹션에서는 배포 가이드 설명서의 lync server <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard Edition Server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프런트 엔드 풀을 이미 설정 하 <A href="lync-server-2013-publish-the-topology.md">2013</A> 고 있습니다.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>중재 서버를 추가하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기의 콘솔 트리에서 중재 서버를 정의 하려는 사이트의 이름을 확장 합니다.

3.  콘솔 트리에서 **중재 풀** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **중재 서버 풀**을 클릭 합니다.

4.  **새 중재 풀 정의**에 중재 서버 풀 FQDN (정규화 된 도메인 이름)을 입력 합니다.

5.  다음 중 하나를 수행합니다.
    
      - 고가용성을 제공 하기 위해 풀에 여러 중재 서버를 배포 하려면 **다중 컴퓨터 풀**을 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > 여러 중재 서버가 있는 중재 서버 풀을 지원 하려면 DNS 부하 분산을 배포 해야 합니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013에서 dns 부하 분산</A> 의 중재 서버 풀에서 Dns 부하 분산 사용 섹션을 참조 하십시오.

        
        </div>
    
      - 고가용성이 필요 하지 않으므로 풀에 중재 서버를 하나만 배포 하려면 **단일 컴퓨터 풀**을 선택 합니다. 다음 단계를 건너뜁니다.

6.  이전 단계에서 **다중 컴퓨터 풀**을 선택한 경우 **이 풀의 컴퓨터 정의** 항목에서 **컴퓨터 FQDN**을 클릭하고 풀의 각 서버에 대한 FQDN을 입력한 다음 **추가**를 클릭합니다. 풀에 추가 하려는 모든 중재 서버에 대해이 단계를 반복 합니다. 풀의 모든 컴퓨터를 정의했으면 **다음**을 클릭합니다.

7.  **다음 홉 선택** 페이지에서 **다음 홉 풀**을 클릭 하 고이 중재 서버 풀을 사용할 프런트 엔드 풀의 FQDN을 클릭 한 후 **다음**을 클릭 합니다.

8.  **에지 서버 선택** 페이지에서 다음 중 하나를 수행합니다.
    
      - Enterprise Voice에 대해 사용 하도록 설정 된 외부 사용자에 게 PSTN 연결을 제공 하려면이 **중재 서버에서 사용 하는에 지 풀 선택**에서이 중재 서버 풀을 사용 하는에 지 서버 풀의 FQDN을 클릭 하 여 해당 외부 사용자에 게 PSTN 연결을 제공 하 고 **다음**을 클릭 합니다.
    
      - Enterprise Voice에 대 한 외부 사용자를 사용 하도록 설정 하지 않거나 내부 네트워크 외부에 있는 사용자에 게 PSTN 연결을 제공 하지 않으려는 경우 **다음**을 클릭 합니다.

9.  다음에는 배포 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 중재 서버를 토폴로지에 추가 합니다. 데이터를 사용 하 여 Lync Server를 실행 하는 서버에 대 한 파일을 설치할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 작성 하거나 수정할 때마다 토폴로지를 게시 해야 합니다. 필요한 경우 다음 단계를 진행하여 중재 서버의 수신 대기 포트를 수정합니다.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>중재 서버 수신 대기 포트 정의

토폴로지 작성기를 사용 하 여 중재 서버 또는 풀이 게이트웨이 피어에서 들어오는 연결을 수락 하는 수신 대기 포트를 정의 하려면이 항목의 단계를 수행 하십시오.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>중재 서버 수신 대기 포트를 수정 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기의 콘솔 트리에서 **중재 풀** 노드를 확장 하 고 이전에 만든 중재 서버를 마우스 오른쪽 단추로 클릭 합니다.

3.  기본적으로 중재 서버의 SIP 수신 대기 포트는 Lync Server의 TLS 트래픽에 대 한 5070이 고 피어 (게이트웨이, PBXes 또는 sbc)의 TLS 트래픽을 위한 5067입니다. TCP 포트는 기본적으로 사용하지 않도록 설정됩니다. 게이트웨이가 TLS를 지원하지 않는 경우 TCP 포트를 사용하도록 설정해야 합니다.

4.  적절 한 TLS 또는 TCP 수신 대기 포트 범위 지정 중재 서버가 PSTN 게이트웨이에서 들어오는 연결을 수락 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>TCP 포트 사용</STRONG>을 선택하지 않은 경우 TCP 포트 범위를 입력할 필요가 없습니다. 이 설정은 선택 사항입니다.

    
    </div>

그런 다음 lync server [2013의 토폴로지 작성기에서 게이트웨이를 정의](lync-server-2013-define-a-gateway-in-topology-builder.md) 하 고 [lync Server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md)의 절차에 따라 풀의 각 중재 서버에 파일을 설치 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

