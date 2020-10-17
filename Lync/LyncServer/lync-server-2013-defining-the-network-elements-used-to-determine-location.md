---
title: 'Lync Server 2013: 위치를 확인 하는 데 사용 되는 네트워크 요소 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cfedb09cdcdebdc12cdd2aed69e56532dcca5ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504505"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

자동 클라이언트 위치 검색을 지원 하도록 Lync Server 인프라를 설정 하는 경우 먼저 발신자를 위치에 매핑하는 데 사용할 네트워크 요소를 결정 해야 합니다. Lync Server 2013에서는 다음과 같은 계층 2 및 계층 3 네트워크 요소를 위치와 연결할 수 있습니다.

  - WAP(무선 액세스 지점) BSSID(Basic Service Set Identification) 주소(계층 2)

  - LLDP 스위치 포트(계층 2)

  - LLDP 스위치 섀시 ID(계층 2)

  - IP 서브넷(계층 3)

  - 클라이언트 MAC 주소(계층 2)

네트워크 요소는 우선 순위대로 나열되어 있습니다. 두 개 이상의 네트워크 요소를 사용 하 여 클라이언트를 찾을 수 있는 경우 Lync Server에서는 우선 순위를 사용 하 여 사용할 메커니즘을 결정 합니다.

다음 섹션에서는 각 네트워크 요소 사용에 대해 자세하게 설명합니다.

<div>


> [!IMPORTANT]  
> 네트워크 요소를 사용 하 여 발신자를 위치에 매핑하는 경우 위치 정보 서비스 데이터베이스를 최신 상태로 유지 하는 것이 가장 중요 합니다. 예를 들어 WAP를 추가하는 등 네트워크 요소를 추가하거나 변경하려면 오래된 항목을 삭제하고 위치 데이터베이스에 새 항목을 추가해야 합니다.



</div>

<div>

## <a name="wireless-access-point"></a>무선 액세스 지점

클라이언트가 네트워크에 무선으로 연결하면 위치 요청이 WAP의 BSSID 주소를 사용하여 해당 위치를 확인합니다. 클라이언트가 로밍 중인 경우 표시된 WAP는 가장 가까운 항목이 아닐 수 있으며, 건물 내 다른 층에 있는 WAP가 선택될 수도 있습니다. 위치가 대략적임을 표시하기 위해 위치 값 앞에 Near 또는 Close to 설명자를 추가할 수 있습니다.

이 위치 방식은 각 WAP의 BSSID가 정적인 것으로 가정합니다. 하지만 WAP 공급업체가 동적으로 지정되는 BSSID를 사용할 경우 WAP에서 가져온 BSSID가 변경될 수 있으며(WAP 구성 변경 후 발생할 수 있음) 그로 인해 무선 클라이언트가 위치 정보를 수신하지 못할 수 있습니다. 이러한 가능성을 방지 하려면 각 WAP에서 사용 되는 모든 가능한 BSSID 주소에 대해 위치 정보 서비스 데이터베이스를 ERLs로 채워야 합니다.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP 포트 및 스위치

LLDP-MED(Link Layer Discovery Protocol-Media Endpoint Discover)를 지원하는 관리되는 이더넷 스위치는 자신의 ID 및 포트 정보를 LLDP-MED 호환 클라이언트에 광고할 수 있으며, 위치 데이터베이스에 대해 이를 쿼리하여 장치 위치를 제공할 수 있습니다. 스위치 섀시 ID에서만 ERL을 연결하거나 이를 포트 수준으로 매핑할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서는 Windows 8에서 실행 되는 lync Phone Edition 장치 및 Lync 2013의 위치만 확인 하기 위해 LLDP를 사용할 지를 지원 합니다. 스위치 수준 계층 2 데이터를 사용 하 여 다른 유선 PC 기반 Lync 클라이언트의 위치를 확인 해야 하는 경우에는 클라이언트 MAC 주소 메서드를 사용 해야 합니다.



</div>

</div>

<div>

## <a name="subnet"></a>서브넷

계층 3 IP 서브넷은 클라이언트 위치를 자동으로 검색 하는 데 사용할 수 있는 모든 Lync Server 클라이언트에서 지 원하는 메커니즘을 제공 합니다. 유선 클라이언트를 구성 및 관리하는 데에는 IP 서브넷을 사용하는 것이 가장 간편한 위치 방식입니다. 하지만 서브넷을 사용하도록 결정하기 전에 다음과 같은 질문을 고려해서 서브넷의 위치 특성이 클라이언트를 정확하게 찾는 데 충분히 적합한지 여부를 확인하십시오.

  - 한 개 또는 그 이상의 클라이언트 서브넷으로 여러 층이 지원됩니까?

  - 한 개 또는 그 이상의 서브넷으로 건물 외부까지 지원됩니까?

  - 각 클라이언트 서브넷으로 몇 층까지 지원됩니까?

서브넷이 너무 넓은 영역을 지원할 경우, 클라이언트 위치를 찾기 위한 다른 메커니즘을 사용해야 할 수 있습니다. 하지만 실용성을 높이기 위해서는 타사 SNMP 기반 솔루션으로 비용 및 복잡성을 늘리는 대신 ERL 위치 특성 요구 사항을 충족시킬 수 있도록 IP 서브넷 설정을 재구성하는 것이 좋습니다.

</div>

<div>

## <a name="client-mac-address"></a>클라이언트 MAC 주소

클라이언트 컴퓨터의 MAC 주소를 사용하여 발신자를 찾으려면 관리되는 이더넷 스위치가 필요하며, 이러한 스위치에 연결된 Lync 클라이언트의 MAC 주소를 검색할 수 있는 타사 SNMP 솔루션을 배포해야 합니다. SNMP 솔루션은 관리되는 스위치를 지속적으로 폴링하여 각 포트에 연결된 끝점 MAC 주소의 현재 매핑을 가져오고 해당 포트 ID를 가져옵니다. Lync 클라이언트에서 위치 정보 서비스에 대 한 요청을 수행 하는 동안 위치 정보 서비스는 클라이언트의 MAC 주소를 사용 하 여 타사 응용 프로그램을 쿼리 한 다음 일치 스위치 IP 주소 및 포트 Id를 반환 합니다. 위치 정보 서비스는이 정보를 사용 하 여 해당 레코드에 대해 게시 된 계층 2 와이어 맵 매핑 쿼리를 쿼리하고 클라이언트에 대 한 위치를 반환 합니다. 이 옵션을 사용할 경우 스위치 포트 식별자가 SNMP 응용 프로그램 및 게시된 위치 데이터베이스 레코드 사이에 일관적인지 확인하십시오.

<div>


> [!NOTE]  
> 일부 타사 SNMP 솔루션은 관리 되지 않는 액세스 스위치를 지원할 수 있습니다. Lync 클라이언트를 관리 하는 스위치가 관리 되지 않는 배포 스위치에 대 한 업링크를가지고 있는 경우 관리 되는 스위치는 액세스 스위치에 연결 된 클라이언트의 MAC 주소를 SNMP 응용 프로그램에 다시 보고할 수 있습니다. 이 정보를 사용 하면 위치 정보 서비스에서 사용자의 위치를 식별할 수 있습니다. 그러나 관리 되지 않는 스위치의 모든 포트에 하나의 ERL만 할당할 수 있으므로 위치 복구 단위는 포트 수준이 아닌 액세스 스위치의 섀시 수준 에서만 사용할 수 있습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

