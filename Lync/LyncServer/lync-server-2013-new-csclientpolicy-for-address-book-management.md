---
title: 'Lync Server 2013: 주소록 관리를 위한 신규-CsClientPolicy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d63b29ea1198bfee91437a1e6dcd70c1be0a45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리를 위한 신규 및 CsClientPolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 New-CsClientPolicy cmdlet을 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Cmdlet 새 CsClientPolicy는 Lync Server 2013에서 사용할 수 있는 기능에 대해 클라이언트 프로 비전을 위한 다 수의 설정을 정의 합니다. 주소록 서비스의 경우 AddressBookAvailability 매개 변수가 고려됩니다. 클라이언트에서 사용할 수 있는 옵션에 직접 영향을 주는 이 매개 변수에는 다음과 같은 세 가지 옵션이 있습니다.

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

이 매개 변수가 정의된 경우 클라이언트에서 주소록에 액세스하는 방법이 결정됩니다. 이 매개 변수를 정의할 경우 옵션 중 하나를 정의해야 합니다. 이 설정을 수정하지 않으면 기본 WebSearchAndFileDownload가 적용됩니다.

예:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>참고 항목


[신규-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

