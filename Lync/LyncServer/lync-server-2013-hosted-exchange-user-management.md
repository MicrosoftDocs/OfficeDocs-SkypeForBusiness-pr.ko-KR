---
title: 'Lync Server 2013: 호스팅된 Exchange 사용자 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange 사용자 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

호스팅된 Exchange 서비스에 사서함이 있는 Lync Server 2013 사용자에 게 음성 메일 서비스를 제공 하려면 호스트 된 음성 메일에 대 한 사용자 계정을 사용 하도록 설정 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013 사용자가 호스팅된 음성 메일을 사용 하도록 설정할 수 있으려면 먼저 해당 사용자 계정에 적용 되는 호스팅 음성 메일 정책을 배포 해야 합니다. 사용 하도록 설정할 사용자에 게 적용 되는 한, 범위에서 정책이 전역, 사이트 또는 사용자 단위 일 수 있습니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>MsExchUCVoiceMailSettings 특성

Lync Server 2013에는 Lync Server 2013 Active Directory 스키마 준비의 일부로 생성 되는 **msExchUCVoiceMailSettings**이라는 새 사용자 특성이 도입 되었습니다. 이 다중값 특성에는 Lync Server 2013 및 호스팅된 Exchange 서비스에서 공유 하는 음성 메일 설정이 포함 되어 있습니다.

호스트 된 Exchange 서비스는 Exchange UM을 사용 하도록 설정 하거나 사서함을 호스트 된 Exchange 서버로 전송 하는 프로세스 중에 msExchUCVoiceMailSettings 특성 값을 설정할 수 있습니다. 이 특성이 Exchange에 의해 설정 되지 않은 경우 Lync Server 2013 관리자는이 항목의 앞부분에 설명 된 대로 Set CsUser cmdlet을 실행 하 여이 특성을 설정 해야 합니다.

다음 표에는 특성의 키/값 쌍과 해당 작성자가 나와 있습니다.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>MsExchUCVoiceMailSettings 특성 키/값 쌍

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>값</th>
<th>검토자</th>
<th>함</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>교환</p></td>
<td><p>사용자가 Exchange Server에의 한 호스팅된 UM 액세스를 사용 하도록 설정 되었습니다. Exchange UM 라우팅 응용 프로그램은 사용자의 호스팅 음성 메일 정책에 대 한 라우팅 세부 정보를 확인 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>교환</p></td>
<td><p>Exchange Server에의 한 호스팅된 UM 액세스에 대해 사용자를 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail 메일 = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013에서 사용자가 호스팅된 UM 액세스를 사용 하도록 설정 되었습니다. Lync Server 2013 ExUM 라우팅 응용 프로그램은 사용자의 호스팅 음성 메일 정책에 대 한 라우팅 세부 정보를 확인 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail 메일 = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013에서 호스팅된 UM 액세스에 대해 사용자가 사용 하지 않도록 설정 되었습니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lync Server 2013 키/값 쌍 (CSHostedVoiceMail 메일 = 0 또는 CSHostedVoiceMail 메일 = 1) 이외의 값이 특성에 이미 있는 경우, 다른 응용 프로그램에서 특성을 관리할 수 있음을 알리는 경고가 표시 됩니다. 예를 들어 키/값 쌍 ExchangeHostedVoiceMail = 0 또는 ExchangeHostedVoiceMail = 1이 이미 있는 경우 경고가 표시 됩니다. 이 경우 Active Directory를 편집 하 여 값을 변경 하거나 다음 cmdlet을 실행 하 여 값을 null로 설정할 수 있습니다.<BR>Set-CsUser – id 사용자-HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>사용자가 호스팅되는 음성 메일을 사용할 수 있도록 설정

사용자의 음성 메일 통화를 호스트 된 Exchange UM으로 라우팅할 수 있도록 설정 하려면 Set-CsUser cmdlet을 실행 하 여 *HostedVoiceMail* 매개 변수의 값을 설정 해야 합니다. 이 매개 변수는 Lync Server 2013에 "음성 메일 착신 통화" 표시등을 표시 하도록 신호를 보냅니다.

  - 다음 예제에서는 호스팅되는 음성 메일에 Pilar Ackerman의 사용자 계정을 사용 하도록 설정 합니다.
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    이 cmdlet은 호스팅된 음성 메일 정책 (전역, 사이트 수준 또는 사용자 단위)이이 사용자에 게 적용 되는지 확인 합니다. 정책이 적용 되지 않으면 cmdlet이 실패 합니다.

  - 다음 예제에서는 호스팅되는 음성 메일에 대해 Pilar Ackerman의 사용자 계정을 사용 하지 않도록 설정 합니다.
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Cmdlet은이 사용자에 게는 호스트 된 음성 메일 정책 (전역, 사이트 수준 또는 사용자 단위)이 적용 되지 않는지 확인 합니다. 정책이 적용 되 면 cmdlet이 실패 합니다.

Set CsUser cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

