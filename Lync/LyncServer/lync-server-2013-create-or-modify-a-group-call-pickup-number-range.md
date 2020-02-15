---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

다음 절차에 따라 통화 대기 궤도 테이블에서 통화 픽업 그룹 번호 범위를 만들거나 수정 합니다.

<div>


> [!NOTE]  
> Lync Server 관리 셸을 사용 하 여 통화 대기 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다. Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.



</div>

<div>


> [!IMPORTANT]  
> Call pickup 그룹 번호 범위에는 GroupPickup 유형이 할당 되어야 합니다. 사용자가 할당 된 그룹 번호가 GroupPickup 형식인 경우에만 그룹 통화 픽업 지를 사용할 수 있습니다.



</div>

Call pickup 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.

  - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

  - 번호 범위는 고유 해야 합니다. 이 범위는 다른 범위와 겹칠 수 없습니다.

  - 숫자 범위가 문자로 \* \#시작 하는 경우에는 범위가 100 보다 커야 합니다.

  - 유효한 값:은 정규식 문자열\[\\\*|\#\](?\[ 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}) 즉,이 값은 1부터 9 까지의 숫자로 시작 \* \# 하는 문자열 (첫 번째 문자는 0이 될 수 없음)입니다. 첫 번째 문자가 \* or \#인 경우 다음 문자는 1에서 9 사이의 숫자 (0이 될 수 없음) 여야 합니다. 이후 문자에는 0에서 9 까지의 추가 문자 (예: "\#6000", "\*92000", "\*95551212" 및 "915551212")가 최대 7 자까지 있을 수 있습니다. 첫 문자가 아닌 \* \#경우 첫 번째 문자는 1부터 9 까지의 숫자 (0이 될 수 없음)와 최대 8 자 (예: "915551212", "41212", "300") 사이에 있어야 합니다.

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>통화 픽업 그룹 범위를 만들거나 수정 하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  **Get-cscallparkorbit** 을 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다. **Get-cscallparkorbit** 을 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.
    
    명령줄에서 다음을 실행합니다.
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    예를 들면 다음과 같습니다.
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    다음 예에서는 통화 대기 궤도에서 pickup 그룹으로 번호 범위를 변경 하는 방법을 보여 줍니다.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 했 고 그룹 범위가 아직 사용 되지 않은 경우에만 번호 범위에 할당 된 형식을 변경 합니다. 번호 범위를 CallPark에서 GroupPickup로 변경 하거나 그 반대로, 숫자 범위를 이미 사용 중인 경우에는 통화 대기 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동 하지 않습니다. 예를 들어 번호 범위를 CallPark에서 GroupPick로 변경 하는 경우 통화 대기 응용 프로그램은 더 이상이 궤도 범위를 사용 하 여 통화를 대기 시킬 수 없습니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 통화 대기 번호 범위 삭제](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

