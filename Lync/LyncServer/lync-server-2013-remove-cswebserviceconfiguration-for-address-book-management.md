---
title: 'Lync 서버 2013: 주소록 관리를 위한 CsWebServiceConfiguration 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 206c47ebb272f6ab637f4f07e9bb54a7fd1d40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리에 대 한 CsWebServiceConfiguration 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원에 게 CsWebServiceConfiguration cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

CsWebServiceConfiguration cmdlet을 사용 하면 관리자가 이전에 만든 웹 서비스 구성을 제거할 수 있습니다. Cmdlet은 전역 웹 서비스 구성을 제거할 수 없습니다.

예를 들면 다음과 같습니다.

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a>참고 항목


[제거-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

