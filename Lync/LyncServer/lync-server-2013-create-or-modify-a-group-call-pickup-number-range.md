---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

통화 공원 표에서 통화 픽업 그룹 번호 범위를 만들거나 수정 하려면 다음 절차를 사용 합니다.

<div>


> [!NOTE]  
> Lync Server Management Shell을 사용 하 여 통화 공원 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다. Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.



</div>

<div>


> [!IMPORTANT]  
> 통화 픽업 그룹 번호 범위에 GroupPickup 종류를 할당 해야 합니다. 사용자는 자신에 게 할당 된 그룹 번호가 GroupPickup 형식인 경우에만 그룹 통화 픽업 트럭을 사용할 수 있습니다.



</div>

통화 픽업 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.

  - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

  - 번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.

  - 숫자 범위가 문자로 \* 시작 하거나 \#범위가 100 보다 커야 합니다.

  - 유효한 값: 정규식 문자열 (?\[\\\*|\#\]\[ )과 일치 해야 합니다. 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). 즉, 값이 문자 \* 또는 \# 숫자 1부터 9 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다. 첫 번째 문자가 \* or \#이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다. 이후 문자는 0 ~ 9 개의 추가 문자 (예: "\#6000", "\*92000", "\*95551212" 및 "915551212") 일 수 있습니다. 첫 문자를 입력 하지 않은 \* \#경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 각 숫자 0 ~ 9 (예: "915551212", "41212", "300") 이어야 합니다.

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>통화 픽업 그룹 범위를 만들거나 수정 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  **New-CsCallParkOrbit** 를 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다. **Set-CsCallParkOrbit** 를 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.
    
    명령줄에서 다음을 실행 합니다.
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    예를 들면 다음과 같습니다.
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    다음 예제에서는 통화 공원 orbits에서 pickup 그룹으로 숫자 범위를 변경 하는 방법을 보여 줍니다.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 하 고 그룹 범위가 아직 사용 되지 않은 경우에만 숫자 범위에 할당 된 유형을 변경할 수 있습니다. 번호 범위를 CallPark에서 GroupPickup으로 변경 하거나 그 반대의 경우 또는 그 반대로, 그리고 해당 번호 범위를 이미 사용 중인 경우에는 통화 공원 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동을 중지 합니다. 예를 들어, 번호 범위를 CallPark에서 GroupPick로 변경 하면 통화 공원 응용 프로그램이 더 이상 통화를 파킹 하기 위해 해당 orbits 범위를 사용할 수 없습니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 통화 공원 궤도 범위 삭제](lync-server-2013-delete-a-call-park-orbit-range.md)  


[새로운 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

