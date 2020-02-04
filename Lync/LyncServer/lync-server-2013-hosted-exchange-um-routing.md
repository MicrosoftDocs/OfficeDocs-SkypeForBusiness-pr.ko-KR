---
title: 'Lync Server 2013: 호스팅된 Exchange UM 라우팅'
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
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange UM 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

Exchange UM 라우팅 응용 프로그램은 프런트 엔드 서버에서 실행 되어 온-프레미스 Microsoft Exchange Server UM (통합 메시징) 배포 또는 호스팅된 Exchange UM 서비스에 호출을 라우팅합니다.

<div>

## <a name="the-exum-routing-application"></a>ExUM 라우팅 응용 프로그램

Lync Server 2013 Exchange UM 라우팅 응용 프로그램은 사용자 계정 설정 및 호스팅된 음성 메일 정책 매개 변수의 정보를 사용 하 여 다음 다이어그램과 같이 호스팅된 음성 메시지의 호출을 라우팅하는 방법을 결정 합니다.

**Exchange UM 라우팅의 혼합 배포 예제**

![온-프레미스 Lync Server Exchange UM 배포](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")

온-프레미스 Exchange UM에 대해 사용 하도록 설정 된 사용자, 호스트 된 Exchange UM에 대해 사용 하도록 설정 된 사용자 또는 둘의 조합에 대 한 통화를 라우팅하도록 Exchange UM 라우팅을 구성할 수 있습니다.

예를 들어 Roy의 사서함 및 Exchange UM 서비스가 온-프레미스 Exchange 배포에 설정 되어 있다고 가정 합니다.

  - Roy의 사용자 계정에 있는 프록시 주소 정보는 ExUM Routing application이 온-프레미스 Exchange UM 서버로의 호출을 라우팅하는 데 사용 하는 정보를 제공 합니다.

Alice의 사서함과 Exchange UM 서비스는 호스팅된 Exchange 서비스 공급자의 데이터 센터에 있습니다. Exchange UM 통화에 대 한 라우팅은 다음과 같이 구성 됩니다.

  - Alice의 사용자 계정에 있는 msExchUCVoiceMailSettings 특성에 설정 된 값은 호스팅된 음성 메일 정책에서 라우팅 세부 정보를 확인 하도록 ExUM 라우팅 응용 프로그램에 알립니다.
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 특성 값은 Exchange 서비스 공급자 또는 Lync Server 2013 관리자가 설정할 수 있습니다. 앞의 다이어그램에 표시 된 예제에서 Lync Server 2013 관리자가 Alice에 대해 호스팅된 음성 메일을 사용 하도록 설정 하 여 값 (CsHostedVoiceMail 메일 = 1)을 설정한 경우 이 특성에 대 한 자세한 내용은 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013에서 호스트 된 Exchange 사용자 관리</A>를 참조 하세요.

    
    </div>

  - Alice의 사용자 계정에 할당 된 호스트 된 음성 메일 정책은 라우팅 세부 정보를 제공 합니다.
    
      - 대상은 호스트 된 Exchange UM 서비스 공급자 (1!)입니다. ExUm. \<이\>예제에서는 hostedExchangeServer.
    
      - 조직에는 ls에 있는 Exchange Server 테 넌 트에 대 한 SIP 메시지의 라우팅 Fqdn 인 테 넌 트 Id가 식별 됩니다. ExUm. \<hostedExchangeServer\>(이 예에서는 corp.contoso.com 및 corp.litwareinc.com).
        
        <div>
        

        > [!NOTE]  
        > Exchange Online에 대 한 FQDN은 exap.um.outlook.com입니다.

        
        </div>
        
        자세한 내용은 [Lync Server 2013의 호스팅된 음성 메일 정책을](lync-server-2013-hosted-voice-mail-policies.md)참조 하세요.

<div>


> [!NOTE]  
> 사용자 계정에 msExchUCVoiceMailSettings 특성 및 UM 프록시 주소 설정이 둘 다 있는 경우 msExchUCVoiceMailSettings 특성이 우선권을 갖습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

