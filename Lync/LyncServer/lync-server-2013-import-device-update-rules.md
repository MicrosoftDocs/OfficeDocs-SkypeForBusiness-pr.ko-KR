---
title: 'Lync Server 2013: 장치 업데이트 규칙 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f729584f14011d18920a676c32205d38c7f62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 규칙 가져오기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

장치 업데이트 규칙은 Windows PowerShell 및 **가져오기-CsDeviceUpdate** cmdlet을 사용 하는 경우에만 가져올 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>단일 웹 서버로 장치 업데이트 규칙 가져오기

  - 다음 명령은 장치 업데이트 규칙을 웹 서버 atl-cs-001.litwareinc.com 가져옵니다.
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>모든 웹 서버에 장치 업데이트 규칙을 가져오려면

  - 이 예제에서는 장치 업데이트 규칙을 조직에 배포 된 모든 웹 서버로 가져옵니다. 이 명령이 작동 하려면 폴더 \\ \\atl-fs-001.litwareinc.com\\업데이트를 공유 하 고 모든 웹 서버에서 사용할 수 있어야 합니다.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

자세한 내용은 [가져오기-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 장치 업데이트 규칙에 대 한 정보 보기](lync-server-2013-view-information-about-device-update-rules.md)  
[Lync Server 2013에서 장치 업데이트 규칙 승인](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

