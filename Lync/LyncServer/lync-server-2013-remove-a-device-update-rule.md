---
title: 'Lync Server 2013: 장치 업데이트 규칙 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 규칙 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

장치 업데이트 규칙을 제거 하면 장치 업데이트 대기열에서 영구적으로 이동 합니다.

규칙 제거는 배포의 장치나 테스트 장치에서 업데이트를 제거 하는 것과 다릅니다. 배포에서 승인 된 업데이트를 제거 하려면 장치 업데이트 규칙을 *복원* 합니다. 자세한 내용은 [Lync Server 2013에서 장치 업데이트 규칙 복원을](lync-server-2013-restore-a-device-update-rule.md)참조 하세요. 테스트 장치에서 승인 하지 않은 업데이트를 제거 하려면 *다시 설정* 합니다. 자세한 내용은 [Lync Server 2013에서 장치 업데이트 규칙 다시 설정을](lync-server-2013-reset-a-device-update-rule.md)참조 하세요.

Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 디바이스 업데이트 규칙을 제거할 수 있습니다.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 제거 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트** 탐색 단추를 클릭 합니다.

4.  **장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 규칙 하나를 제거 하려면 삭제 하려는 규칙을 선택 합니다.
    
      - 모든 규칙을 제거 하려면 **편집** 메뉴를 클릭 한 다음 **모두 선택을**클릭 합니다.

5.  **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 제거

Windows PowerShell 및 **CsDeviceUpdateRule** cmdlet을 사용 하 여 디바이스 업데이트 규칙을 제거할 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>서버에서 단일 장치 업데이트 규칙을 제거 하려면

  - 다음 명령은 atl-cs-001.litwareinc.com의 웹 서버에서 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9을 제거 합니다.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>서버에서 모든 장치 업데이트 규칙을 제거 하려면

  - 이 명령은 atl-cs-001.litwareinc.com의 웹 서버에서 모든 장치 업데이트 규칙을 제거 합니다.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

자세한 내용은 [제거 CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 장치 업데이트 규칙 승인](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

