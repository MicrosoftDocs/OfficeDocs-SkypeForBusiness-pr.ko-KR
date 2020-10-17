---
title: 'Lync Server 2013: 장치 업데이트 구성 설정 모음 삭제'
description: 'Lync Server 2013: 장치 업데이트 구성 설정 컬렉션을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566654"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 구성 설정 컬렉션 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

장치 업데이트 구성 설정은 Windows PowerShell 및 **new-csdeviceupdateconfiguration** cmdlet을 사용 하 여 삭제할 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>장치 업데이트 구성 설정의 특정 컬렉션을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 장치 업데이트 구성 설정을 삭제 합니다.
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 장치 업데이트 구성 설정을 제거 하려면

  - 이 명령은 사이트 범위에 적용 된 모든 장치 업데이트 구성 설정을 삭제 합니다.
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>LogCleanUpInterval 속성 값에 따라 장치 업데이트 구성 설정을 제거 하려면

  - 다음 명령은 로그 정리 간격이 10 일 (10.00:00:00) 보다 큰 모든 장치 업데이트 구성 설정을 삭제 합니다.
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

자세한 내용은 [new-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

