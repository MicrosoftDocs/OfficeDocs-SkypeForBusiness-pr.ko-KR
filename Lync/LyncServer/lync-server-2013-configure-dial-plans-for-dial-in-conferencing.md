---
title: 'Lync Server 2013: 전화 접속 회의에 대한 다이얼 플랜 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-25_

전화 접속 회의를 배포 하는 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 또는 그 이상의 다이얼 플랜을 만들거나 수정 해야 합니다. 각 다이얼 플랜에서 하나 이상의 정규화 규칙에서 휴대폰 내선 번호를 E 164 형식의 완전 한 전화 번호로 변환 하도록 합니다. 전화 접속 회의 사용자는 개인 id 번호 (PIN)와 전화 번호를 입력 하 여 인증 된 엔터프라이즈 사용자로 회의에 참가 합니다. 내선 번호를 완전 한 전화 번호로 변환 하 여 사용자가 전화 내선 번호만 입력 하는 경우 인증 받을 수 있는 정규화 규칙이 필요 합니다.

전화 접속 회의에 대 한 다이얼 플랜을 설정 하려면 다음을 수행 합니다.

  - 엔터프라이즈 음성을 배포할지 여부에 관계 없이 전화 접속 회의 영역을 추가 하도록 전역 다이얼 플랜을 수정 하 고 정규화 규칙이 전화 접속 액세스 번호를 정확 하 게 변환 하는지 확인 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.

  - 엔터프라이즈 음성을 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다. 전화 접속 회의 지역을 포함 해야 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하세요.

  - 엔터프라이즈 음성을 배포한 경우 전화 접속 액세스 번호에 대 한 영역을 포함 하 고 적절 한 정규화 규칙을 사용 하도록 필요한 경우 Enterprise Voice dial 계획을 수정 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요. 전화 접속 액세스 번호에만 사용 되는 전용 다이얼 플랜을 만들 수도 있습니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하세요.

계획 영역에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 전화 접속 회의 요구 사항을](lync-server-2013-dial-in-conferencing-requirements.md) 참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 다이얼 플랜 정보 보기](lync-server-2013-view-dial-plan-information.md)

  - [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)

  - [Lync Server 2013에서 다이얼 플랜 수정](lync-server-2013-modify-a-dial-plan.md)

  - [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

