---
title: 'Lync Server 2013: 호스팅된 Exchange 연락처 개체 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-25_

교차 프레미스 배포에서 각 자동 전화 교환 번호와 구독자 액세스 번호에 대해 Contact 개체를 구성 해야 합니다.

호스팅된 Exchange UM과 통합 하려면 연락처 개체를 관리 하는 데 Active Directory Exchange UM 설정에 종속 되어 있기 때문에 ocsumutil을 사용할 수 없습니다. 교차 프레미스 배포의 경우 Lync Server 2013 및 호스트 된 Exchange UM을 별도의 포리스트에 설치 하 고 그 사이에 신뢰 하지 않습니다. 보안상의 이유로 Lync Server 2013 관리자는 Exchange UM Active Directory 설정에 직접 액세스할 수 없습니다. 결과적으로 Lync Server 2013는 Lync Server 2013 및 호스팅된 Exchange UM 서비스에 모두 액세스할 수 있는 *공유 SIP 주소 공간* 에서 연락처 개체를 관리 하는 다양 한 모델을 제공 합니다.

<div>

## <a name="hosted-contact-object-workflow"></a>호스팅된 연락처 개체 워크플로

다음은 호스팅된 Exchange 테 넌 트 관리자를 사용 하 여 연락처 개체를 관리 하는 일반적인 단계입니다.

1.  Exchange 관리자는 Exchange UM 구독자 액세스 및 자동 전화 교환 연락처 개체에 대 한 전화 번호를 요청 합니다.

2.  Lync Server 2013 관리자는 각 전화 번호에 대 한 연락처 개체를 만들고 각 연락처 개체에 대해 호스팅되는 음성 메일 정책을 할당 합니다.

3.  Lync Server 2013 관리자는 전화 번호를 Exchange 관리자에 게 제공 합니다.

4.  Exchange 관리자는 자동 전화 교환 및 구독자 액세스를 위한 적절 한 Exchange UM 다이얼 플랜에 전화 번호를 할당 합니다.

<div>


> [!NOTE]  
> 온-프레미스 배포를 사용 하는 경우에는 연락처 개체에 Lync Server 2013 다이얼 플랜 설정을 구성할 필요가 없습니다.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>호스팅된 연락처 개체 구성

<div>


> [!NOTE]  
> Lync Server 2013 Contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정 하기 전에 먼저 호스트 된 음성 메일 정책을 배포 해야 합니다. 사용 하려는 연락처 개체에 적용 되는 한 정책은 전역, 사이트 수준 또는 사용자 단위 범위로 지정할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.



</div>

교차 프레미스 배포에서 호스트 된 자동 전화 교환 및 구독자 액세스 연락처 개체를 구성 하려면 다음 cmdlet을 사용 해야 합니다.

  - **새-c간 Umcontact** 는 호스팅된 UM에 대 한 새 연락처 개체를 만듭니다.

  - **Set-c고 Umcontact** 는 호스팅된 Exchange UM에 대 한 기존 contact 개체를 수정 합니다.

다음 예에서는 자동 전화 교환 연락처 개체를 만듭니다.

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

이 예제에서는 SIP 주소 sip:exumaa1@fabrikam.com를 사용 하 여 새 Exchange UM Contact 개체를 만듭니다. Lync Server 2013 등록자 서비스가 실행 되는 풀의 이름이 RedmondPool.litwareinc.com입니다. 이 정보가 저장 되는 Active Directory 조직 구성 단위는 OU = ExUmContacts, DC = litwareinc, DC = com입니다. 연락처 개체의 전화 번호는 2065554567입니다. 선택적-자동 전화 교환 $True 매개 변수는이 개체가 자동 수행자 연락처 개체 임을 지정 합니다. -자동 전화 교환 매개 변수를 False (기본값)로 설정 하면 구독자 액세스 연락처 개체를 지정 합니다.

새-CsExUmContact 및 Set-CsExUmContact cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

