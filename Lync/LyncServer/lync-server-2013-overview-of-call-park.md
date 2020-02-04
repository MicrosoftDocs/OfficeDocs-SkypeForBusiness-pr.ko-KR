---
title: 'Lync Server 2013: 통화 공원 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 공원 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

Lync Server 2013 통화 공원 응용 프로그램을 통해 엔터프라이즈 음성 사용자는 다음 중 하나를 실행할 수 있습니다.

  - 통화를 대기 상태로 설정한 다음 같은 휴대폰 또는 다른 전화기에서 통화를 검색 합니다.

  - 통화를 대기 또는 일반 영역 (예: 영업부 또는 공통 지역 전화국에 거주 하는 영업 부서나 웨어하우스로)으로 전송할 수 있습니다.

  - 통화를 대기 상태로 전환 하 고 다른 통화를 위해 원래 응답 전화를 무료로 유지 하세요.

사용자가 통화를 전환 하는 경우 Lync Server는 전화를 걸거나 시간 초과 될 때까지 통화를 대기 하는 *회전*이라고 하는 임시 번호로 통화를 전송 합니다. Lync Server는 통화를 파킹 한 사용자에 게 궤도를 보냅니다. 파킹 된 통화를 검색 하기 위해 사용자는 궤도 번호로 전화를 걸거나 대화 창에서 궤도 링크 또는 단추를 클릭할 수 있습니다.

통화를 파킹 한 사용자는 다른 사용자에 게 궤도 번호를 전달 하는 메신저 대화 (인스턴트 메시징) 또는 페이징 시스템 등의 외부 메커니즘을 사용 하 여 전화를 받도록 다른 사람에 게 알릴 수 있습니다. 통화를 파킹 한 사용자는 통화가 검색 될 때 알림을 받도록 대화 창을 열어 둘 수 있습니다.

궤도 범위는 전역적으로 고유 하므로 라우팅이 적절 하 게 구성 된 경우 Lync Server 사이트 또는 PBX 휴대폰에서 전화를 검색할 수 있습니다. 구성 가능한 시간 내에 호출이 검색 되지 않는 경우에는 통화가 대기 하는 사용자에 게 다시 전화가 울립니다. 해당 사용자가 ringback에 응답 하지 않는 경우 통화는 교환원 (예: 구성 된 경우)과 같은 대체 대상으로 전송 됩니다. 통화가 1 ~ 10 번 전송 되기 전에 다시 울릴 횟수를 구성할 수 있습니다. 통화에 대 한 답이 없는 경우 통화의 연결이 끊어집니다. 통화가 검색 되거나 연결이 끊어지면 궤도가 해제 됩니다.

통화 공원를 배포 하는 경우 파킹 통화에 대 한 내선 번호 범위를 예약 해야 합니다. 이러한 확장은 사용자 또는 휴대폰을 할당 하지 않은 가상 확장 이어야 합니다. 그런 다음 내선 번호 범위를 사용 하 여 통화 공원 표를 구성 하 고 각 범위를 처리 하는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정 합니다. 각 프런트 엔드 풀에는 풀에서 파킹 된 통화를 관리 하는 데 사용 되는 해당 백 엔드 서버에 대 한 통화 공원 테이블이 있습니다. 궤도 범위 목록은 중앙 관리 저장소에 저장 되며 대상 풀로 orbits를 라우팅하는 데 사용 됩니다. 통화 공원 응용 프로그램을 배포 하 고 구성 하는 각 Lync Server 풀은 하나 이상의 궤도 범위를 가질 수 있습니다. 궤도 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.

또한 시간이 초과 되는 경우 통화가 리디렉션되는 위치, 휴대 중에는 전화의 상대방이 음악을 듣게 되는지 등 다른 통화 대기 설정을 구성할 수 있습니다. 통화 대기 중에 음악 파일을 재생 하도록 지정할 수도 있습니다.

<div>


> [!NOTE]  
> 통화 공원에 대 한 사용자 지정 음악 저장 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다. 통화 공원에 대해 업로드 한 사용자 지정 음악 보관 파일의 별도의 백업 복사본을 항상 보관 하세요.



</div>

통화 공원 응용 프로그램은 엔터프라이즈 음성의 구성 요소입니다. 엔터프라이즈 음성을 배포 하는 경우 통화 공원 응용 프로그램이 자동으로 설치 되 고 활성화 됩니다. 통화 대기를 사용 하기 전에 엔터프라이즈 음성 관리자가 음성 정책을 통해 사용자에 게이를 구성 하 고 사용할 수 있도록 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

