---
title: 'Lync Server 2013: 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-10_

Lync Server에는 세 가지 고급 엔터프라이즈 음성 기능 (call 허용 제어 (CAC), 응급 서비스 (E9-1-1), 미디어 바이패스)이 있습니다. 이러한 기능은 네트워크 지역, 네트워크 사이트에 대 한 특정 구성 요구 사항과 네트워크 사이트를 사용 하 여 Lync Server 토폴로지의 각 서브넷에 대 한 연결을 공유 합니다. 이러한 기능 배포를 계획 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

  - [Lync Server 2013의 통화 허용 제어 서비스 계획](lync-server-2013-planning-for-call-admission-control.md)

  - [Lync Server 2013의 응급 서비스 계획(E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)

이러한 각 기능을 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.

이 항목에서는 세 가지 고급 엔터프라이즈 음성 기능에 공통적인 구성 요구 사항에 대 한 개요를 제공 합니다.

<div>

## <a name="network-regions"></a>네트워크 지역

네트워크 지역은 호출 허용 제어 (CAC), E9-1-1 및 미디어 바이패스 구성에만 사용 되는 네트워크 허브나 네트워크 백본입니다.

<div>


> [!NOTE]  
> 네트워크 지역은 Lync Server 전화 접속 회의 영역과 동일 하지 않으며, 전화 접속 회의 액세스 번호를 하나 이상의 Lync Server 다이얼 플랜에 연결 하는 데 필요 합니다. 전화 접속 회의 지역에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013에서 전화 접속 회의 요구 사항을</A> 참조 하세요.



</div>

CAC는 모든 네트워크 영역에 지역 내의 미디어 트래픽을 관리 하는 연결 된 Lync Server 중앙 사이트 (즉, 사용자가 구성한 정책에 기반 하 여 실시간 오디오 또는 비디오 세션을 할 수 있는지 여부에 대 한 결정을 내리는 데 사용 됩니다. 설정). Lync Server 중앙 사이트는 지리적 위치를 나타내지 않고 풀 또는 풀 집합으로 구성 된 서버의 논리 그룹입니다. 중앙 사이트에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하세요. 또한 지원 가능성 문서에는 [Lync Server 2013에서 지원 되는 토폴로지가](lync-server-2013-supported-topologies.md) 표시 됩니다.

네트워크 지역을 구성 하려면 Lync Server 제어판의 **네트워크 구성** 섹션에 있는 **지역** 탭을 사용 하거나, **새-CsNetworkRegion** 또는 **Set csnetworkregion** Lync Server 관리 셸 cmdlet을 실행 하면 됩니다. 지침은 배포 설명서의 [Lync Server 2013에서 네트워크 영역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.

동일한 네트워크 지역 정의는 세 가지 고급 엔터프라이즈 음성 기능 모두에 의해 공유 됩니다. 이미 하나의 기능에 대 한 네트워크 지역을 만든 경우에는 다른 기능에 대해 새 네트워크 지역을 만들 필요가 없습니다. 그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다. 예를 들어 E9 (연결 된 중앙 사이트 필요 없음)에 대 한 네트워크 지역을 만든 경우, 나중에 통화 허용 제어를 배포 하는 경우 각 네트워크 영역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다.

Lync Server 중앙 사이트를 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나, **새** 사이트 이름을 지정 하거나 Csnetworkregion 또는 **Set Csnetworkregion** Lync Server Management Shell cmdlet을 실행 합니다. 지침은 배포 설명서의 [Lync Server 2013에서 네트워크 영역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

<div>

## <a name="network-sites"></a>네트워크 사이트

네트워크 사이트는 지사, 지역 사무소 또는 기본 사무실 등의 지리적 위치를 나타냅니다. 각 네트워크 사이트는 특정 네트워크 지역에 연결 되어 있어야 합니다.

<div>


> [!NOTE]  
> 네트워크 사이트는 고급 엔터프라이즈 음성 기능 으로만 사용 됩니다. 이는 Lync Server 토폴로지에서 구성한 분기 사이트와 동일 하지 않습니다. 지점 사이트에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013에서 참조 토폴로지</A> 를 참조 하세요. 또한 지원 가능성 문서에는 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013에서 지원 되는 토폴로지가</A> 표시 됩니다.



</div>

네트워크 사이트를 구성 하 고 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸 **새 csnetworksite** 또는 **Set csnetworksite** cmdlet을 실행할 수 있습니다. 자세한 내용은 배포 설명서의 [Lync server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

<div>

## <a name="identify-ip-subnets"></a>IP 서브넷 확인

각 네트워크 사이트에 대해 네트워크 관리자와 협력 하 여 각 네트워크 사이트에 할당 되는 IP 서브넷을 확인 해야 합니다. 네트워크 관리자가 이미 네트워크 지역 및 네트워크 사이트로 IP 서브넷을 구성한 경우에는 작업이 대폭 간소화 됩니다.

예를 들어 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24의 IP 서브넷이 할당 될 수 있습니다. 일반적으로 디트로이트에서 작동 하는 사용자의 경우, 교육을 위해 뉴욕 사무실로 이동 하 고, 컴퓨터를 설정 하 여 네트워크에 연결 하면 컴퓨터는 뉴욕에 대해 할당 된 4 개의 범위 (예: 172.29.80.103) 중 하나에 IP 주소를 가져옵니다.

<div>


> [!WARNING]  
> 서버에서 네트워크 구성 중에 지정 된 IP 서브넷은 미디어 바이패스에 사용 하기 위해 클라이언트 컴퓨터가 제공 하는 형식과 일치 해야 합니다. Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크를 사용 하 여 IP 주소를 마스크 합니다. 각 클라이언트와 연결 된 우회 ID를 결정할 때, 레지스트라는 각 네트워크 사이트와 연결 된 IP 서브넷 목록을 클라이언트에서 제공 하는 서브넷과 정확히 일치 하도록 비교 합니다. 이러한 이유로, 서버에서 네트워크를 구성 하는 동안 입력 된 서브넷이 가상 서브넷 대신 실제 서브넷이 되는 것이 중요 합니다. (통화 허용 제어를 배포 하지만 미디어 바이패스는 아닌 경우 가상 서브넷을 구성한 경우에도 통화 허용 제어가 올바르게 작동 합니다.)<BR>예를 들어 Lync 클라이언트가 IP 주소 서브넷이 255.255.255.0 인 컴퓨터에 로그인 하면 서브넷 172.29.81.0와 연결 된 우회 ID를 요청 하 게 됩니다. 172.29.81.57. 서브넷이 172.29.0.0/16으로 정의 된 경우에는 클라이언트가 가상 서브넷에 속해 있지만, 레지스트라는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에이에 대 한 일치가 고려 되지 않습니다. 따라서 관리자는 네트워크 구성 중에 서브넷이 정적으로 또는 동적 호스트 구성 프로토콜 (DHCP)에 따라 프로 비전 되는 Lync 클라이언트에서 제공 하는 대로 서브넷을 정확 하 게 입력 하는 것이 중요 합니다.



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>네트워크 사이트와 서브넷 연결

엔터프라이즈 네트워크의 모든 서브넷은 네트워크 사이트와 연결 되어야 하며 (즉, 모든 서브넷은 지리적 위치와 연결 되어야 합니다.) 이러한 서브넷 연결을 통해 고급 엔터프라이즈 음성 기능을 통해 끝점을 지리적으로 찾을 수 있습니다. 예를 들어 끝점을 찾으면 CAC는 네트워크 사이트와 주고 받는 실시간 오디오 및 비디오 데이터의 흐름을 조정할 수 있습니다.

서브넷을 네트워크 사이트와 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸을 사용할 수 있습니다. 지침은 배포 설명서의 [Lync server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 또는 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 서비스 계획](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013의 응급 서비스 계획(E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

