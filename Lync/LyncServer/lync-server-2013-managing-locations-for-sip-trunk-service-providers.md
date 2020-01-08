---
title: 'Lync Server 2013: SIP 트렁크 서비스 공급자의 위치 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크 서비스 공급자의 위치 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

네트워크 내에서 클라이언트를 자동으로 찾기 위해 Lync Server를 구성 하려면 네트워크 wiremap 매핑 및 위치 게시를 사용 하 여 위치 정보 서비스 데이터베이스를 채우고 올바른 파일이 이미 포함 된 외부 데이터베이스에 연결 해야 합니다. 매핑에서. 이 프로세스의 일환으로, E9-1-1 서비스 공급자를 사용 하 여 위치의 도심 주소에 대 한 유효성을 검사 해야 합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.

위치 정보 서비스 데이터베이스를 ERL (긴급 응답 위치)로 채우면 도시 주소와 건물 내의 특정 주소로 구성 됩니다. 위치 정보 서비스 **위치** 필드 (건물 내의 특정 위치)는 최대 길이가 20 자 (공백 포함)입니다. 제한 된 길이 내에 다음을 포함 하세요.

  - 응급 응답 자가 도심 주소에 도착할 때 바로 특정 위치를 찾을 수 있도록 911 발신자의 위치를 식별 하는 이해 하기 쉬운 이름입니다. 이 위치 이름에는 건물 번호, 바닥 번호, 날개 지정자, 방 번호 등이 포함 될 수 있습니다. 사람만 사용할 수 있는 애칭을 사용 하지 마세요 .이로 인해 비상 응답 자가 잘못 된 위치로 이동 합니다.

  - 사용자의 Lync 클라이언트가 올바른 위치를 선택 했는지 쉽게 확인할 수 있도록 돕는 위치 식별자입니다. Lync 클라이언트는 검색 된 **위치** 및 **도시** 필드를 해당 머리글에 자동으로 연결 하 여 표시 합니다. 좋은 방법은 각 위치 식별자에 건물의 거리를 추가 하는 것입니다 (예: "1 층 \<거리 번호\>"). 이 주소가 없으면 "1 층"과 같은 일반적인 위치 식별자가 도시의 모든 건물에 적용 될 수 있습니다.

  - 위치가 무선 액세스 지에 따라 결정 되는 근사치 인 경우에는 근처에 단어를 추가할 수 있습니다 (예: "가까운 1 층 1234").

<div>


> [!NOTE]  
> 중앙 위치 데이터베이스에 추가 된 위치는 Lync Server Management Shell 명령을 사용 하 여 게시 하 고 풀의 로컬 저장소에 복제 될 때까지 클라이언트에서 사용할 수 없습니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 게시</A> 를 참조 하세요.



</div>

다음 섹션에서는 위치 데이터베이스를 채우고 유지 관리 하기 위해 고려해 야 할 고려 사항에 대해 설명 합니다.

<div>

## <a name="populating-the-location-database"></a>위치 데이터베이스 채우기

다음 질문은 위치 데이터베이스를 채우는 방법을 결정 하는 데 도움이 될 수 있습니다.

  - **위치 데이터베이스를 채우는 데 어떤 프로세스를 사용할 수 있나요?**  
    데이터는 어디에 있으며 데이터를 위치 데이터베이스에서 요구 하는 형식으로 변환 하기 위해 수행 해야 하는 단계는 무엇 인가요? CSV 파일을 사용 하 여 개별적으로 또는 대량으로 위치를 추가 하나요?

<!-- end list -->

  - **위치 매핑이 이미 포함 되어 있는 타사 데이터베이스를 사용 하 고 있나요?**  
    타사 데이터베이스에 연결 하기 위해 Lync 서버의 보조 위치 정보 서비스 옵션을 사용 하면 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다. 이 방법의 장점은 위치를 네트워크 식별자와 연결 하는 것 외에 위치를 사용자와 연결할 수 있다는 것입니다. 즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 가져온 여러 주소를 Lync Server 클라이언트로 반환할 수 있습니다. 그러면 사용자가 가장 적합 한 위치를 선택할 수 있습니다.
    
    위치 정보 서비스와 통합 하려면 타사 데이터베이스가 Lync 서버 위치 요청/응답 스키마를 따라야 합니다. 자세한 내용은에서\[\] <http://go.microsoft.com/fwlink/p/?linkid=213819>"E911WS: E911 지원 프로토콜 사양에 대 한 웹 서비스"를 참조 하세요. 보조 위치 정보 서비스 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보조 위치 정보 서비스 구성을](lync-server-2013-configure-a-secondary-location-information-service.md) 참조 하세요.

위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.

</div>

<div>

## <a name="maintaining-the-location-database"></a>위치 데이터베이스 유지 관리

위치 데이터베이스를 채운 후에는 네트워크 구성 변경으로 데이터베이스를 업데이트 하기 위한 전략을 개발 해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리 하는 방법을 결정 하는 데 도움이 됩니다.

  - **위치 데이터베이스를 업데이트 하는 방법은 무엇 인가요?**  
    위치 데이터베이스에 대 한 업데이트가 필요한 몇 가지 시나리오에는 WAPs, office recabling 추가 (다른 전환 지정) 및 서브넷 확장이 포함 됩니다. 각각의 개별 위치를 직접 업데이트 하거나 CSV 파일을 사용 하 여 모든 위치의 대량 업데이트를 수행할지 여부를 선택 합니다.

<!-- end list -->

  - **Lync 클라이언트 MAC 주소와 포트 및 스위치 식별자를 비교 하는 데 SNMP 응용 프로그램을 사용 하나요?**  
    SNMP 응용 프로그램을 사용 하는 경우 SNMP 응용 프로그램과 위치 데이터베이스 간에 스위치 섀시 및 포트 정보를 일관성 있게 유지 하는 수동 프로세스를 개발 해야 합니다. SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소나 포트 ID를 반환 하는 경우 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없게 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

