---
title: 'Lync Server 2013: 공통 영역 전화 연락처 개체 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699fd4413e071a9377369a383c9fd379a3451c6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013에서 공통 영역 전화 연락처 개체 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

모든 공통 영역 전화에 대 한 Active Directory 도메인 서비스 대화 상대 개체를 만들려면 **move-cscommonareaphone** cmdlet을 사용 합니다. 이 cmdlet은 공통 영역 전화와 함께 사용할 새 대화 상대 개체를 만들거나 기존 연락처 개체를 새 공통 영역 전화와 연결할 수 있습니다. 공통 영역 전화와 연결 된 대화 상대 개체의 속성을 수정 하려면 **move-cscommonareaphone** cmdlet을 사용 합니다. **Move-cscommonareaphone** 의 선택적 매개 변수를 사용 하면 연락처의 Active Directory 표시 이름 또는 전화선과 연결 된 줄 URI (Uniform resource Identifier)와 같은 항목을 변경할 수 있으며 Lync Server에서 사용할 수 있도록 계정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 사용 가능한 모든 수정 사항에 대 한 자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)의 Parameters 섹션을 참조 하십시오. **Move-cscommonareaphone** 매개 변수에 대 한 자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)를 참조 하십시오.

Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 이러한 두 가지 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>공통 영역 전화 연락처 개체 만들기

  - 새 공통 영역 전화 연락처 개체를 만들려면 **move-cscommonareaphone** cmdlet을 사용 합니다. 연락처 개체를 만들 때는 최소한 다음 정보를 제공 해야 합니다.
    
      - **Lineuri**: 공통 영역 전화에 할당 된 전화 번호입니다. 전화 번호를 지정할 때는 E. 164 형식을 사용 해야 합니다.
    
      - **RegistrarPool**: 연락처 개체를 호스팅할 등록자 풀의 FQDN (정규화 된 도메인 이름)입니다.
    
      - **OU**: 연락처 개체를 만들 Active Directory 컨테이너의 고유 이름입니다.
    
    또한 Active Directory 도메인 서비스 표시 이름을 제공 하는 것이 좋습니다. 그렇지 않은 경우에는 GUID를 사용 하 여 전화 Id를 지정 해야 합니다. 예:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>공통 영역 전화 연락처 개체 수정

  - 기존 공통 영역 전화의 속성을 수정 하려면 contact 개체는 **move-cscommonareaphone** cmdlet을 사용 합니다. 예를 들어 다음 명령은 DisplayName 로비를 사용 하 여 공통 영역 전화에 대 한 SIP 주소를 구성 합니다.
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 및 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) Cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

