---
title: 'Lync Server 2013: 환경 테스트 문제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013의 환경 테스트 문제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

모범 사례 분석기는 Lync Server 2013 환경이 지원 되는 구성 인지 확인할 수 있는 방법을 제공 합니다. Active Directory 도메인 서비스 검사의 일부로 모범 사례 분석기는 다음을 수행 합니다.

  - Active Directory 도메인 서비스 포리스트와 스키마 준비를 확인 합니다.

  - 배포의 Active Directory 도메인 서비스 사이트 및 도메인 수를 식별 합니다.

  - 포리스트와 도메인 수준을 검사 합니다.

  - 도메인 컨트롤러 버전을 확인 합니다.

  - 도메인, 구성 및 스키마 명명 컨텍스트를 식별 합니다.

  - 사용 하도록 설정 된 사용자의 수를 식별 합니다.

  - 전역 Active Directory 도메인 서비스 설정이 저장 되는 위치를 확인 합니다.

  - Lync Server에 대 한 Scp (서비스 연결 지점)를 확인 합니다.

  - 데이터베이스 버전을 식별 합니다.

<div>

## <a name="resolving-issues-with-the-environment"></a>환경의 문제 해결

환경 테스트에서 환경에 문제가 발견 되는 경우 이러한 문제는 Active Directory 구성 문제 또는 특정 서버에서 실행 되는 소프트웨어 수준 때문에 발생할 수 있습니다. 예를 들어 모범 사례 분석기가 Windows Server 2000를 실행 하는 환경에서 도메인 컨트롤러를 식별 하는 경우 경고를 표시 하 고 해당 도메인 컨트롤러를 지원 되는 Windows Server 버전으로 업그레이드 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

