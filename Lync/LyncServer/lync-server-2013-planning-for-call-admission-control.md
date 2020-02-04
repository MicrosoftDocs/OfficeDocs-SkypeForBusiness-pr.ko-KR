---
title: 'Lync Server 2013: 통화 허용 제어 서비스 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 서비스 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

전화 통신, 비디오, 응용 프로그램 공유 등 IP 기반 통합 커뮤니케이션 (UC) 응용 프로그램의 경우 엔터프라이즈 네트워크의 사용 가능한 대역폭이 일반적으로 LAN 환경 내에서 제한 요인이 아닌 것으로 간주 되지 않습니다. 그러나 사이트를 상호 연결 하는 WAN 링크에서는 네트워크 대역폭이 제한 될 수 있습니다. 네트워크 트래픽이 WAN 링크를 과잉 influx 경우, 대기열, 버퍼링, 패킷 삭제 등의 현재 메커니즘이 정체를 해결 하는 데 사용 됩니다. 추가 소통량은 일반적으로 네트워크 정체가 부드럽게 되거나 필요한 경우 트래픽이 손실 될 때까지 지연 됩니다. 이러한 경우에는 일반 데이터 트래픽의 경우 받는 클라이언트가 복구할 수 있습니다. 통합 통신 트래픽이 대기 시간과 패킷 손실에 모두 영향을 주므로 이러한 방식으로 네트워크 혼잡을 확인할 수 없는 실시간 트래픽입니다. WAN의 정체 때문에 사용자에 게 체감 품질 (환경 품질)이 저하 될 수 있습니다. 혼잡 한 상태의 실시간 트래픽에는 낮은 품질로 연결을 제공 하는 것 보다 호출을 거부 하는 것이 좋습니다.

CAC (호출 허용 제어)는 적절 한 품질로 실시간 세션을 설정할 수 있는 충분 한 네트워크 대역폭이 있는지 여부를 결정 합니다. Lync Server 2013에서 CAC는 오디오 및 비디오에 대 한 실시간 트래픽만 제어 하지만 데이터 트래픽에는 영향을 주지 않습니다. 기본 WAN 경로에 필요한 대역폭이 없는 경우 CAC는 인터넷 경로 또는 PSTN (공개 교환 전화 네트워크)을 통해 통화를 라우팅하도록 할 수 있습니다. CAC는 Lync Server 에서만 사용할 수 있습니다.

이 섹션에서는 전화 허용 제어 기능에 대해 설명 하 고 CAC를 계획 하는 방법을 설명 합니다.

<div>


> [!NOTE]  
> Lync Server에는 세 가지 고급 엔터프라이즈 음성 기능 (call 허용 제어 (CAC), 응급 서비스 (E9-1-1), 미디어 바이패스)이 있습니다. 이러한 세 가지 기능에 모두 공통적으로 제공 되는 계획 정보에 대 한 개요는 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정을</A>참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)

  - [Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [예: Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013의 CAC의 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013의 통화 허용 제어 서비스 모범 사례](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013의 통화 허용 제어 서비스에 대한 배포 검사 목록](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

