---
title: 'Lync Server 2013: 호스팅된 Exchange UM에 대 한 연락처 개체 만들기'
description: 'Lync Server 2013: 호스팅된 Exchange UM에 대 한 대화 상대 개체를 만듭니다.'
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
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562304"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Lync Server 2013에서 호스팅된 Exchange UM에 대 한 대화 상대 개체 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

다음 절차는 호스팅된 Exchange UM(통합 메시징)에 대한 AA(자동 전화 교환), SA(구독자 액세스) 연락처 개체를 만드는 방법에 대해 설명합니다.

자세한 내용은 계획 설명서에서 [Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리](lync-server-2013-hosted-exchange-contact-object-management.md) 를 참조 하십시오.

대화 상대 개체를 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [새 전자 메일 주소](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Lync Server 2013 contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정할 수 있으려면 먼저 해당 연락처에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>호스팅된 Exchange UM에 대한 AA 또는 SA 연락처 개체를 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  New-CsExUmContact cmdlet을 실행하여 배포에 필요한 연락처 개체를 만듭니다. 예를 들어 다음을 실행하여 AA 및 SA 연락처 개체를 만듭니다.
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    이러한 예는 다음 매개 변수를 설정합니다.
    
      - **Nm-server-w15-short** 은 연락처 개체의 SIP 주소를 지정 합니다. Active Directory 도메인 서비스에서 사용자 또는 연락처 개체를 구성 하는 데 사용 되지 않은 주소 여야 합니다. 이 값은 \<*SIP address*\> 앞의 예제에 표시 된 대로 "sip:" 형식 이어야 합니다.
    
      - **RegistrarPool**은 등록자 서비스가 실행되고 있는 풀의 FQDN(정규화된 도메인 이름)을 지정합니다.
        
        <div class=" ">
        

        > [!NOTE]  
        > Exchange UM 연락처 개체는 Lync Server 2013 이전의 Lync Server 2013 배포에 속하는 풀로 이동할 수 없습니다.

        
        </div>
    
      - **OU**는 이 연락처 개체가 위치할 Active Directory 조직 구성 단위를 지정합니다.
    
      - **DisplayNumber**는 연락처 개체의 전화 번호를 지정합니다. 각 연락처 개체의 전화 번호는 고유해야 합니다.
    
      - **AutoAttendant**는 연락처 개체가 자동 전화 교환인지 여부를 지정합니다. 자동 전화 교환은 발신자가 전화 시스템을 탐색하여 연결할 상대방을 찾을 수 있게 하는 음성 안내 집합을 제공합니다. 이 매개 변수의 값이 **False**(기본값)일 경우 연락처 개체는 구독자 액세스 연락처 개체입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

