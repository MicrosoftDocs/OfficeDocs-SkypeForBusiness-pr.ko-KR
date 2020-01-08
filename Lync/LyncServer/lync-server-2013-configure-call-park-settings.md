---
title: 'Lync Server 2013: 통화 공원 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9acbd44acf2ca78042452d2c1f52d4c5fa26056f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Lync Server 2013에서 통화 공원 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

기본 통화 공원 설정을 사용 하지 않으려는 경우에는 사용자 지정할 수 있습니다. 통화 공원 응용 프로그램을 설치할 때 전역 설정이 기본적으로 구성 됩니다. 전역 설정을 수정할 수 있으며 사이트 관련 설정을 지정할 수도 있습니다. 새 사이트 관련 설정을 만들려면 **CsCpsConfiguration** cmdlet을 사용 합니다. **Set-CsCpsConfiguration** cmdlet을 사용 하 여 기존 설정을 수정 합니다.

<div>


> [!NOTE]  
> 최소한 파킹 된 통화가 시간 초과 되 고 ringback 실패할 경우 사용할 대체 대상에 대 한 <STRONG>Ontimeouturi</STRONG> 옵션을 구성 하는 것이 좋습니다.



</div>

**CsCpsConfiguration** Cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용 하 여 다음 설정을 구성 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이 옵션:</th>
<th>다음을 지정 합니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>통화에 응답 한 전화기로 전화를 걸기 전에 대기 하는 데 걸리는 시간입니다.</p>
<p>값은 hh: mm: ss 형식으로 입력 해야 시, 분, 초를 지정할 수 있습니다. 최 솟 값은 10 초 이며 최대값은 10 분입니다. 기본값은 00:01:30입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>통화가 파킹 되는 동안 호출자가 음악을 재생할 것인지 여부</p>
<p>값은 True 또는 False입니다. 기본값은 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>파킹 된 통화가 <strong>Ontimeouturi</strong>에 대해 지정 된 대체 uri (Fallback Uniform resource Identifier)로 착신 전환 되기 전에 응답 하는 전화의 횟수입니다. 기본값은 1입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p><strong>MaxCallPickupAttempts</strong> 를 초과 했을 때 응답 하지 않는 파킹 통화가 라우팅되는 사용자 또는 응답 그룹의 SIP 주소입니다.</p>
<p>값은 sip: 라는 문자열로 시작 하는 SIP URI 여야 합니다. 예를 sip:bob@contoso.com. 기본적으로 전달 주소가 없습니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>통화 공원 설정을 구성 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > 사이트를 식별 하려면 <STRONG>Get-cssite</STRONG> cmdlet을 사용 합니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 통화 공원 음악을 보류할 때 사용자 지정](lync-server-2013-customize-call-park-music-on-hold.md)  


[새로운 CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[가져오기-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

