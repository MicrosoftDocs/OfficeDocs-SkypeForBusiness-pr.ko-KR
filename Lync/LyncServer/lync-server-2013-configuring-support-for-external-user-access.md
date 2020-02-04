---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 지원 구성'
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
ms.openlocfilehash: 143e7e661f793f7a05cb2fdbad8cdab8acaf660e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자 액세스에 대한 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

외부 사용자를 지원 하기 위한 첫 번째 단계는 Edge 서버 또는 Edge 풀 배포입니다. Edge 서버 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요. 정책 구성에 대 한 중요 한 고려 사항은 정책의 우선 순위와 정책이 적용 되는 방법을 이해 하는 것입니다. 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.

Edge 서버 또는 Edge 풀 설정을 완료 한 후에 제공 하려는 외부 사용자 액세스 유형을 사용 하도록 설정 하 고 외부 액세스에 대 한 설정을 구성 해야 합니다. Lync Server 2013에서 lync Server 제어판, Lync Server 관리 셸 또는 둘 다를 사용 하 여 외부 사용자 액세스 및 정책을 설정 하 고 작업 요구 사항에 따라 구성 합니다.

외부 사용자 액세스를 지원 하려면 다음 두 가지 작업을 수행 해야 합니다.

  - **조직에 대 한 지원을 사용**   하도록 설정 배포에서 외부 사용자 액세스 지원을 사용 하도록 설정 하려면 지원 하려는 각 외부 액세스 유형을 사용 하도록 설정 합니다. 전역 설정을 편집 하거나 Lync Server 제어판의 **페더레이션 및 외부 액세스** 그룹에 있는 **외부 액세스 정책** 페이지에서 사이트 또는 사용자 정책을 만들고 구성 하거나 lync server 관리 셸 및 연결 된 cmdlet을 사용 하 여 외부 사용자 액세스 지원을 사용 하거나 사용 하지 않도록 설정 합니다. **외부 액세스 정책을** 관리 하는 Cmdlet은 [Lync Server 2013의 항목 페더레이션 및 외부 액세스 cmdlet](https://docs.microsoft.com/powershell/module/skype/)에서 찾을 수 있습니다. 외부 액세스를 지원 하도록 설정 하면 Lync Server 액세스에 지 서비스를 실행 하는 서버에서 외부 사용자 및 서버와의 통신을 지원 하도록 지정 합니다. 외부 사용자 액세스를 사용할 수 없거나 정책이 아직 지원 하도록 구성 되지 않은 경우 내부 및 외부 사용자는 통신할 수 없습니다.

  - **하나 이상의 정책을**   구성 하 고 할당 하 여 외부 사용자 액세스를 지원 하려면 다음을 포함 하는 요구 사항을 처리 하도록 정책을 구성 합니다.
    
      - ****   사이트 또는 사용자 범위를 사용 하 여 만든 외부 액세스 정책 (전역 정책은 기본적으로 존재 하 고 설정 되지 않음). 페더레이션 사용자 액세스 (선택 하는 경우, 페더레이션 XMPP 도메인 포함), 원격 사용자 사용자 액세스 및 지원 되는 공용 IM 서비스 공급자를 비롯 하 여 하나 이상의 외부 사용자 액세스 유형에 대 한 사용을 제어 하는 정책을 만들고 구성 합니다. 글로벌 정책 또는 하나 이상의 관리적으로 만든 사이트 및 사용자 정책, **페더레이션 및 외부 액세스** 그룹의 **외부 액세스 정책** 페이지에서 외부 정책을 사용 하 여 Lync Server 제어판에서 구성 합니다. 전역 정책은 삭제할 수 없습니다. 특정 사이트 또는 사용자에 대 한 외부 사용자 액세스를 제한 하는 데 사용 하려는 사이트 및 사용자 정책을 만들고 구성 합니다. 전역 및 사이트 정책이 자동으로 할당 됩니다. 사용자 정책을 만들고 구성 하는 경우 사용자 페이지의 Lync Server 제어판 **에서 사용자 구성** 페이지를 사용 하 여 특정 사용자에 게 할당 해야 합니다. 이 정책을 적용 하 고 정책을 할당 하려는 사용자를 찾습니다. 를 선택 하 여 적용 합니다. 사용자에 게 구성 된 사용자 정책을 할당 하려면 lync [Server 2013에서 lync를 사용 하는 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)을 참조 하세요. 각 외부 사용자 액세스 정책은 원격 사용자 액세스, SIP 페더레이션 사용자 액세스, XMPP 페더레이션된 사용자 액세스 및 공용 IM 연결 중 하나 이상을 지원할 수 있습니다.
    
      - **회의 정책**   조직의 사용자에 게 자신이 호스트 하는 회의에 대 한 익명 사용자 초대를 비롯 하 여 조직의 회의를 제어 하는 정책을 만들고 구성 합니다. Lync Server 제어판 **회의** 페이지에는 실제 회의에 대 한 설정을 제어 하는 전역, 사이트 및 사용자 범위의 정책 설정이 있습니다. 자세한 내용은 [Lync Server 2013에서 모임 및 회의 관리](lync-server-2013-managing-meetings-and-conferences.md)를 참조 하세요. **액세스 경계 구성** 페이지에서 회의, 원격 사용자, 페더레이션 사용자에 대해 익명 사용자를 사용할 수 있도록 설정 합니다. **액세스에 지 구성** 에 대 한 정책은 범위 내 전역입니다. 사이트 또는 사용자 정책을 정의 하는 옵션은 없습니다. 범위는 전역, 사이트 또는 사용자 정책 설정을 사용 하 여 **외부 액세스 정책** 페이지에서 제어 됩니다.
        
        예를 들어 사용자가 원격 사용자와 회의를 만들고, 초대 하 고, 관리 하는 것을 허용 하려면 **외부 액세스 정책** 전역, 사이트 또는 사용자 정책에서 **원격 사용자와의 통신 사용** 을 설정 하 고 **액세스에 지 구성** 페이지에서 **원격 사용자와의 통신을 사용** 해야 합니다. 마찬가지로, 익명 사용자 또는 관련 된 연결 파트너 (예: 구성 된 페더레이션 SIP 도메인 및 공급자 (XMPP federation)가 있는 연결 된 파트너가 있는 회의를 허용 하려면 **공용 사용자와의 통신 사용** 을 설정 하 고 **외부 액세스 정책** 전역, 사이트 또는 사용자 정책에서 **페더레이션 사용자와의 통신** 을 설정 합니다. 그런 다음 무료 전역 정책 설정을 선택 하면 **사용자가 회의에 익명으로 액세스할 수** 있으며 **액세스에 지 구성** 페이지에서 **페더레이션 및 공용 IM 연결을 사용** 하도록 설정 합니다.

조직에 대 한 외부 사용자 액세스를 설정 하지 않은 경우에도 외부 사용자 액세스를 제어 하는 데 사용 하려는 모든 정책을 포함 하 여 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 조직에 대 한 외부 사용자 액세스를 사용할 수 있는 경우에만 구성 하는 정책 및 기타 설정이 적용 됩니다. 외부 사용자 액세스를 사용 하지 않도록 설정 하거나 외부 사용자 액세스 정책이 지원 하도록 구성 되어 있지 않은 경우 외부 사용자는 조직의 사용자와 통신할 수 없습니다.

Edge 배포는 외부 사용자의 유형 (익명 사용자를 제외한, 회의를 만들 때 익명 참가자에 게 전송 되는 암호와 회의 ID를 통해 인증 된 자격 증명) 및 컨트롤 (참가자 초대)을 인증 합니다. edge 지원 구성 방법에 따라 액세스 합니다. 통신을 제어 하기 위해 하나 이상의 정책을 구성 하 고 배포 내부 및 외부 사용자 들이 서로 통신 하는 방식을 정의 하는 설정을 구성할 수 있습니다. 정책 및 설정에는 외부 사용자 액세스에 대 한 기본 전역 정책 외에도 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용 하도록 만들기 및 구성할 수 있는 사이트 및 사용자 정책이 포함 됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

