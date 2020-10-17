---
title: 'Lync Server 2013: 할당 되지 않은 번호 범위 만들기 또는 수정'
description: 'Lync Server 2013: 할당 되지 않은 번호 범위를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2998616b931e94c9c38fc44d569b84b3af37709d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546954"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Lync Server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

다음 절차 중 하나를 사용 하 여 알림 응용 프로그램에 대해 할당 되지 않은 번호 범위를 구성 합니다.

<div>


> [!IMPORTANT]  
> 할당되지 않은 번호 테이블을 구성하려면 하나 이상의 알림을 정의하거나 Exchange UM(통합 메시징) 자동 전화 교환을 설정해야 합니다.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Lync Server 제어판을 사용 하 여 지정 되지 않은 전화 번호를 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 기능**을 클릭하고 **지정되지 않은 번호**를 클릭합니다.

4.  **지정되지 않은 번호** 페이지에서 다음 중 하나를 수행합니다.
    
      - 새 번호 범위를 만들려면 **새로 만들기**를 클릭하고 **이름**에 이 번호 범위에 대한 식별 이름을 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 할당되지 않은 새 번호 범위를 데이터베이스에 커밋하고 나면 이 이름은 변경할 수 없습니다.

        
        </div>
    
      - 기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름을 모두 또는 일부분 입력합니다. 결과 번호 범위 목록에서 수정할 이름을 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.

5.  첫 번째 **번호 범위** 필드에는 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</P>
    > <LI>
    > <P>범위의 시작 번호나 끝 번호에 내선 번호가 포함된 경우에는 범위의 시작 번호와 끝 번호 둘 다에 내선 번호가 포함되어야 하며, 내선 번호는 시작 번호와 끝 번호에 대해 같아야 합니다.</P>
    > <LI>
    > <P>번호는 정규식 (tel:)? ()와 일치 해야 합니다. \+ [1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?. 즉, 번호가 문자열 tel:(이 문자열을 지정하지 않으면 자동으로 추가됨), 더하기 기호(+) 및 숫자 1-9로 시작할 수 있습니다. 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</P></LI></UL>

    
    </div>

6.  **알림 서비스**에서 다음 중 하나를 수행합니다.
    
      - **알림**을 클릭합니다.
    
      - **Exchange UM**을 클릭합니다.

7.  이전 단계에서 **알림**을 클릭한 경우 다음을 수행합니다.
    
    1.  **대상 서버의 FQDN**에서 **선택**을 클릭하고, 이 지정되지 않은 번호 범위에 대한 수신 전화를 처리할 알림 응용 프로그램을 실행하는 응용 프로그램 서비스의 서비스 ID를 클릭한 후에 **확인**을 클릭합니다.
    
    2.  **알림**에서 이 지정되지 않은 번호 범위에 대해 재생할 알림을 클릭합니다.

8.  이전 단계에서 **Exchange UM**을 클릭한 경우에는 **자동 전화 교환 전화 번호**에서 **선택**을 클릭하고 이 지정되지 않은 번호 범위에 사용할 전화 번호를 클릭한 후에 **확인**을 클릭합니다.

9.  **확인**을 클릭합니다.

10. **지정되지 않은 번호** 페이지에서 지정되지 않은 번호 범위가 원하는 순서로 정렬되어 있는지 확인합니다. 표에서 범위 위치를 변경하려면 범위 목록에서 연속하는 이름을 하나 이상 클릭하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    <div>
    

    > [!TIP]  
    > Lync Server는 지정 되지 않은 번호 테이블을 위에서 아래로 검색 하 고 지정 되지 않은 번호와 일치 하는 첫 번째 범위를 사용 합니다. 겹치는 범위와 최후의 수단으로 수행할 작업을 지정하는 범위가 있는 경우에는 해당 범위가 목록 맨 밑에 오도록 하십시오.

    
    </div>

11. 할당되지 않은 번호 범위를 원하는 순서대로 표시하려면 **모두 커밋**을 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Windows PowerShell을 사용 하 여 지정 되지 않은 전화 번호를 구성 하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  **New-csunassignednumber** 을 사용 하 여 새 지정 되지 않은 번호 범위를 만듭니다. **New-csunassignednumber** 을 사용 하 여 기존 지정 되지 않은 번호 범위를 수정 합니다.
    
    <div>
    

    > [!TIP]  
    > 겹치는 범위가 있고 해당 범위가 특정 순서로 적용되게 하려는 경우에는 Priority 매개 변수를 포함합니다. 우선 순위가 가장 높은 범위가 통화 적용됩니다.

    
    </div>
    
    명령줄에서 다음 중 하나를 수행합니다.
    
      - 알림 서비스에 대한 번호 범위를 만들려면 다음을 실행합니다.
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - 또는 Exchange UM 자동 전화 교환에 대한 번호 범위를 만들려면 다음을 실행합니다.
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    예:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    또는
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    다음 예에서는 지정되지 않은 기존 번호 범위의 번호를 수정하는 방법을 보여 줍니다.
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 할당 되지 않은 번호 범위 삭제](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[New-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[New-csunassignednumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

