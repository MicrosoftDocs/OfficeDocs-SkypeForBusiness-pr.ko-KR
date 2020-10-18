---
title: 'Lync Server 2013: 사이트 수준 호스팅된 음성 메일 정책 만들기'
description: 'Lync Server 2013: 사이트 수준의 호스팅된 음성 메일 정책을 만듭니다.'
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
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578374"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 사이트 수준 호스팅된 음성 메일 정책 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

*사이트* 정책은 정책이 정의된 사이트가 홈으로 지정된 모든 사용자에게 영향을 줄 수 있습니다. 사용자가 호스팅된 Exchange UM에 액세스할 수 있도록 구성되어 있는데 사용자별 정책이 할당되지 않은 경우에는 사이트 정책이 적용됩니다. 사이트 정책을 배포하지 않은 경우에는 글로벌 정책이 적용됩니다.

사이트 정책 구성에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>사이트 호스팅된 음성 메일 정책을 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  New-CsHostedVoicemailPolicy cmdlet을 실행하여 정책을 만듭니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    이 예제에서는 사이트 범위를 포함하는 호스팅된 음성 메일 정책을 만들고 다음 매개 변수를 설정합니다.
    
      - **Identity**는 정책의 고유한 식별자를 지정합니다(범위 포함). 사이트 범위가 포함 된 정책의 경우에는 Identity 매개 변수 값을 형식으로 지정 해야 `site:` *\<name\>* 합니다 (예:) `site:Redmond` .
    
      - **Destination**은 호스팅된 Exchange UM 서비스의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 매개 변수는 선택 사항이지만 호스팅된 음성 메일에 대해 사용자를 활성화하려는 경우 사용자에게 할당된 정책에 Destination 값이 없으면 활성화가 실패합니다.
    
      - **Description**은 옵션 매개 변수로, 정책에 대한 설명 정보를 제공합니다.
    
      - **조직** 홈 Lync Server 2013 사용자에 해당 하는 쉼표로 구분 된 Exchange 테 넌 트 목록을 지정 합니다. 각 테넌트는 호스트된 Exchange UM 서비스에 있는 해당 테넌트의 FQDN으로 지정해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

