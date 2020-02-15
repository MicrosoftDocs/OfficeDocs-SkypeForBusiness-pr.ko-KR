---
title: Exchange Online과 온-프레미스 Lync Server의 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca82ae3078a2fd158e48f0dcd5906e3ae6d6983d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Exchange Online과 온-프레미스 Lync Server 2013의 통합 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2018-03-30_

온-프레미스 Lync Server 2013 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App과의 상호 운용성을 구성할 수 있습니다. 상호 운용성 기능에는 Outlook Web App 인터페이스와 통합된 Single Sign-On, 메신저, 현재 상태 등이 있습니다. 이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 Lync Server 배포에서에 지 서버를 구성 해야 합니다.

  - 공유 SIP 주소 공간 구성

  - 에 지 서버에서 호스팅 공급자 구성

  - 업데이트 된 중앙 관리 저장소의 복제 확인

Lync Server 2013이 Exchange Online과 통합 된 경우 OWA에서 IM에 로그인을 시도 하는 사용자는 원격 또는 외부 사용자로 간주 됩니다. 이 시나리오에서는이 사용자에 게 다음 옵션을 선택 하는 외부 액세스 정책이 할당 되어 있어야 합니다.

**원격 사용자와의 통신 사용**

조직의 사용자 (예: 재택 근무자, 출장 중인 사용자)가 인터넷을 통해 Lync Server에 연결할 수 있게 하려면이 옵션을 사용 하도록 설정 합니다.

자세한 내용은 [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)를 참조 하세요.

<div>

## <a name="configure-a-shared-sip-address-space"></a>공유 SIP 주소 공간 구성

Exchange Online과 온-프레미스 Lync Server 2013을 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다. Lync Server와 Exchange Online 서비스 둘 다에서 동일한 SIP 도메인 주소 공간이 지원 됩니다.

Lync Server 관리 셸을 사용 하 여 다음 예에 표시 된 매개 변수를 사용 하 여 **set-csaccessedgeconfiguration** cmdlet을 실행 하 여 페더레이션을 위한에 지 서버를 구성 합니다.

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers**는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다. 또한이 속성은 내부 사용자가 Lync Server 및 Exchange Online을 사용 하는 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.

Lync Server 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>에지 서버에서 호스팅 공급자 구성

Lync Server 관리 셸을 사용 하 여에 지 서버에서 호스팅 공급자를 구성 합니다. 이 작업을 수행 하려면 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 합니다.

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 중국에서 21Vianet에서 운영 하는 Office 365을 사용 하는 경우이 예의 <STRONG>proxyfqdn</STRONG> 매개 변수 값 ("exap.um.outlook.com")을 21vianet에서 운영 하는 서비스에 대 한 FQDN으로 바꿉니다. "exap.um.partner.outlook.cn".



</div>

  - **Identity** 는 만들려는 호스팅 공급자에 대 한 고유 문자열 값 식별자를 지정 합니다 (예: "Exchange Online"). 공백이 포함 된 값은 큰따옴표로 묶어야 합니다.

  - **Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이를 **True**로 설정 해야 합니다.

  - **EnabledSharedAddressSpace**는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다. 이를 **True**로 설정 해야 합니다.

  - **HostsOCSUsers** 는 호스팅 공급자가 Office Communications Server 또는 Lync Server를 호스트 하는 데 사용 되는지 여부를 나타냅니다. 이를 **False**로 설정 해야 합니다.

  - **ProxyFQDN**은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다. Exchange Online의 경우 FQDN은 exap.um.outlook.com입니다.

  - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다. 이를 **False**로 설정 해야 합니다.

  - **Verificationlevel은** 은 호스팅된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다. # # **인증**을 지정 합니다. 이 옵션은 호스팅 공급자가 보낸 메시지에 포함 된 확인 수준에 의존 합니다. 이 수준을 지정 하지 않으면 메시지가 확인할 수 없는 것으로 거부 됩니다.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>업데이트된 중앙 관리 저장소의 복제 확인

이전 섹션의 cmdlet을 사용 하 여 변경한 내용은에 지 서버에 자동으로 적용 되며, 일반적으로 복제 하는 데 1 분이 걸리지 않습니다. 다음 cmdlet을 사용 하 여 복제 상태를 확인 하 고 변경 내용이에 지 서버에 적용 되었는지 확인할 수 있습니다.

Lync Server 배포의 내부 서버에서 복제 업데이트를 확인 하려면 다음 cmdlet을 실행 합니다.

    Get-CsManagementStoreReplicationStatus

변경 내용이 적용 되었는지 확인 하려면에 지 서버에서 다음 cmdlet을 실행 합니다.

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 users 사용자에 게 호스팅된 Exchange UM에 대 한 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

