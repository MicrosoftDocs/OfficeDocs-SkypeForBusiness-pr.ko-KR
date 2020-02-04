---
title: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb8c4504674e5459fbbb0e7529ea4e6c4ad7a8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013에서 서버 역할 및 서비스 cmdlet 문제 해결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-27_

문제 해결 cmdlet은 Microsoft Lync Server 2013이 예상 대로 작동 하는지 확인 하는 다양 한 방법을 제공 합니다. 예를 들어 CsHealthMonitoringConfiguration cmdlet을 사용 하면 레지스트라 및 디렉터 풀의 테스트 계정을 설정할 수 있습니다. 그런 다음 해당 테스트 계정을 사용 하 여 사용자가 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 PSTN (공개 통신 네트워크)에 있는 휴대폰으로 전화 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인할 수 있습니다.

<div>


> [!NOTE]
> Cmdlet에 대 한 자세한 내용은의 Lync Server&nbsp;Windows PowerShell 블로그를 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>하세요. 각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a>서버 역할 및 서비스 Cmdlet

다음은 서버 역할 및 서비스 문제 해결에 직접 관련 된 cmdlet의 목록입니다.

**서버 역할 및 서비스 문제 해결**

  - <span></span>  
    [Get-Cs오디오/Estserviceapplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set-Cs| Rootestserviceapplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))

  - <span></span>  
    [새로운 CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))

  - <span></span>  
    [제거-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))

  - <span></span>  
    [새로운 CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))

  - <span></span>  
    [제거-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새로운 CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))

  - <span></span>  
    [제거-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

