---
title: 'Lync Server 2013: 에지 서버 인증서 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Lync Server 2013의 에지 서버 인증서 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-05_

Lync Server 2013에서 Edge 용 인증서 만들기가 간소화 되었습니다.

**에지 서버에 대한 인증서 순서도**

![a5fc20db-7ced 4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced 4364-b577-6a709a8367cd")

단일 공용 인증서를 만들고 인증서에 대해 내보낼 수 있는 개인 키가 정의 되어 있는지 확인 하 고 인증서 마법사를 사용 하 여 다음 Edge Server 외부 인터페이스에이를 할당 합니다.

<div>


> [!IMPORTANT]  
> 역방향 프록시를 통해 간단한 Url을 요약 하는 데 사용 되는 경우를 제외 하 고 Lync Server에서는 와일드 카드 인증서가 지원 되지 않습니다. 배포에서 제공 하는 각 SIP 도메인 이름, 웹 회의에 지 서비스, A/V Edge 서비스 및 XMPP 도메인에 대해 고유한 San (주체 대체 이름)을 정의 해야 합니다.



</div>

<div>


> [!NOTE]  
> Lync Server 2013에 도입 된 현재 인증서의 만료 시간 전에 오디오/비디오 인증 인증서를 준비 하는 경우 몇 가지 추가 계획이 필요 합니다. 외부에 지 인터페이스에 대 한 용도가 여러 개 있는 인증서 대신, 하나는 두 개의 인증서 (액세스 경계 서비스 및 웹 회의 Edge 서비스에 할당 됨)와 A/V Edge 서비스에 대 한 인증서가 필요 합니다. 자세한 내용은 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Lync Server 2013 using-롤에서 CsCertificate 설정에서 AV 및 OAuth 인증서 준비</A> 를 참조 하세요.



</div>

<div>


> [!IMPORTANT]  
> Edge 서버의 풀에서 각 Edge 서버로 개인 키가 있는 인증서를 내보내고 각 Edge 서버 서비스에 인증서를 할당 합니다. 내부에 지 서버 인증서에 대해 동일한 작업을 수행 하 고, 개인 키를 사용 하 여 인증서를 내보내고, 각 내부에 지 인터페이스에 할당 합니다.



</div>

  - 인증서에 대해 내보낼 수 있는 개인 키가 할당 되어 있는지 확인

  - 액세스에 지 서비스 (인증서 마법사의 **SIP 액세스에 외부** 이 라고도 함)

  - 웹 회의에 지 서비스 (인증서 마법사의 **외부 웹 회의 경계** 라고 함)

  - A/V 인증 서비스 (인증서 마법사의 **외부/v 경계** 라고 함)

내보낼 수 있는 개인 키를 사용 하 여 단일 내부 인증서를 만들고 각 Edge Server 내부 인터페이스에 복사 하 여 할당 합니다.

  - Edge 서버 (인증서 마법사의 **경계 내부** 라고 함)

<div>


> [!IMPORTANT]  
> 각 Edge 서버 서비스에 대해 별개의 인증서를 사용 하는 것이 가능 합니다. 별도의 인증서를 선택 하는 것이 좋은 이유는 A/V Edge 서비스 인증서에 대 한 새 롤링 인증서 기능을 사용 하려는 경우입니다. 이 기능을 사용 하는 경우에는 A/V Edge 서비스 인증서를 액세스 경계 서비스 및 웹 회의에 지 서비스에서 분리 하는 것이 좋습니다. 각 서비스에 대해 별도의 인증서를 요청 하 고 취득 하 고 할당 하는 경우에는 A/v Edge 서비스에 대해 개인 키를 내보낼 수 있도록 요청 하 고 (이는 실제로 A/V 인증 서비스를 담당 하는 경우) 각 Edge 서버의 A/V Edge 외부 인터페이스에 동일한 인증서를 할당 해야 합니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 using in CsCertificate에서 설정 된 AV 및 OAuth 인증서 준비](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[에지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

