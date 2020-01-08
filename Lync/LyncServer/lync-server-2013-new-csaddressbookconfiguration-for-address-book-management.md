---
title: 'Lync Server 2013: 주소록 관리용 새-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a11829a6c0dd4e53f5684e5b950e3adf755811
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리를 위한 새 CsAddressBookConfiguration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 다음 그룹의 구성원에 게 새 CsAddressBookConfiguration cmdlet을 로컬로 실행할 권한이 부여 됩니다. RTCUniversalServerAdmins. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

새로운-CsAddressBookConfiguration cmdlet은 주소록의 동작을 관리 하기 위한 새 구성을 만듭니다. 이 cmdlet에 대 한 자세한 내용은 주소록 서비스에서 클라이언트 다운로드 파일을 만들고, 정규화 규칙을 사용 하는 방법, 델타 및 압축 델타 파일의 보존 기간, 새 전체 파일을 통합 하기 전에 델타 파일 크기를 유지 하는 방법 등을 정의 하는 기능입니다. 전체 파일 주소록을 만든 날짜와 사용자 데이터베이스의 정보를 동기화 하는 데 사용할 내부 작업 시간을 지정 합니다.

예를 들면 다음과 같습니다.

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>참고 항목


[New-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

