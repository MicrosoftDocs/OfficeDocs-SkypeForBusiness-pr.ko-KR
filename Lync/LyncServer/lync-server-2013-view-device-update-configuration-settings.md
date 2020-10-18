---
title: 'Lync Server 2013: 장치 업데이트 구성 설정 보기'
description: 'Lync Server 2013: 장치 업데이트 구성 설정을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e686562d99da679149b6b977bd3cb9feb5c9a7fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579424"
---
# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013의 장치 업데이트 구성 설정 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

Lync Server 관리 셸을 사용 하 여 장치 업데이트 서비스 구성 설정을 확인 하 고 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있는 **new-csdeviceupdateconfiguration** cmdlet을 사용할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.



</div>

<div>


<div>


  - 모든 음성 경로에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsDeviceUpdateConfiguration
    
    이 명령은 다음과 비슷한 정보를 반환합니다.
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

이 cmdlet에 대 한 자세한 내용은 [new-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)의 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

