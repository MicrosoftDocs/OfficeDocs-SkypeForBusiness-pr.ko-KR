---
title: 'Lync Server 2013: 음성 번호 정규화 및 라우팅 확인'
description: 'Lync Server 2013: 음성 번호 정규화 및 라우팅의 유효성을 검사 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547144"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Lync Server 2013에서 음성 번호 정규화 및 라우팅 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-19_

올바른 번호 정규화와 라우팅은 기능적인 엔터프라이즈 음성 환경에서 매우 중요 합니다. 특히 PBX (private branch exchange)에서 독립 실행형 Lync Server 환경으로 마이그레이션하는 동안에는 기존의 모든 전화 걸기 규칙을 표시 하 고 문서화 하 고 적절 한 정규화 규칙, 음성 정책, 전화 사용 및 경로를 만드는 것이 좋습니다.

마이그레이션 중에는 번호 정규화와 라우팅을 확인 하는 것이 중요 하지만 시스템을 정상적으로 작동 하는 경우에도 가능 합니다.

Lync server 전역 설정에 게시 된 현재 정규화 규칙 집합에 대해 견고한 테스트 사례 집합을 개발 하는 것부터 시작 하 여 매일이 유효성 검사를 수행 하는 것이 좋습니다. 이러한 테스트 사례는 매일 실행 하 여 다이얼 플랜에 적용 되거나 커밋된 원치 않는 변경을 강조 표시 해야 합니다.

Lync Server 제어판은 또한 음성 라우팅 및 Enterprise Voice number 정규화 규칙, 다이얼 플랜, 음성 정책 및 경로 변경에 대 한 구성 정보를 시각화, 테스트, 변경, 보관 및 공유 하는 데 도움이 됩니다. 다음과 같은 추가 기능을 사용할 수 있습니다.

  - 시스템 간에 음성 라우팅 데이터 내보내기 및 가져오기 또는 백업

  - 구성 변경 내용을 라이브 시스템에 업로드 하기 전에 테스트

  - 구성 테스트 사례를 만들고 실행 하 여 배포 된 시스템에 변경 내용을 커밋하기 전에 라우팅 데이터의 유용성을 보장 하는 데 도움을 주는 작업입니다.

  - 필요한 정규식을 작성 하지 않고 숫자 정규화 규칙, 위치 프로필, 음성 정책 및 라우팅 데이터를 만들고 변경 합니다.

  - Lync Server Phone Edition과의 호환성을 위해 위치 프로필을 분석 합니다.

  - 음성 라우팅 테스트에 대 한 자세한 내용은 [Lync Server 2013의 테스트 음성 라우팅](lync-server-2013-test-voice-routing.md) 에서 찾을 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

