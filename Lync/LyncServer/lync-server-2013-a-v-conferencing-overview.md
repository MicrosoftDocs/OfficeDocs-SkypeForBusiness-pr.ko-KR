---
title: Lync Server 2013 A/V 회의 개요
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Lync Server 2013의 A/V 회의 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-13_

A/V 회의는 사용자 간 실시간 오디오 및 비디오 통신을 가능 하 게 합니다. 회의를 배포 하는 경우 웹 회의 및 A/V 회의를 사용 하도록 설정 하 고 사용 하거나 웹 회의만을 선택할 수 있습니다.

A/V 회의를 계획 하려면 조직에 필요한 회의 미디어 유형에 필요한 네트워크 대역폭을 이해 해야 합니다. 여기에는 오디오, 비디오, 파노라마 비디오가 포함 될 수 있습니다.

A/V 회의에 대 한 사용자를 활성화 하기 전에 네트워크가 결과 로드를 처리할 수 있는지 확인 합니다. 네트워크 대역폭이 충분 하지 않으면 사용자 환경이 심각 하 게 저하 될 수 있습니다. CAC (호출 허용 제어)를 사용 하 여 A/V 회의에 사용 되는 네트워크 대역폭을 관리할 수 있습니다. 이는 중앙 사이트와 지점 간 제한 된 대역폭 연결과 같은 제한 네트워크에 중요 합니다. 자세한 내용은 [Lync Server 2013에서 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)를 참조 하세요. 미디어 대역폭 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항을](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)참조 하세요.

네트워크에 오디오 회의를 배포 하는 경우 헤드셋과 같은 오디오 장치가 있어야 오디오 회의에 참가할 수 있습니다. 비디오 회의를 배포 하는 경우 사용자 용 웹캠 등의 비디오 장치를 배포 해야 합니다. 최적의 사용자 환경을 위해 Microsoft에서 모든 디바이스 유형에 대해 인증 하는 UC (통합 통신) 장치를 사용 하는 것이 좋습니다. UC 인증 장치에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)"Lync 용 전화 및 장치"를 참조 하세요. 오디오 또는 비디오 장치, 장치 배포, 사용자 교육 등을 위해 고려해 야 할 중요 한 단계가 있습니다.

다음 섹션에서는 대역폭 관리 및 적절 한 클라이언트 선택에 대 한 정보를 포함 하 여 오디오 및 비디오 회의 기능에 대해 설명 합니다.

<div>

## <a name="audio-conferencing-features"></a>오디오 회의 기능

Lync Server 2013는 다음을 포함 하 여 사용자에 대 한 오디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.

  - **청중 음소거**   발표자는이 설정을 사용 하 여 전화 회의의 모든 오디오 참가자를 음소거 하 고 발표자 이외의 사용자는 음소거를 해제할 수 없는 상태에 회의를 설정할 수 있습니다.

  - **회의 시작/종료 알림**   전화 접속 회의를 사용 하도록 설정한 경우 발표자는이 설정을 사용 하 여 알림 기능을 설정 하거나 해제 하 여 회의가 진행 되는 동안 혼란을 최소화할 수 있습니다.

  - ****   사용 권한이 부여 된 발표자 및 참석자에 게 전화를 걸어 사용자를 추가 하면, 회의에 PSTN 번호를 추가 하 고 해당 번호로 전화를 걸 수 있습니다.

</div>

<div>

## <a name="video-conferencing-features"></a>비디오 회의 기능

Lync Server 2013는 다음을 포함 하 여 사용자에 대 한 비디오 회의 환경을 구성 하는 데 사용할 수 있는 몇 가지 기능을 제공 합니다.

  - **갤러리 보기**   두 명 이상이 있는 비디오 회의에서 사용자는 자동으로 회의의 모든 사람을 볼 수 있습니다. 회의에 다섯 명 이상의 참가자가 있는 경우 가장 활발 한 참가자의 비디오가 맨 위쪽 행에 나타나고 다른 참가자를 위한 사진만 표시 됩니다. 단체 비디오는 기본적으로 켜져 있습니다. 단체 비디오의 구성 또는 해제에 대 한 자세한 내용은 [Lync Server 2013에서 비디오 대역폭 구성을](lync-server-2013-configuring-video-bandwidth.md)참조 하세요.

  - **파노라마 비디오**   RoundTable 영상 회의 장치가 회의실에 설치 되어 있는 경우이 기능은 회의실에 대 한 전체 360도 보기를 제공 합니다. 파노라마 비디오 스트립은 RoundTable 장치 에서만 사용할 수 있습니다.

  - **발표자 전용 비디오 모드**   발표자는 발표자의 비디오만 표시 되도록 모임을 구성할 수 있습니다. 이렇게 하면 여러 비디오 스트림을 사용할 수 있으며 다양 한 원본으로 잠길 때 대규모 모임에서 혼란을 방지할 수 있습니다. 이 모드는 RoundTable 디바이스에서 캡처하고 제공 하는 비디오에도 적용 됩니다.

  - **Hd 영상**   사용자는 2-파티 통화와 단체 회의에서 hd 1080p로 해상도를 경험할 수 있습니다.

  - **비디오 스포트라이트**   발표자는 선택한 참가자가 비디오 원본에 있는 비디오만 회의의 다른 참가자에 게 표시 되도록 모임을 구성할 수 있습니다. 이 모드는 파노라마 비디오의 RoundTable 장치에서 캡처한 후 제공 하는 비디오에도 적용 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

