---
title: 'Lync Server 2013: 통화 대기 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b99bc06f22490013dd14dc8527bd3eb88938380
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

기본 통화 대기 설정을 사용 하지 않으려면 사용자 지정할 수 있습니다. 통화 대기 응용 프로그램을 설치할 때 전역 설정은 기본적으로 구성 됩니다. 전역 설정을 수정할 수 있으며 사이트별 설정을 지정할 수도 있습니다. 새 사이트별 설정을 만들려면 **New-CsCpsConfiguration** cmdlet을 사용합니다. 기존 설정을 수정하려면 **Set-CsCpsConfiguration** cmdlet을 사용합니다.

<div>


> [!NOTE]  
> 대기된 통화의 시간이 초과되고 되걸기가 실패하는 경우 최소한 대체 대상에서 사용할 <STRONG>OnTimeoutURI</STRONG> 옵션을 구성하는 것이 좋습니다.



</div>

**New-CsCpsConfiguration** cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용하여 다음 설정 중 원하는 항목을 구성합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>옵션</th>
<th>지정 내용</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>전화를 받았던 전화기에 벨이 다시 울릴 때까지 통화를 대기하고 있는 시간입니다.</p>
<p>hh:mm:ss 형식으로 시간, 분 및 초를 지정하여 값을 입력해야 합니다. 최소값은 10초이고 최대값은 10분입니다. 기본값은 00:01:30입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Enablemusiconhold-</strong></p></td>
<td><p>통화를 대기하는 동안 전화를 건 사람에게 음악이 재생되는지 여부입니다.</p>
<p>값은 True 또는 False이고, 기본값은 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>대기된 통화를 <strong>OnTimeoutURI</strong>에 대해 지정된 대체 URI(Uniform Resource Identifier)에 전달할 때까지 해당 통화가 전화기에서 다시 울리는 횟수입니다. 기본값은 1입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용할 ontimeouturi</strong></p></td>
<td><p><strong>MaxCallPickupAttempts</strong>가 초과될 때 응답하지 않은 대기된 통화를 경로 지정할 사용자 또는 응답 그룹의 SIP 주소입니다.</p>
<p>값은 문자열 sip:로 시작하는 SIP URI여야 합니다(예: sip:bob@contoso.com). 기본적으로는 전달 주소가 지정되지 않습니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>통화 대기 설정을 구성 하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <STRONG>Get-CsSite</STRONG> cmdlet을 사용하여 사이트를 식별합니다. 자세한 내용은 Lync Server Management Shell 설명서를 참조 하십시오.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 통화 대기 음악 사용자 지정](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[New-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

