---
title: Lync Server 2013 회의 사용자 모델
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013의 회의 사용자 모델

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

Lync Server 회의 사용자 모델의 중요 한 부분은 모임 크기입니다. 이전 섹션에서 설명한 대로 여러 데이터 요소에서 데이터를 수집한 후에는 다음을 결정 했습니다.

  - 대부분의 모임은 실제로 4 ~ 6 명의 참가자가 포함 된 매우 작은 협업 모임입니다.

  - 모임 중 약 80%는 참가자가 20 명 미만입니다.

  - 99.98%의 모임이 100 명 미만입니다.

회의 사용자 모델에는 모임 크기 외에도 다음과 같은 다양 한 요소가 고려 됩니다.

  - **동시**에 모임에서 예상 되는 사용자 수   

  - **미디어 믹스**   어떤 유형의 미디어를 사용할 수 있으며 모임 중에 사용자가 사용할 것으로 예상 되나요?

  - **사용자 유형은**   사용자가 내부 사용자, 원격 사용자, 페더레이션 사용자 또는 익명 사용자입니다.

  - **모임 램프 시간**   모임의 모든 사용자가 모임에 참가 하는 데 어떤 시간이 걸립니까?

사용자 모델에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하세요.

테스트에 사용할 모임 및 사용자 수를 결정 하려면 다음을 수행 합니다.

  - 조직에 있는 총 사용자 수 (예: 8만 사용자)를 만들고 모임 동시성 비율로 곱하여 (예: 모든 사용자의 5%) 동시에 모임에 예정 된 총 사용자 수를 확인 합니다 (이 예에서는 , 4000 사용자).

  - 총 사용자 수를 Lync Server 2013, 배포의 프런트 엔드 서버 (예: 8 개 서버)로 나누어 각 프런트 엔드 서버에 대 한 예상 모임 참가자 수 (이 예제에서는 프런트 엔드 서버 당 사용자를 500)를 결정 합니다.

  - 프런트 엔드 서버 당 사용자 수를 평균 모임 크기 (예: 4 명의 사용자)로 나누어 프런트 엔드 서버 당 예상 평균 모임 수를 결정 합니다 (이 예에서는 프런트 엔드 서버 당 125 모임).

  - 각 프런트 엔드 서버에서 미디어 당 로드를 얻으려면 미디어 조합을 예상 하 게 됩니다. 예를 들어 모임 중 75%가 오디오 지원 이상의 기능을 요구 하 고 해당 모임의 50%가 응용 프로그램 공유를 요구 하는 경우 평균 47 회의와 188 사용자가 각 프런트 엔드 서버에 응용 프로그램 공유에 대해 동시에 연결 됩니다.

  - 서버 확장성을 보장 하기 위해 다양 한 모임 크기 (공유 풀에서 최대 250 사용자 모델을 기반으로)가 테스트 되었습니다.

</div>

<span> </span>

</div>

</div>

</div>

