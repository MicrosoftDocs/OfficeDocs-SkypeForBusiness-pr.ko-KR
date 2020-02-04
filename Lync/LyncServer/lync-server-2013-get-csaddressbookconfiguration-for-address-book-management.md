---
title: 'Lync Server 2013: 주소록 관리용 가져오기-CsAddressBookConfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a9f29ee4842b11c503e913d1e80e97e2dab274
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리를 위한 가져오기-CsAddressBookConfiguration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 Get-CsAddressBookConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Cmdlet Get CsAddressBookConfiguration은 이미 존재 하는 구성에 대 한 정보를 반환 합니다.

예를 들면 다음과 같습니다.

    Get-CsAddressBookConfiguration -Identity site:Redmond

Get-CsAddressBookConfiguration 및 Set CsAddressBookConfiguration 기능을 결합 하면 관리자가 수정할 구성을 정의한 다음 수정 내용을 적용할 수 있습니다. 예를 들어 다음과 같이 결합 됩니다.

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

모든 사이트의 모든 구성을 반환 하 고 구성에 23:00 시간을 기준으로 RunTimeOfDay를 적용 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

