---
title: 'Lync Server 2013: 전화 접속 회의에 대 한 다이얼 플랜을 구성 합니다.'
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
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

전화 접속 회의를 배포할 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만들거나 수정해야 합니다. 각 다이얼 플랜의 하나 이상의 정규화 규칙이 전화 내선 번호를 E.164 형식의 완전한 전화 번호로 변환하는지 확인합니다. 전화 접속 회의의 사용자는 PIN(개인 식별 번호) 및 전화 번호를 입력하여 인증된 엔터프라이즈 사용자로 전화 회의에 참가합니다. 사용자들이 전화 내선 번호를 입력할 때 사용자를 인증할 수 있도록 내선 번호를 완전한 전화 번호로 변환하는 정규화 규칙이 필요합니다.

전화 접속 회의에 대해 다이얼 플랜을 설정하려면 다음을 수행합니다.

  - Enterprise Voice를 배포 하는지 여부에 관계 없이 전화 접속 회의 지역을 추가 하 고 정규화 규칙을 통해 전화 접속 액세스 번호를 정확 하 게 변환 하도록 전역 다이얼 플랜을 수정 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오.

  - Enterprise Voice를 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다. 이 경우 전화 접속 회의 지역을 포함해야 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하십시오.

  - Enterprise Voice를 배포한 경우 국가를 포함 하 고 전화 접속 액세스 번호에 대해 적절 한 정규화 규칙을 사용 하려면 Enterprise Voice 다이얼 요금제를 수정 합니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오. 전화 접속 액세스 번호에만 사용되는 전용 다이얼 플랜을 만들 수도 있습니다. 자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하십시오.

영역 계획에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 전화 접속 회의 요구 사항](lync-server-2013-dial-in-conferencing-requirements.md) 를 참조 하십시오.

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

