---
title: 'Lync Server 2013: 분기 사이트에 대한 PSTN 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Lync Server 2013에서 분기 사이트에 대한 PSTN 게이트웨이 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버가 포함 된 중앙 사이트에서이 절차를 수행 합니다.

<div>


> [!IMPORTANT]  
> 절차를 수행 하기 전에 다음 조건이 충족 되어야 합니다. 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp;통신 소프트웨어는 중앙 사이트에 설정 되어 있어야 합니다.</P>
> <LI>
> <P>중재 서버는 중앙 사이트에 배포 해야 합니다.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>PSTN 게이트웨이를 정의 하려면

1.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 중앙 사이트를 확장 하 고, **지점**사이트를 확장 하 고, 다음에 대 한 PSTN (공용 전환 전화 네트워크) 게이트웨이를 정의 하려는 지점 사이트의 이름을 확장 한 다음 **공유 구성 요소**를 확장 합니다.

3.  **PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭 한 다음 **새 IP/PSTN 게이트웨이**를 클릭 합니다.

4.  **새 IP/PSTN 게이트웨이 정의** 대화 상자에서 **게이트웨이 Fqdn 또는 IP 주소**를 클릭 한 다음 지점 사이트에서 배포 하려는 게이트웨이의 FQDN (정규화 된 도메인 이름) 또는 ip 주소를 입력 합니다.

5.  **IP/PSTN 게이트웨이의 수신 대기 포트**를 클릭 한 다음 기본값을 적용 합니다.

6.  **SIP 전송 프로토콜** 목록에서 게이트웨이에서 사용 하는 전송 프로토콜을 클릭 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 보안상의 이유로 TLS (전송 계층 보안)를 지 원하는 PSTN 게이트웨이를 사용 하는 것이 좋습니다.

    
    </div>

<div>


> [!TIP]  
> 이 <STRONG>(가) Cmdlet 집합-CsPstnGateway</STRONG> 를 사용 하 여 PSTN 게이트웨이의 속성을 수정 합니다. 자세한 내용은 Lync Server 관리 셸 도움말에서 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>를 참조 하세요.



</div>

지점 사이트 복원에 대 한 **다음 단계** : [Lync Server 2013에서 지점 사이트 복원에 대 한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

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

