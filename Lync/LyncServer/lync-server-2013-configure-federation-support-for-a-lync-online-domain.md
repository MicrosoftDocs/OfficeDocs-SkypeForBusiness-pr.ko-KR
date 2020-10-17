---
title: 'Lync Server 2013: Lync Online 도메인에 대 한 페더레이션 지원 구성'
description: 'Lync Server 2013: Lync Online 도메인에 대 한 페더레이션 지원을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553304"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Microsoft Lync Online 2010 고객에 페더레이션 하려면 다음 단계를 완료 해야 합니다.

  - Lync Online 2010 고객 (예: contoso.onmicrosoft.com)의 도메인에 대 한 지원을 구성 합니다. 이 문서의 [Lync Server 2013 섹션에서 Lync Online 고객과 페더레이션 하기 위한 필수 구성 요소](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) 에 지정 된 대로 조직에 대해 페더레이션을 사용 하도록 이미 설정 되어 있어야 합니다. 페더레이션을 설정하려면 페더레이션된 도메인에서 액세스를 제어하기 위해 사용할 방법을 지정해야 합니다. 조직에 검색이 사용되도록 구성한 경우 필요에 따라 도메인을 조직의 허용 목록에 추가할 수 있습니다. 도메인 검색을 사용 하도록 설정 하지 않은 경우에는 Lync Online 고객의 도메인 이름을 허용 도메인 목록에 추가 해야 합니다. Lync Server 제어판을 사용 하거나 **새-CSAllowedDomain** cmdlet을 실행 하 여 도메인 이름을 추가할 수 있습니다. 도메인 검색 사용을 포함 하 여 Lync Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync server 2013에서 조직의 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 를 참조 하십시오. **새 csalloweddomain** cmdlet을 사용 하 여 도메인을 추가 하는 방법에 대 한 자세한 내용은 작업 설명서의 [New-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 를 참조 하십시오.
    
    <div>
    

    > [!NOTE]  
    > Lync Online 고객에 게는 여러 도메인이 있을 수 있습니다. 둘 이상의 도메인에 페더레이션 하려면 페더레이션을 지원할 각 도메인에 대 한 지원을 구성 해야 하며, Lync Online 고객의 관리자는 페더레이션 할 각 도메인에 대해 페더레이션을 사용 하도록 설정 해야 합니다.

    
    </div>

  - 페더레이션 하려는 Lync Online 2010 고객 도메인의 호스팅 공급자에 대 한 지원을 구성 합니다. 이 섹션의 절차에 따라 호스팅 공급자에 대한 지원을 구성합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계는 페더레이션 파트너의 위치에 온-프레미스에 배포 된 도메인과 페더레이션 하지 않고 Lync Online 고객의 도메인과 페더레이션 하는 경우에만 필요 합니다.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>호스팅 공급자에 대한 지원을 구성하려면

1.  프런트 엔드 서버에서 Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.

2.  **New-CsHostingProvider** cmdlet을 실행하여 호스팅 공급자를 만들고 구성합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Identity**는 만들고 있는 호스팅 공급자에 대한 고유 문자열 값 식별자를 지정합니다. 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **ProxyFQDN**은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **VerificationLevel**은 호스팅 공급자가 보낸 메시지가 해당 공급자로부터 전송되었는지 확인하는 방법 또는 여부를 나타냅니다.
    
      - **Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True**로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace**는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
    
      - **HostsOCSUsers** 은 호스팅 공급자가 Lync Server 계정을 호스트 하는 데 사용 되는지 여부를 나타냅니다. **False**인 경우에는 공급자가 Microsoft Exchange 계정 등의 다른 계정 유형을 호스팅합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.
    
    이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 작업 설명서의 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

