---
title: 'Lync Server 2013: 위치 정책 만들기'
description: 'Lync Server 2013: 위치 정책을 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562264"
---
# <a name="create-location-policies-in-lync-server-2013"></a>Lync Server 2013의 위치 정책 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-11_

Lync Server는 클라이언트 등록 중에 E9-1-1에 대해 Lync 클라이언트를 사용 하도록 설정 하기 위해 위치 정책을 사용 합니다. 위치 정책에는 E9-1-1이 구현 되는 방식을 정의 하는 설정이 포함 되어 있습니다.

전역 위치 정책을 편집 하 고 태그가 지정 된 새 위치 정책을 만들 수 있습니다. 클라이언트가 연결 된 위치 정책을 사용 하는 서브넷 내에 없거나 클라이언트에 위치 정책이 직접 할당 되지 않은 경우에는 글로벌 정책을 가져옵니다. 태그가 지정 된 정책은 서브넷 또는 사용자에 게 할당 됩니다.

위치 정책을 만들려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 이거나이에 해당 하는 관리자 권한 및 사용 권한이 있는 계정을 사용 해야 합니다.

위치 정책에 대 한 자세한 내용은 [Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하십시오. 이 절차의 cmdlet은 다음 값을 사용 하 여 정의 된 위치 정책을 사용 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>요소</th>
<th>값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>고지 사항</strong></p></td>
</tr>
<tr class="odd">
<td><p>Microsoft.rtc.management.writableconfig.policy.location.enhancedemergencyservicedisclaimer 유형의</p></td>
<td><p>회사 정책에 따라 위치를 설정 해야 합니다. 위치를 설정 하지 않으면 응급 서비스에서 해당 사용자를 찾을 수 없게 됩니다. 위치를 설정 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


위치 정책을 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>위치 정책을 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>PstnUsage</STRONG> 에 대 한 설정이 PstnUsages의 전역 목록에 없으면 CsLocationPolicy가 실패 합니다.

    
    </div>

2.  필요한 경우 다음 cmdlet을 실행 하 여 전역 위치 정책을 편집 합니다.
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  다음을 실행 하 여 태그가 지정 된 위치 정책을 만듭니다.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  다음 cmdlet를 실행 하 여 3 단계에서 만든 태그가 지정 된 위치 정책을 사용자 정책에 적용 합니다.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

