---
title: 호스팅된 Exchange UM과의 통합을 위한 에지 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d9d37e5ed9127c81f0aec4fcdc8f2e90b5940f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>호스팅된 Exchange UM과의 통합을 위한 에지 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-01-23_

Lync Server 2013 사용자에 게 호스팅된 Exchange UM (통합 메시징)에 대 한 음성 메일 기능을 제공 하려면 Edge 서버에서 다음 구성 작업을 수행 해야 합니다.

  - 에지 서버에서 페더레이션을 사용할 수 있도록 구성합니다.

  - 중앙 관리 저장소 데이터를 Edge 서버에 복제 하 고 복제를 확인 합니다.

  - 에지 서버에서 호스팅 공급자 만들기

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

  - [신규-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> 이러한 단계를 수행하기 전에 호스팅 Exchange 서비스용 외부 DNS SRV 레코드를 만들어야 합니다. 자세한 내용은 <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">호스팅된 EXCHANGE UM과 통합 하기 위한 DNS SRV 레코드 만들기</A>를 참조 하세요.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>에지 서버에서 페더레이션을 사용할 수 있도록 구성하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  Set-CsAccessEdgeConfiguration cmdlet를 실행하여 서버에서 페더레이션을 사용할 수 있도록 구성합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **UseDnsSrvRouting **은 페더레이션 요청을 보내고 받을 때 에지 서버가 DNS SRV 레코드를 기반으로 하도록 지정합니다.
    
      - **AllowFederatedUsers **는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다. 이 속성은 내부 사용자가 분할 도메인 시나리오의 사용자와 통신할 수 있는지 여부도 결정합니다.
    
      - **Enable지정 검색** Lync Server에서 Active Directory 허용 도메인 목록에 나열 되지 않은 파트너 도메인을 검색 하는 데 DNS 레코드를 사용할지 여부를 결정 합니다. False 인 경우, Lync Server 2013는 허용 된 도메인 목록에 있는 도메인만 페더레이션 합니다. 이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다. 대부분의 배포에서는 페더레이션을 일부 파트너로 제한하기 위해 이 값이 false로 설정됩니다.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>에지 서버에 데이터를 복제하고 복제되었는지 확인하려면

  - 에지 서버로의 복제가 완료되었는지 확인합니다. 절차에 대 한 자세한 내용은 [Lync Server 2013에서 내부 서버 및 Edge 서버 간 연결 확인](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)을 참조 하세요.

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>에지 서버에서 호스팅 공급자를 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  **New-CsHostingProvider** cmdlet을 실행하여 호스팅 공급자를 구성합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Identity **는 만들고 있는 호스팅 공급자에 대한 고유한 문자열 값 ID를 지정합니다(이 예의 경우 **Fabrikam.com **). 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True **로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace **는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
        
        <div>
        

        > [!NOTE]
        > True로 설정 <CODE>EnableSharedAddressSpace</CODE> 하기 전에 내부적으로 페더레이션 SRV 레코드를 확인 하세요. 이 레코드를 내부적으로 확인할 수 없는 경우에는 _tcp _sipfederationtls 레코드를 만들어야 합니다. &lt;도메인&gt; 및 _sip. _tls. &lt;내부&gt; DNS의 도메인 이러한 레코드는 에지 서버의 액세스 인터페이스에 대한 외부 IP 주소를 가리켜야 합니다.

        
        </div>
    
      - **HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Lync Server 2013 계정을 호스트 하는지 여부를 나타냅니다. **False **로 설정하면 공급자가 Microsoft Exchange 계정 등과 같은 다른 계정 유형을 호스팅합니다.
    
      - **ProxyFQDN **은 호스팅 공급자에서 사용되는 프록시 서버에 대해 FQDN(정규화된 도메인 이름)을 지정합니다(이 예의 경우 **proxyserver.fabrikam.com **). 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 2013 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.
    
      - **VerificationLevel **은 호스팅 공급자에 대해 보내고 받는 메시지에 허용되는 확인 수준을 나타냅니다. **UseSourceVerification**(호스팅 공급자에서 보내는 메시지에 포함된 확인 수준 사용)으로 설정합니다. 이 수준을 지정하지 않으면 메시지가 확인할 수 없는 항목으로 간주되어 거부됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 토폴로지 내보내기 및 에지 설치용 외부 미디어에 토폴로지 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Lync Server 2013에서 내부 서버와 에지 서버 간의 연결 확인](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[신규-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

