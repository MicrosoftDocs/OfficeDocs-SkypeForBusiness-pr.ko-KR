---
title: 'Lync Server 2013: 고급 Enterprise Voice 기능에 대 한 네트워크 설정'
description: 'Lync Server 2013: 고급 Enterprise Voice 기능에 대 한 네트워크 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f04ba78a4cd2114e6ecffb5b92a7a54facb0df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561424"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Lync Server 2013의 고급 Enterprise Voice 기능에 대 한 네트워크 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-10_

Lync Server에는 3 가지 고급 Enterprise Voice 기능인 CAC (통화 허용 제어), 응급 서비스 (E9-1-1) 및 미디어 바이패스가 있습니다. 이러한 기능은 네트워크 지역, 네트워크 사이트 및 네트워크 사이트와 함께 Lync Server 토폴로지의 각 서브넷 연결에 대 한 특정 구성 요구 사항을 공유 합니다. 이러한 기능의 배포 계획에 대한 자세한 내용은 다음을 참조하십시오.

  - [Lync Server 2013의 통화 허용 제어 계획](lync-server-2013-planning-for-call-admission-control.md)

  - [Lync Server 2013의 응급 서비스 계획 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)

이러한 각 기능을 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하십시오.

이 항목에서는 세 가지 고급 Enterprise Voice 기능에 공통적으로 적용 되는 구성 요구 사항에 대 한 개요를 제공 합니다.

<div>

## <a name="network-regions"></a>네트워크 지역

네트워크 지역은 CAC(통화 허용 제어), E9-1-1 및 미디어 바이패스 구성에만 사용되는 네트워크 허브 또는 네트워크 백본입니다.

<div>


> [!NOTE]  
> 네트워크 지역은 Lync Server 전화 접속 회의 지역과는 동일 하지 않으며 전화 접속 회의 액세스 번호를 하나 이상의 Lync Server 다이얼 플랜과 연결 하는 데 필요 합니다. 전화 접속 회의 지역에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013의 전화 접속 회의 요구 사항</A> 를 참조 하십시오.



</div>

CAC에서는 모든 네트워크 지역에 연결 된 Lync Server 중앙 사이트 (즉, 구성 된 정책에 따라 결정을 내리는 데, 즉, 실시간 오디오 또는 비디오 세션을 설정할 수 있는지 여부에 대 한)가 지역 내의 미디어 트래픽을 관리 합니다. Lync Server 중앙 사이트는 지리적 위치를 나타내는 것이 아니라 풀 또는 풀 집합으로 구성 된 서버의 논리적 그룹입니다. 중앙 사이트에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하십시오. 또한 지원 가능성 설명서의 [Lync Server 2013에서 지 원하는 토폴로지](lync-server-2013-supported-topologies.md) 를 참조 하세요.

네트워크 지역을 구성 하려면 Lync Server 제어판의 **네트워크 구성** 섹션에 있는 **지역** 탭을 사용 하거나, **새-csnetworkregion** 또는 **Set-csnetworkregion** Lync Server 관리 셸 cmdlet을 실행 하면 됩니다. 자세한 내용은 배포 설명서에서 [Lync server 2013의 네트워크 지역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하십시오.

동일한 네트워크 지역 정의는 세 가지 고급 Enterprise Voice 기능을 모두 공유 합니다. 따라서 하나의 기능에 대한 네트워크 지역을 이미 만든 경우 다른 기능에 대한 새 네트워크 지역을 만들 필요가 없습니다. 그러나 기능별 설정을 적용하기 위해 기존 네트워크 지역 정의를 수정해야 하는 경우가 있을 수 있습니다. 예를 들어 E9-1-1(연결된 중앙 사이트 필요 없음)에 대한 네트워크 지역을 만들고 나중에 통화 허용 제어를 배포한 경우 각 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.

Lync Server 중앙 사이트를 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나, **새-csnetworkregion** 또는 **Set-Csnetworkregion** Lync Server 관리 셸 cmdlet을 실행 하 여 중앙 사이트 이름을 지정 합니다. 자세한 내용은 배포 설명서에서 [Lync server 2013의 네트워크 지역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하십시오.

</div>

<div>

## <a name="network-sites"></a>네트워크 사이트

네트워크 사이트는 지점, 지사 또는 본사와 같은 지리적 위치를 나타냅니다. 각 네트워크 사이트는 특정 네트워크 지역과 연결되어야 합니다.

<div>


> [!NOTE]  
> 네트워크 사이트는 고급 Enterprise Voice 기능 에서만 사용 됩니다. 사용자가 Lync Server 토폴로지에서 구성한 분기 사이트와는 다릅니다. 분기 사이트에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013의 참조 토폴로지</A> 를 참조 하십시오. 또한 지원 가능성 설명서의 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013에서 지 원하는 토폴로지</A> 를 참조 하세요.



</div>

네트워크 사이트를 구성 하 고 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸 **새 Csnetworksite** 또는 **Set-csnetworksite** cmdlet을 실행 하면 됩니다. 자세한 내용은 배포 설명서의 [Lync server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하십시오.

</div>

<div>

## <a name="identify-ip-subnets"></a>IP 서브넷 확인

각 네트워크 사이트에 대해 네트워크 관리자와 함께 각 네트워크 사이트에 지정된 IP 서브넷을 확인해야 합니다. 네트워크 관리자가 네트워크 지역 및 네트워크 사이트에 대한 IP 서브넷을 이미 구성한 경우에는 작업이 훨씬 간편합니다.

예를 들어 북미 지역의 뉴욕 사이트에 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24 IP 서브넷을 지정할 수 있습니다. 주로 디트로이트에서 근무하는 Bob이 교육을 받기 위해 뉴욕 사무실에 출장을 왔다고 가정해 보겠습니다. Bob이 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에서 뉴욕에 할당된 네 개 범위 중 하나의 IP 주소(예: 172.29.80.103)를 가져옵니다.

<div>


> [!WARNING]  
> 서버에서 네트워크를 구성하는 동안 지정된 IP 서브넷을 미디어 바이패스에 사용하려면 IP 서브넷이 클라이언트 컴퓨터에서 제공한 형식과 일치해야 합니다. Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크와 함께 IP 주소를 마스크 합니다. 각 클라이언트에 연결된 바이패스 ID를 확인할 때 등록자는 각 네트워크 사이트에 연결된 IP 서브넷 목록이 클라이언트에서 제공한 서브넷과 정확히 일치하는지 비교합니다. 따라서 서버에서 네트워크를 구성할 때 가상 서브넷 대신 실제 서브넷을 입력해야 합니다. 미디어 바이패스가 아니라 통화 허용 제어를 배포한 경우에는 가상 서브넷을 구성한 경우에도 통화 허용 제어가 제대로 작동합니다.<BR>예를 들어 ip 서브넷 마스크가 255.255.255.0 인 IP 주소가 172.29.81.57 인 컴퓨터에 Lync 클라이언트가 로그인 하는 경우에는 서브넷 172.29.81.0와 연결 된 바이패스 ID를 요청 합니다. 서브넷이 172.29.0.0/16으로 정의 된 경우 클라이언트가 가상 서브넷에 속해 있더라도 등록자는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에 해당 등록자는이 일치를 고려 하지 않습니다. 따라서 관리자는 네트워크 구성 중에 서브넷으로 프로 비전 되는 Lync 클라이언트 (동적 호스트 구성 프로토콜 (DHCP))에서 제공 하는 대로 서브넷을 정확히 입력 해야 합니다.



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>서브넷과 네트워크 사이트 연결

엔터프라이즈 네트워크의 모든 서브넷은 네트워크 사이트와 연결 되어야 하며 (즉, 모든 서브넷을 지리적 위치로 연결 해야 함) 이러한 서브넷 연결을 통해 고급 Enterprise Voice 기능을 사용 하 여 끝점을 지리적으로 찾을 수 있습니다. 예를 들어 CAC를 사용 하 여 네트워크 사이트에서 주고 나가는 실시간 오디오 및 비디오 데이터의 흐름을 조정할 수 있습니다.

네트워크 사이트에 서브넷을 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸을 사용할 수 있습니다. 자세한 내용은 배포 설명서에서 [Lync server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 을 참조 하거나 Lync Server 관리 셸 설명서를 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 계획](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013의 응급 서비스 계획 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

