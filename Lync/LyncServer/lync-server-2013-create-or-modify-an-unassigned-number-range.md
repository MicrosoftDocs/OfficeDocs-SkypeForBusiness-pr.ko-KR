---
title: 'Lync Server 2013: 할당 되지 않은 숫자 범위 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c24e1f76e6c07e1a5e32b075aec6aa7de23ea1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013에서 할당 되지 않은 숫자 범위 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차 중 하나를 사용 하 여 알림 신청에 대해 할당 되지 않은 번호 범위를 구성 합니다.

<div>


> [!IMPORTANT]  
> 지정 하지 않은 번호 테이블을 구성 하기 전에 이미 하나 이상의 알림을 정의 하거나 UM (Exchange 통합 메시징) 자동 전화 교환을 설정 해야 합니다.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Lync Server 제어판을 사용 하 여 할당 되지 않은 전화 번호를 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 기능**을 클릭 한 다음 지정 하지 **않은 번호**를 클릭 합니다.

4.  지정 하지 **않은 번호** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 새 번호 범위를 만들려면 **새로**만들기를 클릭 합니다. **이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 데이터베이스에 새 할당 되지 않은 번호 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.

        
        </div>
    
      - 기존 번호 범위를 수정 하려면 검색 필드에 숫자 범위 이름 전체 또는 일부를 입력 합니다. 결과 번호 범위 목록에서 원하는 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  첫 번째 **숫자 범위** 필드에 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</P>
    > <LI>
    > <P>범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.</P>
    > <LI>
    > <P>번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. 즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 지정 하지 않으면 자동으로 추가 됩니다), 더하기 기호 (+), 숫자 1 ~ 9 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</P></LI></UL>

    
    </div>

6.  **알림 서비스**에서 다음 중 하나를 수행 합니다.
    
      - **공지 사항을**클릭 합니다.
    
      - **EXCHANGE UM**을 클릭 합니다.

7.  이전 단계에서 **공지 사항을**클릭 한 경우 다음을 수행 합니다.
    
    1.  **대상 서버의 FQDN**아래에서 **선택을**클릭 하 고 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 클릭 하 여이 범위의 지정 되지 않은 번호로 걸려오는 통화를 처리 하 고 **확인**을 클릭 합니다.
    
    2.  **알림에서**이 지정 되지 않은 숫자 범위에 대해 재생할 공지 사항을 클릭 합니다.

8.  이전 단계에서 **EXCHANGE UM**을 클릭 한 후 **자동 전화 교환 전화 번호**아래에서 **선택을**클릭 하 고 지정 하지 않은이 범위의 번호에 사용할 전화 번호를 클릭 한 다음 **확인**을 클릭 합니다.

9.  **확인**을 클릭합니다.

10. 지정 하지 않은 **번호** 페이지에서 지정 하지 않은 번호 범위가 원하는 순서 대로 정렬 되어 있는지 확인 합니다. 표에서 범위의 위치를 변경 하려면 범위 목록에서 하나 이상의 연속 된 이름을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 지정 하지 않은 번호 표를 맨 위에서 아래로 검색 하 고 지정 된 번호와 일치 하는 첫 번째 범위를 사용 하는 Lync Server 겹치는 범위와 한 범위에서 마지막 리조트 작업을 지정 하는 경우 해당 범위가 목록의 맨 아래에 있는지 확인 합니다.

    
    </div>

11. 지정 하지 않은 번호 범위가 원하는 순서 대로 되어 있으면 **모두 커밋을**클릭 합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Windows PowerShell을 사용 하 여 지정 되지 않은 전화 번호를 구성 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  **New-CsUnassignedNumber** 를 사용 하 여 할당 되지 않은 새 번호 범위를 만듭니다. **Set-CsUnassignedNumber** 를 사용 하 여 지정 되지 않은 기존 번호 범위를 수정 합니다.
    
    <div>
    

    > [!TIP]  
    > 범위가 겹쳐져 특정 순서로 범위를 적용 하려면 Priority 매개 변수를 포함 합니다. 우선 순위가 가장 높은 범위가 통화에 적용 됩니다.

    
    </div>
    
    명령줄에서 다음 중 하나를 수행 합니다.
    
      - 알림 서비스에 대 한 번호 범위를 만들려면 다음을 실행 합니다.
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - 또는 Exchange UM 자동 전화 교환에 대 한 숫자 범위를 만들려면 다음을 실행 합니다.
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    예를 들면 다음과 같습니다.
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    또는
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    다음 예제에서는 기존에 할당 되지 않은 숫자 범위에서 숫자를 수정 하는 방법을 보여 줍니다.
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 할당 되지 않은 번호 범위 삭제](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

