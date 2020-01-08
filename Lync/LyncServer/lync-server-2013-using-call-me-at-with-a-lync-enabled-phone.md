---
title: 'Lync Server 2013: Lync 사용 전화를 사용 하 여 전화 걸기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Lync 사용 전화 및 Lync Server 2013을 사용 하 여 전화 걸기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-08-09_

Lync의 전화 받음 기능을 통해 사용자는 휴대폰, "육지 라인" 또는 PSTN (공개 전환 전화 네트워크)에 연결 된 다른 장치를 사용 하 여 전화 회의의 오디오 부분에 참가할 수 있습니다. Lync를 사용 하 여 모임에 참가 하려고 하면 일반적으로 **모임 오디오 참가** 대화 상자가 표시 됩니다.

![Lync를 사용 하 여 모임 오디오 창 스크린샷 참가](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "lync를 사용 하 여 모임 오디오 창 스크린샷 참가")

**전화**를 받을 항목을 선택한 경우 드롭다운 목록에서 전화 번호를 선택할 수 있습니다. Lync Server 2013에서 선택한 번호로 전화를 걸고 해당 휴대폰을 사용 하 여 회의의 오디오 부분에 참가할 수 있습니다.

드롭다운 목록은 **Lync – 옵션** 대화 상자의 **전화 탭에서** 입력 한 전화번호 (휴대폰, 집 전화 번호 또는 기타 전화기의 경우)로 채워집니다.

![Lync 전화 설정 옵션 스크린샷](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "lync 전화 설정 옵션 스크린샷")

**휴대폰** 탭에서 전화 번호를 입력 하지 않은 경우에는 드롭다운 상자에서 사용할 수 있는 번호가 없습니다. 하지만 언제 든 지 **새 번호** 를 클릭 하 고 원하는 전화 번호로 Lync 서버에서 전화를 걸 수 있습니다.

![Lync 참가 모임 음성 통화 창 스크린샷](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "lync 참가 모임 오디오 음성 통화 창 스크린샷")

전화 받음 기능을 사용 하는 경우에는 Lync Server에서 PSTN 전화 번호로 전화를 걸고 있는 것으로 제공 하는 것이 매우 잘 작동 합니다. 그러나 lync를 사용 하는 종점 (예: 회의실의 전화기)에서 사용자에 게 전화를 거는 경우에는 최적화 되지 않은 환경으로 실행할 수 있습니다. 다음은이 문제를 해결 하는 두 가지 방법 뿐 아니라 실행할 수 있는 문제입니다.

시작 하기 위해 Lync 사용 전화 번호를 사용 하 여 전화 받기 기능을 제공 하면 다음과 같은 현상이 발생 합니다. : 진구 Myer는 lync server에서 1-206-555-1219 (Lync Server 사용 전화 번호)를 호출 하 여 모임에 참가 하려고 하는 것으로 가정 합니다. : 진구는 처음에 모임에 연결 되지만 몇 초 후에도 Lync에서 메시지 **호출이 완료 되지 않았거나 종료**된 것으로 표시 되며 모임에서: 진구가 삭제 된 것 처럼 표시 됩니다.

Lync 통화 전화 회의 ![창]스크린샷 화상(images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "통화 회의 창") 스크린샷

그러나 Lync 대화 창에는 차이가 있습니다. : 진구 Myer는 **참가자** 제목 아래에 나열 된 유일한 이름입니다. 그러나 창의 제목 표시줄을 보면 회의에 총 4 명의 참가자가 포함 된 것을 확인할 수 있습니다.

마찬가지로 다른 회의 참가자의 대화 창을: 진구 Myer에는 표시 되지 않습니다.

![Lync 참가자 목록 창 스크린샷](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "lync 참가자 목록 창 스크린샷")

이번에도: 진구 Myer는 Lync 사용 전화를 사용 하 여 통화의 오디오 부분에 참여할 수 있습니다. 전화 번호 기능으로 실제로 작업을 수행 했지만 사용자 환경이 최적이 아닙니다.

이 문제는 두 가지 이상의 방법으로 해결할 수 있습니다. 이미이 방법으로 회의에 참가 한 경우 (예:: 진구 Myer)가 발생 한 경우 일반적으로 다른 모달을 사용 하 여 문제를 해결할 수 있습니다. 예를 들어 인스턴트 메시지를 보내는 경우 대화 창에는 자신을 포함 하 여 모든 컨퍼런스 참가자가 표시 됩니다.

![Lync 대화 및 참가자 목록 스크린샷](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "lync 대화 및 참가자 목록 스크린샷")

이 시점에서 예상 되는 방식으로 모임에 참가할 수 있어야 합니다.

또는 모임에 참가 하는 방식을 변경 하 여이 문제를 완전히 방지할 수 있습니다. Lync server에서 Lync Server를 사용 하는 전화기를 호출 해야 하는 경우에는 오디오 연결 없이 모임에 참가 하는 것으로 시작 해야 합니다. 이렇게 하려면 모임 오디오 참가 대화 상자가 표시 되 면 오디오 연결 안 함을 선택 합니다.

![Lync가 모임 오디오 창 스크린샷에 참가 하지 않음](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "lync 모임 오디오 화면 스크린샷 참가 안 함")

모임에 연결한 후에는 이제 Lync Server 사용 가능 전화기를 "초대" 하 여 모임에 참가할 수 있습니다. 이렇게 하려면 사람 아이콘 위에 마우스를 놓은 다음 **추가 사용자 초대**를 클릭 합니다.

![Lync 초대 추가 참가자 창 스크린샷](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 초대 추가 참가자 창 스크린샷")

그러면 **IM 보내기** 대화 상자가 표시 됩니다. 대화 상자 제목을 무시 하 고 (실제로 인스턴트 메시지를 전송 하지 않는 경우) Lync 사용 전화의 전화 번호를 입력 하세요.

![Im 보내기 대화 상자 스크린샷](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "메신저 대화 상자 스크린샷 보내기")

**확인**을 클릭 하면 Lync Server가 대화 상자에 입력 한 번호로 전화를 겁니다. 연결이 이루어지면 Lync를 사용 하는 휴대폰을 통해 전체 오디오 기능을 사용할 수 있으며, 전체 컨퍼런스 명단을 보고 상호 작용할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

