---
title: 'Lync Server 2013: 장치 업데이트 규칙 다시 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68162e0661090ac57bfaacecfd22eea1261911e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 규칙 다시 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

테스트 장치에서 업데이트가 작동 하는 방식이 마음에 들지 않는 경우에는 장치 업데이트 규칙을 다시 설정 하 여 해당 규칙의 보류 중 상태를 제거 하 고 테스트 장치에서 업데이트를 제거할 수 있습니다.

Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 장치 업데이트 규칙을 제거할 수 있습니다.

<div>


> [!NOTE]  
> 이미 승인 된 규칙 (롤아웃)을 제거 하려면 복원 합니다. 자세한 내용은 <A href="lync-server-2013-restore-a-device-update-rule.md">Lync Server 2013에서 장치 업데이트 규칙 복원을</A>참조 하십시오.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 다시 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **장치 업데이트** 탐색 단추를 클릭 합니다.

4.  **장치 업데이트** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 규칙 하나를 다시 설정 하려면 다시 설정 하려는 규칙을 선택 합니다.
    
      - 모든 규칙을 다시 설정 하려면 **편집** 메뉴에서 **모두 선택을**클릭 합니다.
    
      - 한 브랜드에 대해 모든 규칙을 다시 설정 하려면 **브랜드** 열 메뉴를 사용 합니다.

5.  **동작**을 클릭 한 다음 **보류 중인 업데이트 취소**를 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 취소 한 장치 업데이트 규칙을 롤아웃할 필요가 없는 경우에는 삭제 하는 것이 좋습니다. 자세한 내용은 <A href="lync-server-2013-remove-a-device-update-rule.md">Lync Server 2013에서 장치 업데이트 규칙 제거</A>를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 다시 설정

Windows PowerShell 및 **get-csdeviceupdaterule** cmdlet을 사용 하 여 장치 업데이트 규칙을 다시 설정할 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>서버에서 특정 장치 업데이트 규칙을 다시 설정 하려면

  - 다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 규칙 d5ce3c10-2588-420a-82ac-82ac-dc2d9b1222ff9를 다시 설정 합니다.
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>서버에서 모든 장치 업데이트 규칙을 다시 설정 하려면

  - 이 명령은 웹 서버 atl-cs-001.litwareinc.com의 모든 장치 업데이트 규칙을 다시 설정 합니다.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>특정 브랜드의 모든 장치 업데이트 규칙을 다시 설정 하려면

  - 이 예에서는 조직이 다음과 같은 브랜드의 조직 전체에서 모든 장치 업데이트가 다시 설정 됩니다.
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

자세한 내용은 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하십시오.

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

