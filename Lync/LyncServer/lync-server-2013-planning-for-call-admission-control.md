---
title: 'Lync Server 2013: 통화 허용 제어 계획'
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
ms.openlocfilehash: a7c101ab49d16b01dd35d4fc498f002747cd31cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497815"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

전화 통신, 비디오, 응용 프로그램 공유 등과 같은 IP 기반 UC(통합 통신) 응용 프로그램에서 사용 가능한 엔터프라이즈 네트워크 대역폭은 일반적으로 LAN 환경에서는 제한 요소로 간주되지 않지만 사이트, 네트워크 대역폭이 교차되는 WAL 링크에서는 제한될 수 있습니다. 네트워크 트래픽량이 WAN 링크를 초과 구독할 경우 이러한 정체를 해결하기 위해 큐, 버퍼링 및 패킷 삭제 등과 같은 현재 메커니즘이 사용됩니다. 추가 트래픽은 일반적으로 네트워크 정체가 해결되거나 필요한 경우 트래픽이 삭제될 때까지 지연됩니다. 이러한 상황에서 일반적인 데이터 트래픽에 대해서는 수신 클라이언트가 복구할 수 있습니다. 하지만 통합 통신과 같은 실시간 트래픽의 경우 통합 통신이 대기 시간 및 패킷 손실 모두에 민감하므로 이 방법으로 네트워크 정체를 해결할 수 없으며, WAN의 정체로 인해 사용자의 QoE(체감 품질)가 저하될 수 있습니다. 정체된 상황에서의 실시간 트래픽에 대해 품질이 낮은 연결을 제공하는 것보다 통화를 지연시키는 것이 더 나은 선택입니다.

CAC(통화 허용 제어)는 허용 가능한 품질의 실시간 세션을 설정하기 위해 충분한 네트워크 대역폭이 있는지 여부를 확인합니다. Lync Server 2013에서는 CAC가 오디오 및 비디오에 대 한 실시간 트래픽만 제어 하지만 데이터 트래픽에는 영향을 주지 않습니다. 기본 WAN 경로에 필요한 대역폭이 없는 경우 CAC는 인터넷 경로나 PSTN(공중 전화망)을 통해 통화를 라우팅할 수 있습니다. CAC는 Lync Server 에서만 사용할 수 있습니다.

이 섹션에서는 통화 허용 제어 기능과 CAC를 계획하는 방법에 대해서 설명합니다.

<div>


> [!NOTE]  
> Lync Server에는 3 가지 고급 Enterprise Voice 기능인 CAC (통화 허용 제어), 응급 서비스 (E9-1-1) 및 미디어 바이패스가 있습니다. 이러한 세 가지 기능에 공통적으로 제공 되는 계획 정보에 대 한 개요는 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013의 Advanced Enterprise Voice 기능에 대 한 네트워크 설정을</A>참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)

  - [Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [예: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013의 CAC에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013의 통화 허용 제어에 대 한 모범 사례](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013의 통화 허용 제어에 대 한 배포 검사 목록](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

