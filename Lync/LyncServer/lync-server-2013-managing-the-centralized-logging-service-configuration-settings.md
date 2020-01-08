---
title: 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 중앙 집중화 된 로깅 서비스 구성 설정 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

중앙 로깅 서비스는 각 컴퓨터의 중앙 로깅 서비스 에이전트에 명령을 전송 하기 위해 중앙 집중식 로깅 서비스 컨트롤러 (CLSController)에서 만들고 사용 하는 설정 및 매개 변수를 통해 제어 및 구성 됩니다 ( CLSAgent). 에이전트는 여기에 전송 된 명령을 처리 하 고 (시작 명령의 경우) 시나리오, 공급자, 로그 크기, 추적 기간 및 플래그 구성을 사용 하 여 제공 되는 구성 정보에 따라 추적 로그 수집을 시작 합니다.

<div>


> [!IMPORTANT]
> 중앙 로깅 서비스에 대해 나열 된 모든 Windows PowerShell cmdlet은 Lync Server 2013 온-프레미스 배포와 함께 사용 하기 위한 것이 아닙니다. 다음과 같은 cmdlet는 작동 하는 것 처럼 보일 수 있지만 Lync Server 2013 온-프레미스 배포에서 작동 하도록 설계 되지 않았습니다. 
> <UL>
> <LI>
> <P><STRONG>Csclsregion cmdlet:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-csclsregion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-csclsregion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-csclsregion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">제거-csclsregion</A>.</P>
> <LI>
> <P><STRONG>Csclssearchterm cmdlet:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-csclssearchterm</A> 및 <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set csclssearchterm</A>입니다.</P>
> <LI>
> <P><STRONG>Csclssecuritygroup cmdlet:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-csclssecuritygroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-csclssecuritygroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>및 <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-csclssecuritygroup</A>.</P></LI></UL>이러한 cmdlet에 정의 된 설정은 방해 하거나 부정적인 동작을 발생 시 키 지 않으며, Microsoft Office 365에서 사용 하도록 디자인 되었으며 온-프레미스 배포에서 예상 되는 결과가 생성 되지 않습니다. 이는 온-프레미스 배포에서 이러한 cmdlet을 사용 하지 않는 것이 아니라,이를 사용 하는 것이이 문서에서 다루지 않는 고급 항목입니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션의 항목은 중앙 로깅 서비스에 대 한 구성 옵션, 매개 변수 및 설정을 정의 합니다. 중앙 로깅 서비스를 구성 하는 방법, 구성 설정을 검색 하는 방법, 시나리오 만들기, 중앙 로깅 서비스에 대 한 보안 그룹 관리, 자세한 내용은 다음 항목에 대 한 정보를 포함 합니다.

  - [Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Lync Server 2013에서 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Lync Server 2013에서 중앙 집중화 된 로깅 서비스에 대 한 시나리오 구성](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013의 중앙 집중화 된 로깅 cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

