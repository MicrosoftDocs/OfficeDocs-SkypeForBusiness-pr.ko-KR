---
title: 'Lync Server 2013: 호스팅된 Exchange UM 통합 아키텍처'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange UM 통합 아키텍처

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-25_

Lync Server 2013 ExUM 라우팅 응용 프로그램은 온-프레미스 Exchange UM (통합 메시징) 배포, 서비스 공급자가 호스트 하는 Exchange UM 또는 두 가지 조합으로 통합을 지원 합니다. 다음 다이어그램에서는 세 가지 가능성을 모두 보여 줍니다.

**온-프레미스 Exchange UM 배포 및 호스트 된 두 개의 Exchange 공급자와의 통합**

온-프레미스 lync ![Server exchange Um 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 LYNC Server exchange um 배포")

지원 되는 모드는 다음과 같습니다.

  - 온 **-프레미스 배포:** Lync Server 2013 및 Exchange UM은 모두 엔터프라이즈 내의 로컬 서버에 배포 됩니다.

  - **교차 프레미스 배포:** Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되며 Exchange UM은 Microsoft Exchange Online 데이터 센터와 같은 온라인 서비스 공급자의 기능에서 호스팅됩니다.

  - **혼합 배포:** Lync Server 2013 배포에는 엔터프라이즈 내의 로컬 Exchange 서버와 호스트 된 Exchange 서비스 데이터 센터에 있는 일부 사서함에 일부 사용자 사서함이 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 혼합 배포는 사용자에 대 한 평가 및 호스팅 Exchange UM에 대 한 단계별 마이그레이션 중에 사용 하거나 다른 사용자의 Exchange UM 서비스를 사용 하도록 선택 하는 경우 영구 해결 솔루션으로 사용할 수 있습니다.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>공유 SIP 주소 공간

Lync Server 2013를 온-프레미스 Exchange UM 배포와 통합 하려면 Exchange UM Active Directory 도메인 서비스 개체를 읽을 수 있도록 Lync Server 2013 권한을 부여 합니다. 이 접근 방식은 Lync Server 2013 및 Exchange UM이 서로 간에 트러스트 관계 없이 별도의 포리스트에 설치 되어 있기 때문에 호스팅된 Exchange UM과 통합 하는 경우에는 작동 하지 않습니다.

Lync Server 2013을 호스트 된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간*을 구성 해야 합니다. 이 구성에서는 Lync Server 2013와 호스팅된 Exchange UM 서비스 공급자 모두에 동일한 SIP 도메인 주소 공간을 사용할 수 있습니다.

<div>


> [!NOTE]  
> 공유 된 SIP 주소 공간 사용은 일부 사용자가 온-프레미스 배포에 설정 되어 있고 그 일부가 호스팅된 배포 (예: Lync Online)에 속해 있는 교차 프레미스 Lync Server 2013 환경에서 사용 되는 방법과 유사 합니다. SIP 도메인이 그 사이를 분할 합니다. Lync Server 2013을 호스트 된 Exchange UM과 통합 하는 경우 공유 SIP 주소 공간에 Exchange UM 서비스 공급자를 포함 해야 합니다.



</div>

Exchange UM 서비스 공급자와 통합할 공유 SIP 주소 공간을 구성 하려면 아래와 같이 Edge 서버를 구성 해야 합니다.

1.  **Set-CsAccessEdgeConfiguration** cmdlet을 실행 하 여 다음 매개 변수를 설정 하 여 페더레이션의 Edge 서버를 구성 합니다.
    
      - **UseDnsSrvRouting **은 페더레이션 요청을 보내고 받을 때 에지 서버가 DNS SRV 레코드를 기반으로 하도록 지정합니다.
    
      - **AllowFederatedUsers **는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다. 이 속성은 내부 사용자가 분할 도메인 시나리오의 사용자와 통신할 수 있는지 여부도 결정합니다.
    
      - **Enablepartnerdiscovery** Lync Server 2013에서 DNS 레코드를 사용 하 여 Active Directory에서 허용 된 도메인 목록에 나열 되지 않은 파트너 도메인을 검색 하려고 할 때 지정 합니다. False 인 경우, Lync Server 2013는 허용 된 도메인 목록에 있는 도메인에만 페더레이션 합니다. 이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다. 대부분의 배포에서는 페더레이션을 일부 파트너로 제한하기 위해 이 값이 false로 설정됩니다.

2.  중앙 관리 저장소를 Edge 서버에 복제 하 고 복제를 확인 합니다. 자세한 내용은 [Lync Server 2013 토폴로지 내보내기를 참조 하 여 edge 설치에 대 한 배포 설명서의 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 합니다.

3.  **새-CsHostingProvider** cmdlet을 실행 하 여 다음 매개 변수를 설정 하 여 Edge 서버에서 *호스팅 공급자* 를 구성 합니다.
    
      - **Id** 는 만들려는 호스팅 공급자 (예: **호스팅된 Exchange UM**)에 대 한 고유한 문자열 값 식별자를 지정 합니다.
    
      - **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. **True**로 설정 해야 합니다.
    
      - **EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간 시나리오에 사용 되는지 여부를 나타냅니다. **True**로 설정 해야 합니다.
    
      - **HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Lync Server 2013 계정을 호스트 하는지 여부를 나타냅니다. **False**로 설정 되어 있어야 합니다.
    
      - **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버에 대 한 FQDN (정규화 된 도메인 이름)을 지정 합니다 (예: **proxyserver.fabrikam.com**). 이 정보는 호스팅 공급자에 게 문의 하세요. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경 하는 경우 해당 공급자에 대 한 항목을 삭제 한 다음 다시 만들어야 합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 2013 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다. **False**로 설정 되어 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

