---
title: 'Lync Server 2013: 장치 업데이트 규칙 승인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 규칙 승인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

장치 업데이트 규칙을 가져온 후에는 테스트 장치에 설치 되어 있습니다. 테스트에 성공 하 고 조직에 업데이트를 배포 하려는 경우 Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 승인 합니다.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 디바이스 업데이트 규칙을 승인 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  **장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 하나의 규칙을 승인 하려면 해당 규칙을 선택 합니다.
    
      - 모든 규칙을 승인 하려면 **편집**을 클릭 한 다음 **모두 선택을**클릭 합니다.

4.  **작업**을 클릭 한 다음 **승인을**클릭 합니다.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 디바이스 업데이트 규칙 승인

Windows PowerShell 및 **CsDeviceUpdateRule** cmdlet을 사용 하 여 디바이스 업데이트 규칙을 승인할 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>단일 장치 업데이트 규칙을 승인 하려면

  - 다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 찾을 수 있는 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9을 승인 합니다.
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>여러 장치 업데이트 규칙을 승인 하려면

  - 이 명령은 Microsoft 브랜드 장치에 대 한 모든 장치 업데이트 규칙을 승인 합니다.
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

자세한 내용은 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 장치 업데이트 규칙 가져오기](lync-server-2013-import-device-update-rules.md)  
[Lync Server 2013에서 장치 업데이트 규칙 복원](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

