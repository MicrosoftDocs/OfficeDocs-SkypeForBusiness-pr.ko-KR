---
title: 'Lync Server 2013: 주소록 관리 Set-CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ffa2cfb5435919d28f959bf6d8bc49673b87ef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509955"
---
# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리 Set-CsClientPolicy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 Set-CsClientPolicy cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

새 CsClientPolicy와 마찬가지로 Set-CsClientPolicy cmdlet을 사용 하 여 이미 적용 된 클라이언트 설정을 수정할 수 있습니다.

예를 들면 다음과 같습니다.

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a>참고 항목


[설정-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

