---
title: 'Lync Server 2013: 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358b595fceb05a377c59479b0a08e100bffb318a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Lync Server 2013에서 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-24_

다음 절차에서는 호스팅된 Exchange UM (통합 메시징)에 대 한 자동 전화 교환 (AA) 또는 SA (구독자 액세스) 연락처 개체를 만드는 방법에 대해 설명 합니다.

자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 Exchange 연락처 개체 관리](lync-server-2013-hosted-exchange-contact-object-management.md) 를 참조 하세요.

연락처 개체를 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [신규-C또는 Um연락처](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-C간 Umcontact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Lync Server 2013 contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정 하기 전에 먼저 호스트 된 음성 메일 정책을 배포 해야 합니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>호스팅된 Exchange UM에 대 한 AA 또는 SA 연락처 개체를 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새-CsExUmContact cmdlet을 실행 하 여 배포에 필요한 연락처 개체를 만듭니다. 예를 들어 AA 및 SA contact 개체를 만들려면 다음을 실행 합니다.
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    이러한 예제에서는 다음 매개 변수를 설정 합니다.
    
      - **SipAddress** 는 연락처 개체의 SIP 주소를 지정 합니다. Active Directory 도메인 서비스에서 사용자 또는 연락처 개체를 구성 하는 데 아직 사용 되지 않은 주소 여야 합니다. 이 값은 앞의 예제에 표시 된 대로\<"sip:*sip 주소*\>" 형식 이어야 합니다.
    
      - **RegistrarPool** 는 등록자 서비스가 실행 되는 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.
        
        <div class=" ">
        

        > [!NOTE]  
        > Exchange UM 연락처 개체는 Lync server 2013 이전의 Lync Server 2013 배포에 포함 된 풀로 이동할 수 없습니다.

        
        </div>
    
      - **OU** 이 연락처 개체를 배치할 Active Directory 조직 구성 단위를 지정 합니다.
    
      - **Displaynumber** 연락처 개체의 전화 번호를 지정 합니다. 각 연락처 개체의 전화 번호는 고유 해야 합니다.
    
      - 자동 **전화 교환** 연락처 개체가 자동 전화 교환 인지 여부를 지정 합니다. 자동 전화 교환은 발신자가 전화 시스템을 탐색 하 고 연락 하려는 상대방에 게 연락할 수 있는 음성 프롬프트 집합을 제공 합니다. 이 매개 변수의 값이 **False** (기본값) 인 경우 구독자 액세스 연락처 개체를 나타냅니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

