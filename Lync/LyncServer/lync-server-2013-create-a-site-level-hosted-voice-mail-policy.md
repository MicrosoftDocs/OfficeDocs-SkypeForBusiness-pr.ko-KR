---
title: 'Lync Server 2013: 사이트 수준 호스팅 음성 메일 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 사이트 수준의 호스팅 음성 메일 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-24_

*사이트* 정책은 정책이 정의 된 사이트에 속한 모든 사용자에 게 영향을 줄 수 있습니다. 사용자가 호스트 된 Exchange UM 액세스에 대해 구성 되어 있고 사용자 단위 정책이 할당 되지 않은 경우 사이트 정책이 적용 됩니다. 사이트 정책을 배포 하지 않은 경우에는 전역 정책이 적용 됩니다.

사이트 정책을 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새로운 CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>사이트 호스팅 음성 메일 정책을 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새 CsHostedVoicemailPolicy cmdlet을 실행 하 여 정책을 만듭니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    이 예제에서는 사이트 범위를 사용 하 여 호스트 된 음성 메일 정책을 만들고 다음 매개 변수를 설정 합니다.
    
      - **Id** 는 범위를 포함 하는 정책에 대 한 고유 식별자를 지정 합니다. 사이트 범위 정책에 대해 id 매개 변수 값을 형식 `site:` * \<이름\>*(예:)으로 지정 해야 합니다. `site:Redmond`
    
      - **대상** 호스트 된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 이 매개 변수는 선택 사항 이지만, 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하려고 하면 사용자의 할당 된 정책에 대상 값이 없는 경우에는 enable이 실패 합니다.
    
      - **설명은** 정책에 대 한 선택적 설명 정보를 제공 합니다.
    
      - **조직** 홈 Lync Server 2013 사용자에 해당 하는 Exchange 테 넌 트의 쉼표로 구분 된 목록을 지정 합니다. 각 테 넌 트는 호스팅된 Exchange UM 서비스에서 해당 테 넌 트의 FQDN으로 지정 되어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

