---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd25dabcf0f3f908d6fa90515cc59179abe784f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

에지 서버 또는 에지 풀을 배포하는 것은 외부 사용자를 지원하기 위한 첫 번째 단계입니다. 에 지 서버를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하십시오. 정책 구성 시 정책 우선 순위와 정책이 적용되는 방식을 이해하는 것이 중요합니다. 한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 대해 자세히 설정 된다는 것을 의미 하며 개체에 대 한 영향을 더 줍니다.

에지 서버 또는 에지 풀 설치를 완료한 후에는 제공할 외부 사용자 액세스 유형을 사용하도록 설정하고 외부 액세스 관련 설정을 구성해야 합니다. Lync Server 2013에서는 작업 요구 사항에 따라 Lync Server 제어판, Lync Server 관리 셸 또는 둘 모두를 사용 하 여 외부 사용자 액세스 및 정책을 설정 하 고 구성 합니다.

외부 사용자 액세스를 지원하려면 다음 작업을 모두 수행해야 합니다.

  - **조직에 대 한 지원 사용**   배포에서 외부 사용자 액세스에 대 한 지원을 사용 하도록 설정 하려면 지원 하려는 각 유형의 외부 액세스를 사용 하도록 설정 합니다. 전역 설정을 편집 하거나 lync server 컨트롤 패널의 **페더레이션 및 외부 액세스** 그룹에 있는 **외부 액세스 정책** 페이지에서 또는 lync server 관리 셸 및 연결 된 cmdlet을 사용 하 여 외부 사용자 액세스에 대 한 지원을 사용 하거나 사용 하지 않도록 설정 합니다. **외부 액세스 정책을** 관리 하기 위한 Cmdlet은 [Lync Server 2013의 항목 페더레이션 및 외부 액세스 cmdlet](https://docs.microsoft.com/powershell/module/skype/)에 나와 있습니다. 외부 액세스를 사용 하도록 설정 Lync Server 액세스에 지 서비스를 실행 하는 서버가 외부 사용자 및 서버와의 통신을 지원 하도록 지정 합니다. 외부 사용자 액세스를 사용 하지 않도록 설정 하거나 정책이 아직 지원 되도록 구성 되지 않은 경우 내부 및 외부 사용자는 통신할 수 없습니다.

  - **하나 이상의 정책을**   구성 하 고 할당 하 여 외부 사용자 액세스를 지원 하려면 다음을 포함 하는 요구 사항을 충족 하도록 정책을 구성 합니다.
    
      - ****   사이트 또는 사용자 범위를 사용 하 여 만든 외부 액세스 정책 (전역 정책은 기본적으로 존재 하며 설정 되지 않음) 페더레이션 사용자 액세스 (선택한 경우, 페더레이션 XMPP 도메인) 원격 사용자 액세스, 지원 되는 공용 IM 서비스 공급자를 비롯 하 여 하나 이상의 외부 사용자 액세스 유형 사용을 제어 하는 정책을 만들고 구성 합니다. 외부 정책은 **페더레이션 및 외부 액세스** 그룹의 **외부 액세스 정책** 페이지에서 글로벌 정책 또는 하나 이상의 관리적으로 만든 사이트 및 사용자 정책을 사용 하 여 Lync Server 제어판에서 구성 합니다. 글로벌 정책은 삭제할 수 없습니다. 특정 사이트 또는 사용자에 대 한 외부 사용자 액세스를 제한 하는 데 사용 하려는 모든 사이트 및 사용자 정책을 만들고 구성 합니다. 전역 및 사이트 정책이 자동으로 할당 됩니다. 사용자 정책을 만들고 구성한 경우 **사용자 페이지의** Lync Server 제어판에 있는 사용자 구성 페이지를 사용 하 여 특정 사용자에 게 할당 해야 합니다. 이 정책을 적용 하 고 정책을 할당 하려는 사용자를 찾습니다. 사용자를 적용할 사람을 선택 합니다. 사용자에 게 구성 된 사용자 정책을 할당 하려면 [Lync Server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)을 참조 하십시오. 각 외부 사용자 액세스 정책은 원격 사용자 액세스, SIP 페더레이션 사용자 액세스, XMPP 페더레이션 사용자 액세스 및 공용 IM 연결 중 하나 이상을 지원할 수 있습니다.
    
      - **회의 정책**   조직의 사용자가 호스트 하는 전화 회의에 익명 사용자를 초대할 수 있는 것을 포함 하 여 조직의 회의를 제어 하는 정책을 만들고 구성 합니다. Lync Server 제어판 **회의** 페이지에서 실제 회의에 대 한 설정을 제어 하는 전역, 사이트 및 사용자 범위의 정책 설정이 됩니다. 자세한 내용은 [Lync Server 2013에서 모임 및 회의 관리](lync-server-2013-managing-meetings-and-conferences.md)를 참조 하세요. **액세스 에지 구성** 페이지에서 회의 익명 사용자, 원격 사용자 및 페더레이션 사용자를 사용하도록 설정할 수 있습니다. **액세스 에지 구성**의 정책은 전역 범위에 있습니다. 사이트나 사용자 정책을 정의할 수 있는 옵션은 없습니다. 범위는 전역, 사이트 또는 사용자 정책 설정을 사용하여 **외부 액세스 정책** 페이지에서 제어됩니다.
        
        예를 들어 사용자가 원격 사용자가 참여하는 회의를 만들고, 초대하며 관리하도록 하려면 **외부 액세스 정책** 전역, 사이트 또는 사용자 정책에서 **원격 사용자와의 통신 사용**을 설정하거나, **액세스 에지 구성** 페이지에서 **원격 사용자와의 통신 사용**을 설정해야 합니다. 이와 마찬가지로 관계가 정의되어 있는 익명 사용자나 페더레이션 파트너와의 회의를 허용하려는 경우(예: 구성된 페더레이션 SIP 도메인 및 공급자 – XMPP 페더레이션에서는 회의를 지원하지 않음) **외부 액세스 정책** 전역, 사이트 또는 사용자 정책에서 **공용 사용자와의 통신 사용**과 **페더레이션 사용자와의 통신 사용**을 설정합니다. 그런 다음 **액세스 에지 구성** 페이지의 **전화 회의에 대한 익명 사용자 액세스 사용**과 **페더레이션 및 공용 IM 연결 사용(Enable federated and public IM connectivity)** 이라는 무료 글로벌 정책 설정을 선택합니다.

조직에서 외부 사용자 액세스를 지원하도록 설정하지 않은 경우에도 외부 사용자 액세스를 제어하는 데 사용할 정책을 포함하여 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 구성한 정책 및 기타 설정은 조직에서 외부 사용자 액세스를 사용하도록 설정한 경우에만 적용됩니다. 외부 사용자 액세스가 해제되어 있거나 지원하는 외부 사용자 액세스 정책이 구성되어 있지 않은 경우에는 외부 사용자가 조직의 사용자와 통신할 수 없습니다.

에지 배포에서는 에지 지원을 구성한 방법에 따라 외부 사용자 유형(전화 회의를 만들고 참가자를 초대할 때 익명 참가자에게 보낸 암호 키와 전화 회의 ID로 인증된 익명 사용자 제외)을 인증하고 액세스를 제어합니다. 통신을 제어하기 위해 하나 이상의 정책을 구성하고 배포 내부 사용자와 외부 사용자가 서로 통신하는 방법을 정의하는 설정을 구성할 수 있습니다. 이러한 정책과 설정에는 외부 사용자 액세스에 대한 기본 글로벌 정책과 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용하도록 설정하기 위해 만들고 구성할 수 있는 사이트 및 사용자 정책이 포함됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013에서 익명 사용자를 지원 하기 위한 회의 정책 할당](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

