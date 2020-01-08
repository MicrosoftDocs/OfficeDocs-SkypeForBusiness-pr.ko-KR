---
title: 'Lync Server 2013: 지정 되지 않은 숫자 범위 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8bf1bcea1a2f84def783b833d232a44282cab6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013에서 할당 되지 않은 번호 범위 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차 중 하나를 사용 하 여 공지 사항에 할당 되지 않은 번호 범위를 삭제 합니다.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>Lync Server 제어판을 사용 하 여 지정 되지 않은 숫자 범위를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.

4.  지정 하지 **않은 번호** 페이지의 검색 필드에 삭제 하려는 배정 되지 않은 번호 범위 이름의 전부 또는 일부를 입력 합니다.

5.  결과 번호 범위 목록에서 이름을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

6.  **모두 커밋을**클릭 합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>Windows PowerShell을 사용 하 여 지정 되지 않은 번호 범위를 삭제 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령줄에 다음을 입력 합니다.
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    예를 들면 다음과 같습니다.
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > 추가 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">제거-CsCallParkOrbit</A>를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 할당 되지 않은 숫자 범위 만들기 또는 수정](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[제거-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

