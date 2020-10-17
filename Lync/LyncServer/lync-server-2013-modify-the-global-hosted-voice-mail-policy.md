---
title: 'Lync Server 2013: 글로벌 호스팅된 음성 메일 정책 수정'
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
ms.openlocfilehash: f9a7e9dcb3c626c076d51fa32fa195f0787a922c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515175"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 호스팅된 글로벌 음성 메일 정책 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

*글로벌* 호스팅된 음성 메일 정책은 Lync Server 2013와 함께 설치 됩니다. 필요에 맞게 수정할 수는 있지만 이름을 바꾸거나 삭제할 수는 없습니다. 전역 정책을 수정 하려면 Set-CsHostedVoicemailPolicy cmdlet을 사용 하 여 특정 배포에 대 한 적절 한 값으로 매개 변수를 설정 합니다.

[Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>글로벌 호스팅된 음성 메일 정책을 수정 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Set-CsHostedVoicemailPolicy cmdlet을 실행 하 여 환경에 대 한 전역 정책 매개 변수를 설정 합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    이 명령은 정책의 Identity 매개 변수를 지정 하지 않으므로 Windows PowerShell 명령줄 인터페이스는 글로벌 호스팅된 음성 메일 정책에서 다음 값을 설정 합니다.
    
      - **Destination**은 호스팅된 Exchange UM 서비스의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 매개 변수는 선택 사항이지만 호스팅된 음성 메일에 대해 사용자를 활성화하려는 경우 사용자에게 할당된 정책에 Destination 값이 없으면 활성화가 실패합니다.
    
      - **조직** 홈 Lync Server 사용자가 사용 하는 쉼표로 구분 된 Exchange 테 넌 트 목록을 지정 합니다. 각 테넌트는 호스트된 Exchange UM 서비스에 있는 해당 테넌트의 FQDN으로 지정해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이전 예제 cmdlet에서 "corp1.litwareinc.com" 값은 조직 매개 변수에 이미 있을 수 있는 모든 값을 바꿉니다. 예를 들어 정책에 이미 쉼표로 구분 된 조직 목록이 포함 되어 있는 경우 전체 목록이 대체 됩니다. 전체 목록을 대체 하는 대신 목록에 조직을 추가 하려면 다음과 같은 명령을 실행 합니다.

    
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

