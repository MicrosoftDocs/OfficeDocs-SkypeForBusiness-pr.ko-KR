---
title: 'Lync Server 2013: 통화 공원 회전 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f759c0bb5c33991c961dbe4a2790c50df1f098
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차 중 하나를 사용 하 여 통화 공원 궤도 범위를 만들거나 수정 합니다.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Lync Server 제어판을 사용 하 여 파킹 통화에 대 한 숫자 범위를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 **통화 공원**을 클릭 합니다.

4.  **통화 공원** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 새 궤도 범위를 만들려면 **새로**만들기를 클릭 합니다. **이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 데이터베이스에 궤도 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.

        
        </div>
    
      - 기존 궤도 범위를 수정 하려면 검색 필드에 궤도 범위의 이름 전체 또는 일부를 입력 합니다. Orbits의 결과 목록에서 원하는 궤도를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  첫 번째 **숫자 범위** 필드에이 통화 공원 궤도에 대 한 확장 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</P>
    > <LI>
    > <P>범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</P>
    > <LI>
    > <P>궤도 범위는 고유 해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.</P>
    > <LI>
    > <P>궤도 범위가 * 또는 # 문자로 시작 하는 경우 범위는 100 보다 커야 합니다.</P>
    > <LI>
    > <P>유효한 값: 정규식 문자열과 일치 해야 합니다 ([\*| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). 즉, 값은 * 또는 # 문자나 1~9 사이의 숫자로 시작하는 문자열이어야 하며, 첫 문자가 0일 수는 없습니다. 첫 문자가 * 또는 #인 경우 다음 문자는 숫자 1-9여야 합니다(0일 수 없음). 이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "*92000",*"95551212", "915551212") 일 수 있습니다. 첫 번째 문자가 * 또는 #이 아닌 경우 첫 번째 문자는 1부터 9 (0이 될 수 없음) 다음에 최대 8 자 (예: "915551212", "41212", "300")로 시작 하 고, 각각의 숫자는 각각 0 ~ 9를 입력 합니다.</P>
    > <LI>
    > <P>풀 당 총 5만 orbits를 넘지 않아야 합니다. 일반적으로 각 궤도 범위는 100 개 이하의 orbits에 포함 되지만, 1만 orbits 보다 적은 만큼 더 커질 수 있습니다. 예를 들어 시작 번호를 "7000000"으로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"으로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</P></LI></UL>

    
    </div>

6.  **대상 서버의 fqdn**(정규화 된 도메인 이름) 또는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 서비스 ID (fqdn)를 클릭 합니다. 궤도 범위의 시작 번호와 끝 번호로 지정 된 범위 내에 있는 모든 통화는이 서버 또는 풀로 라우팅됩니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Windows PowerShell을 사용 하 여 파킹 통화에 대 한 숫자 범위를 만들거나 수정 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  **New-CsCallParkOrbit** 를 사용 하 여 궤도 번호의 새 범위를 만듭니다. **Set-CsCallParkOrbit** 를 사용 하 여 기존 궤도 번호 범위를 수정 합니다.
    
    명령줄에서 다음을 실행 합니다.
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    예를 들면 다음과 같습니다.
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    다음 예제에서는 기존 궤도 범위에서 숫자를 수정 하는 방법을 보여 줍니다.
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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

