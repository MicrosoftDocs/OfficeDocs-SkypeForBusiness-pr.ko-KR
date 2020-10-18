---
title: 'Lync Server 2013: 온-프레미스 통합 메시징 통합을 위한 지침'
description: 'Lync Server 2013: 온-프레미스 통합 메시징의 통합을 위한 지침입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814c927aa36199737712328d3b92c64a8e967a55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576644"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>온-프레미스 통합 메시징과 Lync Server 2013의 통합 지침

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-25_

다음은 Enterprise Voice를 배포할 때 고려해 야 할 지침 및 모범 사례입니다.

<div>


> [!IMPORTANT]  
> Exchange UM (통합 메시징)은 c u 3을 함께 사용 하는 경우에만 i p v를 지원 합니다.



</div>

  - Lync Server 2013 Standard Edition Server 또는 프런트 엔드 풀을 배포 합니다. 설치에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하십시오.

  - Exchange 관리자와 함께 원활하고 성공적인 통합을 위해 각자가 수행할 작업을 확인합니다.

  - Exchange UM에 대해 사용자를 사용 하도록 설정할 각 Exchange UM (통합 메시징) 포리스트에 Exchange 사서함 서버 역할을 배포 합니다. Exchange 서버 역할을 설치 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서를 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange UM (통합 메시징)을 설치 하면 자체 서명 된 인증서를 사용 하도록 구성 됩니다.<BR>그러나 자체 서명 된 인증서를 사용 하는 경우 Lync Server 2013 및 Exchange UM에서 서로를 신뢰 하지 않으므로 두 서버에서 모두 신뢰 하는 인증 기관과 별도의 인증서를 요청 해야 합니다.

    
    </div>

  - Lync Server 2013 및 Exchange UM이 서로 다른 포리스트에 설치 된 경우 lync server 2013 포리스트와 Lync Server 2013 포리스트를 트러스트 하도록 각 exchange 포리스트를 구성 합니다. 또한 일반적으로 스크립트 또는 ILM (Identity 수명 주기 관리자) 같은 크로스 포리스트 도구를 사용 하 여 Lync Server 2013 포리스트의 사용자 개체에 대 한 사용자의 Exchange UM 설정을 설정 합니다.

  - 필요한 경우 통합 메시징 서버를 관리할 Exchange 관리 콘솔을 설치합니다.

  - Outlook Voice Access 및 자동 전화 교환을 위한 유효한 전화 번호를 받습니다.

  - Microsoft Exchange Server 2010 SP1 (서비스 팩 1) 이전 버전의 Exchange UM을 사용 하는 경우 Exchange UM SIP URI 다이얼 플랜 및 Enterprise Voice 다이얼 플랜에 대 한 좌표 이름입니다.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>중복 Exchange UM 서버 배포

<div>


> [!IMPORTANT]  
> 조직에 대해 구성 하는 각 Exchange UM SIP URI 다이얼 플랜에 대해 Exchange UM 서비스가 실행 되는 최소 두 대의 서버를 배포 하는 것이 좋습니다. 확장 된 용량을 제공 하는 것 외에도 중복 서버를 배포 하면 고가용성이 제공 됩니다. 서버 오류가 발생할 경우 Lync Server 2013를 다른 서버로 장애 조치 (failover) 하도록 구성할 수 있습니다.



</div>

다음 구성 예에서는 Exchange UM 복구를 제공합니다.

**예 1: Exchange UM 복구**

![Exchange UM 예제 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 예제 1")

예 1에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다. Tukwila의 Exchange UM 중단 시에는 DNS (Domain Name System)가 서버 3과 4를 가리키도록 구성 해야 합니다. Exchange UM 중단 시간이 더블린 이면 서버 3과 4에 대 한 DNS A 레코드를 각각 서버 1과 2를 가리키도록 구성 해야 합니다.

<div>


> [!NOTE]  
> 예 1의 경우 각 Exchange UM 서버에서 다음 인증서 중 하나를 할당해야 합니다. 
> <UL>
> <LI>
> <P>SAN(주체 대체 이름)에 와일드카드가 포함된 인증서 사용</P>
> <LI>
> <P>SAN에 있는 4 대의 Exchange UM 서버 각각의 FQDN (정규화 된 도메인 이름)을 배치 합니다.</P></LI></UL>



</div>

**예 2: Exchange UM 복구**

![Exchange UM 예제 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 예제 2")

예 2의 경우 정상 작동 조건에서 Exchange UM 서버 1과 2는 Tukwila 데이터 센터에서 사용되고, Exchange UM 서버 3과 4는 Dublin 데이터 센터에서 사용됩니다. 네 서버 모두 Tukwila 사용자의 SIP URI 다이얼 플랜에 포함되어 있지만 서버 3과 4는 사용하지 않도록 설정되어 있습니다. Tukwila에서 Exchange UM의 작동이 중단된 경우 예를 들어 Exchange UM 서버 1과 2가 사용할 수 없게 되고, Exchange UM 서버 3과 4를 사용할 수 있으므로 Tukwila Exchange UM 트래픽이 Dublin의 서버로 라우팅됩니다.

Exchange 2013에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은의 "Exchange 2013 UM과 Lync Server 통합"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

Microsoft Exchange Server 2010에서 통합 메시징을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.

  - "Exchange 2010에서 통합 메시징 사용" [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418)

  - "Exchange 2010에서 통합 메시징 사용 안 함" [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416)

</div>

<div>

## <a name="see-also"></a>참고 항목


[온-프레미스 통합 메시징과 Lync Server 2013의 통합을 위한 배포 프로세스](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

