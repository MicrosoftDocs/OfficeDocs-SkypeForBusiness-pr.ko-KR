---
title: 'Lync Server 2013: Lync Online 도메인에 대 한 페더레이션 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7568e3e93850301a0c37fc73ae44cf4f5a84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Microsoft Lync Online 2010 고객과 페더레이션 하 여 다음 단계를 완료 해야 합니다.

  - Lync Online 2010 고객의 도메인에 대 한 지원을 구성 합니다 (예: contoso.onmicrosoft.com). 이 설명서의 [Lync Server 2013에서 Lync Online 고객과 페더레이션 하기 위한 필수 구성 요소](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) 에 명시 된 대로 조직에 대해 이미 페더레이션을 사용 하도록 설정 해야 합니다. 페더레이션을 사용 하려면 페더레이션 도메인에서 액세스를 제어 하는 데 사용할 메서드를 지정 해야 합니다. 검색을 사용 하도록 조직을 구성한 경우 조직의 허용 목록에 도메인을 추가 하는 것은 선택 사항입니다. 도메인 검색을 사용 하도록 설정 하지 않은 경우 허용 된 도메인 목록에 Lync Online 고객의 도메인 이름을 추가 해야 합니다. Lync Server 제어판을 사용 하거나 **새-CSAllowedDomain** cmdlet을 실행 하 여 도메인 이름을 추가할 수 있습니다. 도메인의 검색 사용을 포함 하 여 Lync Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 운영 설명서의 [Lync server 2013에서 조직의 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 를 참조 하세요. **새 csalloweddomain** cmdlet을 사용 하 여 도메인을 추가 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [새-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 을 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > Lync Online 고객은 여러 도메인을 가질 수 있습니다. 둘 이상의 도메인에 페더레이션 하려면 페더레이션을 지원할 각 도메인에 대 한 지원을 구성 해야 하며 Lync Online 고객의 관리자는 페더레이션 할 각 도메인에 대해 페더레이션을 설정 해야 합니다.

    
    </div>

  - 페더레이션 하려는 Lync Online 2010 고객 도메인의 호스팅 공급자에 대 한 지원을 구성 합니다. 이 섹션의 절차를 사용 하 여 호스팅 공급자에 대 한 지원을 구성 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계는 페더레이션 파트너의 위치에서 온-프레미스에 배포 되는 도메인과 페더레이션에 대 한 것이 아니라 Lync Online 고객의 도메인과 페더레이션 할 때만 필요 합니다.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>호스팅 공급자에 대 한 지원을 구성 하려면

1.  프런트 엔드 서버에서 Lync Server Management Shell을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server management shell**을 클릭 합니다.

2.  **새-CsHostingProvider** cmdlet을 실행 하 여 호스팅 공급자를 만들고 구성 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Id** 는 만들려는 호스팅 공급자에 대 한 고유한 문자열 값 식별자를 지정 합니다. 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **VerificationLevel** 는 호스팅 공급자가 보낸 메시지를 확인 하 여 해당 공급자 로부터 보냈는지 확인 하는 방법을 지정 합니다.
    
      - **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True **로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace **는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
    
      - **HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Lync Server 계정을 호스트 하는지 여부를 나타냅니다. **False **로 설정하면 공급자가 Microsoft Exchange 계정 등과 같은 다른 계정 유형을 호스팅합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.
    
    이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [새-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

