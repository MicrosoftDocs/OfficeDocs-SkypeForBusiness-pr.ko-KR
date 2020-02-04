---
title: 'Lync Server 2013: 사용자 단위 호스팅 음성 메일 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-24_

사용자별 *정책은 개별* 사용자, 그룹 및 연락처 개체에만 영향을 줄 수 있습니다. 사용자별 정책을 배포 하려면 하나 이상의 사용자, 그룹 또는 연락처 개체에 정책을 명시적으로 할당 해야 합니다. 자세한 내용은 [Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)을 참조 하세요.

사용자 단위 호스팅 음성 메일 정책을 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새로운 CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>사용자 단위 호스팅 음성 메일 정책을 만들려면 다음을 사용 합니다.

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새 CsHostedVoicemailPolicy cmdlet을 실행 하 여 정책을 만듭니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    앞의 예제에서는 사용자별 범위를 사용 하 여 호스트 된 음성 메일 정책을 만들고 다음 매개 변수를 설정 합니다.
    
      - **Id** 는 범위를 포함 하는 정책에 대 한 고유 식별자를 지정 합니다. 사용자별 범위가 있는 정책의 경우이 매개 변수 값은 ExRedmond와 같은 간단한 문자열로 지정 됩니다.
    
      - **대상** 호스트 된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 이 매개 변수는 선택 사항 이지만, 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하려고 하면 사용자의 할당 된 정책에 대상 값이 없는 경우에는 enable이 실패 합니다.
    
      - **설명은** 정책에 대 한 선택적 설명 정보를 제공 합니다.
    
      - **조직** 홈 Lync Server 2013 사용자에 해당 하는 Exchange 테 넌 트의 쉼표로 구분 된 목록을 지정 합니다. 각 테 넌 트는 호스팅된 Exchange UM 서비스에서 해당 테 넌 트의 FQDN으로 지정 되어야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

