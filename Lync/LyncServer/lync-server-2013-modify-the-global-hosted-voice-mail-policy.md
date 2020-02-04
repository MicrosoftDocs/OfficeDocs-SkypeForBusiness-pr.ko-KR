---
title: 'Lync Server 2013: 글로벌 호스팅 음성 메일 정책 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013의 글로벌 호스팅 음성 메일 정책 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-24_

*글로벌* 호스팅 음성 메일 정책은 Lync Server 2013와 함께 설치 됩니다. 필요에 맞게 수정할 수 있지만, 이름을 바꾸거나 삭제할 수는 없습니다. 전역 정책을 수정 하려면 Set-CsHostedVoicemailPolicy cmdlet을 사용 하 여 특정 배포에 대 한 적절 한 값으로 매개 변수를 설정 합니다.

[Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>글로벌 호스팅 음성 메일 정책을 수정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  Set-CsHostedVoicemailPolicy cmdlet을 실행 하 여 환경에 대 한 전역 정책 매개 변수를 설정 합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    이 명령은 정책의 Id 매개 변수를 지정 하지 않기 때문에 Windows PowerShell 명령줄 인터페이스는 글로벌 호스팅 음성 메일 정책에서 다음 값을 설정 합니다.
    
      - **대상** 호스트 된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 이 매개 변수는 선택 사항 이지만, 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하려고 하면 사용자의 할당 된 정책에 대상 값이 없는 경우에는 enable이 실패 합니다.
    
      - **조직** 홈 Lync Server 사용자에 게 표시 되는 Exchange 테 넌 트의 쉼표로 구분 된 목록을 지정 합니다. 각 테 넌 트는 호스팅된 Exchange UM 서비스에서 해당 테 넌 트의 FQDN으로 지정 되어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 앞의 예제 cmdlet에서 "corp1.litwareinc.com" 값은 조직 매개 변수에 이미 있을 수 있는 모든 값을 대체 합니다. 예를 들어 정책에 쉼표로 구분 된 조직 목록이 이미 포함 되어 있는 경우 전체 목록이 바뀝니다. 전체 목록을 대체 하는 대신 조직을 목록에 추가 하려는 경우 다음과 같은 명령을 실행 합니다.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

