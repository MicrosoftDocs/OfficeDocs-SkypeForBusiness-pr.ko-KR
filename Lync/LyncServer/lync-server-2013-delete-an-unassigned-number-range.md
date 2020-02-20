---
title: 'Lync Server 2013: 지정 되지 않은 번호 범위 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba26ebf354a3607cc20f3e59739113a5ad925a99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013에서 할당 되지 않은 번호 범위 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

알림에 대해 할당되지 않은 번호 범위를 삭제하려면 다음 절차를 따르십시오.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>Lync Server 제어판을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 기능**을 클릭하고 **지정되지 않은 번호**를 클릭합니다.

4.  **지정되지 않은 번호** 페이지의 검색 필드에 삭제할 할당되지 않은 번호 범위의 이름 일부나 전체를 입력합니다.

5.  결과 번호 범위 목록에서 이름을 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.

6.  **모두 커밋**을 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>Windows PowerShell을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력합니다.
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    예를 들면 다음과 같습니다.
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > 기타 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">get-cscallparkorbit</A>를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[New-csunassignednumber을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[New-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

