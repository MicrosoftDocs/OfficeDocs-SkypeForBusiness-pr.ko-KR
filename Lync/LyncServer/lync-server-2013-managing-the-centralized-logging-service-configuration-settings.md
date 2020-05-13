---
title: 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 중앙 로깅 서비스 구성 설정 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

중앙 로깅 서비스는 CLSController (중앙화 된 로깅 서비스 컨트롤러)에서 만들고 사용 하 여 개별 컴퓨터의 중앙 로깅 서비스 에이전트 (Clscontroller)에 명령을 전송 하는 설정 및 매개 변수를 통해 제어 및 구성 됩니다. 에이전트는 여기에 전송 되는 명령, 즉 시작 명령의 경우에는 제공 된 구성 정보에 따라 추적 로그 수집을 시작 하기 위한 시나리오, 공급자, 로그 크기, 추적 기간 및 플래그 구성을 사용 합니다.

<div>


> [!IMPORTANT]
> 중앙 로깅 서비스에 대해 나열 된 모든 Windows PowerShell cmdlet은 Lync Server 2013 온-프레미스 배포에 사용 하기 위한 것이 아닙니다. 다음과 같은 cmdlet은 작동 하는 것 처럼 보일 수 있지만 Lync Server 2013 온-프레미스 배포에서는 작동 하도록 설계 되지 않았습니다. 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> 및 <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>CsClsSearchTerm cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> 및 <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> 및 <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>이러한 cmdlet에 정의 된 설정은 방해 하거나 부정적인 동작이 발생 하지 않지만, 이러한 기능은 Microsoft 365에서 사용 하도록 디자인 되었으며, 온-프레미스 배포에서 예상 결과를 얻지 못합니다. 이 말이 온-프레미스 배포에서 이러한 cmdlet을 사용할 수 없음을 의미하는 것은 아니지만 이 설명서에서는 이러한 cmdlet의 용도에 대해 설명하지 않겠습니다.


</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션의 항목에서는 중앙 로깅 서비스에 대 한 구성 옵션, 매개 변수 및 설정을 정의 합니다. 중앙 로깅 서비스를 구성 하는 방법, 구성 설정을 검색 하는 방법, 시나리오를 만드는 방법, 중앙화 된 로깅 서비스에 대 한 보안 그룹 관리, 검색 등에 대 한 자세한 내용은 다음 항목에 포함 되어 있습니다.

  - [Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙화 된 로깅 서비스 구성 관리](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Lync Server 2013에서 중앙 로깅 서비스에 대 한 시나리오 구성](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중앙 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013의 중앙 로깅 cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

