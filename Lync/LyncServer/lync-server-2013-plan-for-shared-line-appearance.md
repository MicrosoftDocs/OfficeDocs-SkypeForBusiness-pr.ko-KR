---
title: 'Lync Server 2013: 공유 선 모양 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb4f8ad407950f8d3180d030ede03a1e93cf0b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Lync Server 2013의 공유 선 모양 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-03-21_

Lync Server 2013, 누적 업데이트 4 월 2016에서 SLA (Shared Line 모양새)를 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오.

공유 선 모양은 Lync Server 2013, 누적 업데이트의 기능으로, 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 데에는 4 월 2016입니다. SLA는 여러 통화에 응답 하는 여러 회선이 있는 공유 번호로 enterprise voice 사용 Lync 사용자를 구성할 수 있습니다. 전화가 공유 번호로 실제로 수신 되지 않고 대신 공유 번호에 대 한 대리인 역할을 하는 사용자에 게 전달 됩니다. 대리인 중 하나는 통화를 선택한 사람에 대 한 알림을 받게 되는 동안 대리인에 게 전화를 걸 수 있으며 그 결과, 결과적으로 사용 중인 회선이 발생 하 게 됩니다. 줄 수와 대리인을 모두 SLA의 공유 번호로 구성할 수 있습니다. 또한 BusyOption (모든 회선이 사용이 진행 중일 때 발생 하는 상황)과 MissedCallOption (대리인이 아무 것도 선택 하지 않은 경우)와 같은 고급 옵션을 공유 번호로 구성할 수도 있습니다.

SLA는 다음 전화 장치 에서만 지원 됩니다 (컴퓨터, 휴대폰 또는 기타 장치의 Lync 클라이언트에는 지원 되지 않음).

  - Polycom VVX300 (펌웨어 업데이트 5.4.1 포함)

  - Polycom VVX400 (펌웨어 업데이트 5.4.1 포함)

  - Polycom VVX500 (펌웨어 업데이트 5.4.1 포함)

  - Polycom VVX600 (펌웨어 업데이트 5.4.1 포함)

SLA는 Lync Server 2013, 누적 업데이트 4 월 2016의 새로운 기능입니다.

SLA를 배포 하는 방법에 대 한 자세한 내용은 [Deploy Shared Line 모양새 In Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md)을 참조 하십시오.

<div>

## <a name="feature-list"></a>기능 목록

SLA 그룹을 설정 하면 다음이 가능해 집니다.

  - 그룹의 모든 대리인은 동일한 공유 번호에 대 한 인바운드 호출에 응답할 수 있습니다. 통화는 PSTN 기반 이거나 SIP 기반 일 수 있습니다.

  - 대리인은 통화를 대기 하 고 선택할 수 있습니다.

  - 대리인은 SLA 그룹 외부의 번호로 전화를 이동할 수 있습니다.

  - 대리인은 현재 공유 번호에 대 한 통화 수를 확인 하 고 각 통화의 상태를 볼 수 있습니다.

  - 공유 번호에 대 한 최대 동시 통화 수를 구성할 수 있습니다. 이 최대 개수에 도달한 후에 추가 통화를 처리 하는 방법을 설정할 수도 있습니다. 불필요 한 전화가 통화 중으로 거부 되거나 대체 번호로 전달 되거나 음성 메일로 전달 될 수 있습니다.

  - 부재 중 통화 (특정 시간 후에 선택 하지 않은 통화)를 처리할 방법을 구성할 수 있습니다. 그룹 id에 대해 음성 메일을 사용 하도록 설정 하면 부재 중 전화가 자동으로 음성 메일로 이동 합니다. 그룹 id (공유 번호)에 대해 음성 메일을 사용 하도록 설정 하지 않은 경우 부재 중 전화 통화를 거부 하거나, 다른 번호로 전달 하거나, 연결을 끊을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

