---
title: 'Lync Server 2013: 호스팅된 Exchange UM 라우팅'
description: 'Lync Server 2013: 호스팅된 Exchange UM 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550134"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange UM 라우팅

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Exchange UM 라우팅 응용 프로그램은 프런트 엔드 서버에서 실행 되어 호출을 온-프레미스 Microsoft Exchange UM (통합 메시징) 배포 또는 호스팅된 Exchange UM 서비스로 라우팅합니다.

<div>

## <a name="the-exum-routing-application"></a>ExUM 라우팅 응용 프로그램

Lync Server 2013 Exchange UM 라우팅 응용 프로그램은 다음 다이어그램에 나와 있는 것 처럼 사용자 계정 설정 및 호스팅된 음성 메일 정책 매개 변수의 정보를 사용 하 여 호스트 된 음성 메시징의 통화를 라우팅하는 방법을 결정 합니다.

**혼합 배포 Exchange UM 라우팅 예제**

![온-프레미스 Lync Server Exchange UM 배포](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")

Exchange UM 라우팅을 구성 하 여 온-프레미스 Exchange UM을 사용 하도록 설정 된 사용자, 호스트 된 Exchange UM을 사용할 수 있는 사용자 또는 둘의 조합으로 통화를 라우팅하도록 구성할 수 있습니다.

예를 들어 Roy의 사서함 및 Exchange UM 서비스가 온-프레미스 Exchange 배포에 있는 경우를 가정해 보겠습니다.

  - Roy의 사용자 계정에 대 한 프록시 주소 정보는 ExUM 라우팅 응용 프로그램에서 온-프레미스 Exchange UM 서버에 대 한 통화를 라우팅하는 데 사용 하는 정보를 제공 합니다.

Alice의 사서함 및 Exchange UM 서비스는 호스팅된 Exchange 서비스 공급자의 데이터 센터에 있습니다. Exchange UM 호출에 대 한 라우팅은 다음과 같이 구성 됩니다.

  - Alice의 사용자 계정에 대 한 msExchUCVoiceMailSettings 특성에 설정 된 값은 호스팅된 음성 메일 정책의 라우팅 세부 정보를 확인 하도록 ExUM 라우팅 응용 프로그램에 지시 합니다.
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 특성 값은 Exchange 서비스 공급자 또는 Lync Server 2013 관리자에 의해 설정 될 수 있습니다. 앞의 다이어그램에 표시 된 예에서 Lync Server 2013 관리자는이 값을 사용 하 여 Alice에 게 호스팅된 음성 메일을 사용할 수 있도록 설정 했습니다. 이 특성에 대 한 자세한 내용은 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013의 호스팅된 Exchange 사용자 관리</A>를 참조 하세요.

    
    </div>

  - Alice의 사용자 계정에 할당 된 호스팅된 음성 메일 정책은 다음과 같은 라우팅 세부 정보를 제공 합니다.
    
      - 대상은 호스팅된 Exchange UM 서비스 공급자 (ls)입니다. ExUm. \<hostedExchangeServer\> . 이 예제의 com)
    
      - 조직은 ls에 있는 Exchange Server 테 넌 트에 대 한 SIP 메시지의 라우팅 Fqdn 인 테 넌 트 Id로 식별 됩니다. ExUm. \<hostedExchangeServer\> . com (이 예에서는 corp.contoso.com 및 corp.litwareinc.com)
        
        <div>
        

        > [!NOTE]  
        > Exchange Online의 FQDN은 exap.um.outlook.com입니다.

        
        </div>
        
        자세한 내용은 [Lync Server 2013에서 호스팅된 음성 메일 정책](lync-server-2013-hosted-voice-mail-policies.md)를 참조 하십시오.

<div>


> [!NOTE]  
> 사용자 계정에 msExchUCVoiceMailSettings 특성과 UM 프록시 주소 설정이 둘 다 있는 경우 msExchUCVoiceMailSettings 특성이 우선적으로 적용 됩니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

