---
title: 'Lync Server 2013: 주소록 관리 Update-CsAddressBook'
description: 'Lync Server 2013: 주소록 관리 Update-CsAddressBook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546244"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리 Update-CsAddressBook

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalUserAdmins 및 RTCUniversalServerAdmins 그룹의 구성원은 Update-CsAddressBook cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Update-CsAddressBook cmdlet은 Office Communications Server의 **abserver.exe –syncNow** 명령을 대체합니다. 이 cmdlet은 예약된 시간을 기다리지 않고 동기화를 즉시 시작하는 데 사용됩니다. 첫 번째 예제 명령에서는 조직의 모든 주소록을 업데이트합니다. 두 번째 예제 명령에서는 정의된 서버에 연결된 주소록만 업데이트합니다.

<div>


> [!NOTE]  
> Lync Server 2013에서는 Lync Server 사용자 복제기가 Active Directory에서 변경 된 내용을 선택 하 고 구성 된 간격에 따라 Lync Server 사용자 데이터베이스를 업데이트 합니다. 또한 Lync Server 사용자 복제기는 관리자가 Update-csaddressbook를 실행 하지 않고 RTCab 데이터베이스에 대 한 변경 내용을 빠르게 전파 합니다. 주소록 파일 다운로드가 설정된 경우 관리자는 Update -CSAddressBook만 실행하면 됩니다.



</div>

예:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>참고 항목


[업데이트-Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

