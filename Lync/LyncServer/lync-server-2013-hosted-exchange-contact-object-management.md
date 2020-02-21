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
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-25_

교차 프레미스 배포에서 각 자동 전화 교환 번호 및 구독자 액세스 번호에 대해 대화 상대 개체를 구성해야 합니다.

호스팅된 Exchange UM과의 통합 시 Active Directory Exchange UM 설정에 따라 달라지므로 ocsumutil.exe를 사용하여 연락처 개체를 관리할 수 없습니다. 크로스-프레미스 배포에서 Lync Server 2013와 호스트 된 Exchange UM은 별도의 포리스트에 따로 트러스트 없이 설치 됩니다. 보안상의 이유로 Lync Server 2013 관리자는 Exchange UM Active Directory 설정에 직접 액세스할 수 없습니다. 따라서 Lync Server 2013에서는 Lync Server 2013 및 호스팅된 Exchange UM 서비스 모두에 액세스할 수 있는 *공유 SIP 주소 공간* 에서 연락처 개체를 관리 하기 위한 다양 한 모델을 제공 합니다.

<div>

## <a name="hosted-contact-object-workflow"></a>호스팅된 대화 상대 개체 워크플로

다음은 대화 상대 개체를 관리하기 위해 호스팅된 Exchange 테넌트 관리자가 수행하는 일반적인 단계입니다.

1.  Exchange 관리자가 Exchange UM 구독자 액세스 및 자동 전화 교환 대화 상대 개체에 대한 전화 번호를 요청합니다.

2.  Lync Server 2013 관리자가 각 전화 번호에 대 한 연락처 개체를 만들고 각 대화 상대 개체에 대해 호스팅된 음성 메일 정책을 할당 합니다.

3.  Lync Server 2013 관리자는 Exchange 관리자에 게 전화 번호를 제공 합니다.

4.  Exchange 관리자가 자동 전화 교환 및 구독자 액세스에 적합한 Exchange UM 다이얼 플랜에 전화 번호를 지정합니다.

<div>


> [!NOTE]  
> 온-프레미스 배포와 마찬가지로 연락처 개체에 대해 Lync Server 2013 다이얼 플랜 설정을 구성할 필요가 없습니다.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>호스팅된 대화 상대 개체 구성

<div>


> [!NOTE]  
> Lync Server 2013 Contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정할 수 있으려면 먼저 해당 연락처에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다. 사용하도록 설정할 연락처 개체에 적용되는 경우에는 정책 범위를 전역, 사이트 수준 또는 사용자별로 지정할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.



</div>

교차 프레미스 배포에서 호스팅된 자동 전화 교환 및 구독자 액세스 대화 상대 개체를 구성하려면 다음 cmdlet를 사용해야 합니다.

  - **New-CsExUmContact** - 호스팅된 UM에 대해 새 대화 상대 개체를 만듭니다.

  - **Set-CsExUmContact** - 호스팅된 Exchange UM에 대해 기존의 대화 상대 개체를 수정합니다.

다음은 자동 전화 교환 대화 상대 개체를 만드는 예입니다.

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

이 예에서는 SIP 주소 sip:exumaa1@fabrikam.com을 사용 하 여 새 Exchange UM 연락처 개체를 만듭니다. Lync Server 2013 등록자 서비스가 실행 되는 풀의 이름은 RedmondPool.litwareinc.com입니다. 이 정보가 저장 되는 Active Directory 조직 구성 단위는 OU = ExUmContacts, DC = litwareinc, DC = com입니다. 연락처 개체의 전화 번호는 2065554567입니다. Optional-attendant $True 매개 변수는이 개체가 자동 전화 교환 대화 상대 개체 임을 지정 합니다. -자동 전화 교환 매개 변수를 False (기본값)로 설정 하면 구독자 액세스 대화 상대 개체를 지정 합니다.

새-CsExUmContact 및 Set-CsExUmContact cmdlet에 대 한 자세한 내용은 Lync Server Management Shell 설명서를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

