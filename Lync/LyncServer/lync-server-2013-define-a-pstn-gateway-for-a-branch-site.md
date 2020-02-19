---
title: 'Lync Server 2013: 분기 사이트에 대 한 PSTN 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08e2010b79213607992ab383b606e7b609ca75e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Lync Server 2013에서 분기 사이트에 대 한 PSTN 게이트웨이 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

하나 이상의 프런트 엔드 풀 또는 Standard Edition server를 포함 하는 중앙 사이트에서이 절차를 수행 합니다.

<div>


> [!IMPORTANT]  
> 절차를 수행하기 전에 다음 조건을 충족해야 합니다. 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp;통신 소프트웨어는 중앙 사이트에서 설정 해야 합니다.</P>
> <LI>
> <P>중재 서버를 중앙 사이트에 배포 해야 합니다.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>PSTN 게이트웨이를 정의하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.

2.  콘솔 트리에서 중앙 사이트, **지점 사이트**를 차례로 확장한 다음 PSTN(공중 전화망) 게이트웨이를 정의할 분기 사이트의 이름을 확장한 후 **공유 구성 요소**를 확장합니다.

3.  **PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭한 다음 **새 IP/PSTN 게이트웨이**를 클릭합니다.

4.  **새 IP/PSTN 게이트웨이 정의** 대화 상자에서 **게이트웨이 FQDN 또는 IP 주소**를 클릭한 다음 분기 사이트에 배포할 게이트웨이의 FQDN(정규화된 도메인 이름) 또는 IP 주소를 입력합니다.

5.  **IP/PSTN 게이트웨이용 수신 대기 포트**를 클릭한 다음 기본값을 수락합니다.

6.  **SIP 전송 프로토콜** 목록에서 게이트웨이가 사용하는 전송 프로토콜을 클릭한 다음 **확인**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 보안을 위해 TLS(전송 계층 보안)를 지원하는 PSTN 게이트웨이를 사용하는 것이 좋습니다.

    
    </div>

<div>


> [!TIP]  
> PSTN 게이트웨이의 속성을 수정하려면 <STRONG>Set-CsPstnGateway</STRONG> cmdlet을 사용합니다. 자세한 내용은 Lync Server 관리 셸 도움말에서 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">설정-CsPstnGateway</A>를 참조 하십시오.



</div>

분기 사이트 복구의 **다음 단계** : [Lync Server 2013에서 분기 사이트 복구를 위한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 PSTN 게이트웨이 배포 옵션](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

