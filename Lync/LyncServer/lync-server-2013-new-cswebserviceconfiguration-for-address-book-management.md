---
title: 'Lync Server 2013: 주소록 관리 New-CsWebServiceConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63d6bfeed8b005c3498a2fd0cfcf2201d0d45c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531805"
---
# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리 New-CsWebServiceConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 New-CsWebServiceConfiguration cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 지정된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

New-CsWebServiceConfiguration cmdlet은 조직의 웹 서비스에 대해 새 구성을 정의합니다. 웹 서비스 구성의 범위는 사이트 또는 서비스 수준이어야 하며, 전역 수준에서 새 웹 서비스 구성을 만들 수는 없습니다. 주소록에서 주의해야 하는 특성은 EnableGroupExansion입니다. 이 특성을 True로 설정하는 경우 웹 서비스가 그룹 확장 요청에 응답할 수 있습니다.

예:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>참고 항목


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

