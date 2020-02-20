---
title: 'Lync Server 2013: 호스팅된 음성 메일 정책'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 음성 메일 정책

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

*호스팅된 음성 메일 정책은* Lync Server 2013 Exum 라우팅 응용 프로그램에 사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대해 통화를 라우팅할 위치에 대 한 정보를 제공 합니다.

<div>


> [!NOTE]  
> 호스팅된 음성 메일 정책은 Lync Server 2013와 호스팅된 Exchange UM의 통합에만 필요 합니다. 온-프레미스 Exchange UM과 통합할 경우에는 필요하지 않습니다.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>호스팅된 음성 메일 정책 범위

호스팅된 음성 메일 정책 범위는 정책이 적용되는 계층 수준을 결정합니다. 다음과 같은 범위 수준으로 호스팅된 음성 메일 정책을 구성할 수 있습니다.

  - *전역* 정책은 잠재적으로 Lync Server 2013 배포의 모든 사용자에 게 영향을 줄 수 있습니다. 사용자에 게 호스팅된 Exchange UM 액세스를 사용 하도록 설정 하 고 사용자별 정책을 할당 하지 않은 경우와 사이트 정책이 사용자 사이트에 할당 되지 않은 경우에는 글로벌 정책이 적용 됩니다. 글로벌 정책은 Lync Server 2013와 함께 설치 됩니다. 필요에 맞게 수정할 수는 있지만 이름을 바꾸거나 삭제할 수는 없습니다.

  - *사이트* 정책은 정책이 정의된 사이트에 속한 모든 사용자에게 영향을 미칠 수 있습니다. 사용자가 호스팅된 Exchange UM에 액세스할 수 있도록 구성되어 있는데 사용자별 정책이 할당되지 않은 경우에는 사이트 정책이 적용됩니다.

  - *사용자별* 정책은 개별 사용자나 그룹에만 영향을 미칠 수 있습니다. 사용자별 정책을 적용하려면 개별 사용자, 그룹 및 대화 상대 개체에 정책을 명시적으로 할당해야 합니다.

<div>


> [!NOTE]  
> 대부분의 경우 호스팅된 음성 메일 정책은 하나만 필요합니다. 요구 사항을 모두 충족하기 위해 전역 정책을 수정해야 하는 경우도 있습니다. 호스팅된 음성 메일 정책을 여러 개 배포할 경우 이러한 모든 정책에는 사용자별 범위가 지정됩니다.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>호스팅된 음성 메일 정책 특성

음성 메일 정책은 Lync Server 2013 ExUM 라우팅 응용 프로그램이 호스팅된 Exchange UM 구현으로 전송 되는 초대 메시지의 요청 URI에 삽입 하는 두 가지 특성을 정의 합니다.

  - **대상:** 호스팅된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)입니다. 이 값은 라우팅 목적으로 온-프레미스 Lync Server에 지 서버에서 사용 됩니다.
    
    <div>
    

    > [!NOTE]  
    > Exchange Online의 FQDN은 exap.um.outlook.com입니다.

    
    </div>

  - **조직:** Lync Server 2013 사용자 사서함을 홈으로 하는 호스팅된 Exchange UM 서비스에 대 한 테 넌 트의 FQDN입니다. 음성 메일 정책에는 여러 개의 조직이 포함될 수 있습니다. 정책에 조직이 두 개 이상 포함 되어 있는 경우이 특성은 Lync Server 2013 사용자 사서함을 홈으로 하는 Exchange Server 테 넌 트의 쉼표로 구분 된 목록 이어야 합니다.

<div>


> [!NOTE]  
> 호스팅된 Exchange UM 서비스의 테넌트 관리자는 Destination 및 Organization 특성 설정에 필요한 값을 제공합니다. 정책을 구성하려면 New-CsHostedVoicemailPolicy cmdlet를 실행하거나 Set-CsHostedVoicemailPolicy cmdlet를 사용하여 기존의 정책(예: 전역 정책)을 수정해야 합니다.



</div>

호스팅된 음성 메일 정책을 관리 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - Set-cshostedvoicemailpolicy

  - Set-cshostedvoicemailpolicy

  - Set-cshostedvoicemailpolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>사용자별 음성 메일 정책 할당

호스팅된 음성 메일 정책이 사용자별 범위에서 정의된 경우 정책을 명시적으로 할당해야 합니다. Grant-CsHostedVoicemailPolicy cmdlet를 실행하여 정책을 개별 사용자나 그룹에 할당할 수 있습니다.

사용자별 호스팅 음성 메일 정책을 할당 하거나 제거 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - Set-cshostedvoicemailpolicy

  - Set-cshostedvoicemailpolicy을 제거 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

