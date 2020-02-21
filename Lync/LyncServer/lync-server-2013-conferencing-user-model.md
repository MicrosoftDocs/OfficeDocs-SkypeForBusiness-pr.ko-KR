---
title: Lync Server 2013 회의 사용자 모델
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1049ff2d11d76e78661636972c812cc6c9c731f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013의 회의 사용자 모델

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

Lync Server 회의 사용자 모델의 중요 한 부분은 모임 크기입니다. 이전 섹션에서 설명한 대로 여러 데이터 요소에서 데이터를 수집한 결과, Microsoft에서는 다음을 파악했습니다.

  - 대부분의 모임은 참가자가 평균 4~6명인 소규모의 공동 작업 모임입니다.

  - 약 80%의 모임은 참가자가 20명 미만입니다.

  - 99.98%의 모임은 참가자가 100명 미만입니다.

모임 크기 이외에도 회의 사용자 모델은 다음과 같은 여러 가지 요인을 고려합니다.

  - **동시 회의**   회의에 예상 되는 사용자의 수는 얼마나 됩니까?

  - **미디어 믹스**   사용할 수 있는 미디어 유형 및 모임 사용자가 사용 해야 할 것으로 예상 되는 기능은 무엇입니까?

  - **사용자 유형은**   사용자 내부 사용자, 원격 사용자, 페더레이션 사용자 또는 익명 사용자입니다.

  - **모임 램프 가동 시간**   모든 모임 사용자가 모임에 참가 하는 데 어느 정도의 시간이 걸립니까?

사용자 모델에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.

테스트에 사용할 모임 및 사용자 수를 결정하기 위해 Microsoft에서는 다음을 수행했습니다.

  - 한 조직의 전체 사용자 수(예: 80,000명의 사용자)에 모임 동시 참가 비율(예: 전체 사용자의 5%)을 곱하여 동시에 모임에 참가할 것으로 예상되는 총 사용자 수(이 예에서 4,000명의 사용자)를 파악했습니다.

  - 총 사용자 수를 Lync Server 2013, 배포의 프런트 엔드 서버 (예: 8 개 서버)로 나누어 프런트 엔드 서버당 예상 모임 참가자 수 (이 예에서는 프런트 엔드 서버당 500 사용자)를 확인 합니다.

  - 프런트 엔드 서버 당 사용자 수를 평균 모임 크기 (예: 4 명의 사용자)로 나누면 프런트 엔드 서버당 예상 평균 모임 수 (이 예에서는 프런트 엔드 서버당 125 회의)를 결정할 수 있습니다.

  - 각 프런트 엔드 서버에서 미디어 부하를 확보 하기 위해 미디어 조합이 예상 됩니다. 예를 들어 회의의 75%에 오디오 지원 뿐 아니라 이러한 모임의 50% 이상이 필요한 경우 응용 프로그램 공유가 필요한 경우 평균 47 회의 및 188 사용자가 각 프런트 엔드 서버에 동시에 응용 프로그램 공유를 연결 합니다.

  - 서버 확장성을 보장하도록 공유 풀에 최대 250명의 사용자가 있는 사용자 모델을 기반으로 다양한 모임 크기를 테스트했습니다.

</div>

<span> </span>

</div>

</div>

</div>

