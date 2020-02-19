---
title: 'Lync Server 2013: 장치와 연결 되지 않은 장치 업데이트 파일 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7089e3f055d89fb07215d119ea287471fd211de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Lync Server 2013에서 장치와 연결 되지 않은 장치 업데이트 파일 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

새 장치 업데이트가 시스템에 업로드 될 때마다 해당 하는 장치 업데이트 규칙이 만들어집니다. 기본적으로 이러한 새 장치 업데이트 규칙은 보류 중 상태에 할당 됩니다. 즉, 테스트 장치에는 규칙을 다운로드 하 고 설치할 수 있지만 프로덕션 장치에는 설치 하지 않아도 되므로 사용자가 해당 업데이트를 사용할 수 있도록 하는 것이 좋습니다. 테스트를 기반으로 업데이트를 수락 하 고 배포 하거나 거부 하 고 삭제 합니다. 업데이트를 거부 하면 장치 업데이트는 해당 장치 업데이트 규칙과의 연결이 끊어집니다.

<div>


장치 업데이트 더 이상 장치와 연결 되지 않은 파일은 Windows PowerShell 및 **일반 CsDeviceUpdateFile** cmdlet을 사용 하 여 제거할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>


  - 예를 들어 다음 명령은 장치에 더 이상 연결 되어 있지 않은 웹 서버 atl-cs-001.litwareinc.com에서 모든 장치 업데이트 규칙을 제거 합니다.
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

자세한 내용은 [일반-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

