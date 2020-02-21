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
ms.openlocfilehash: c96bae1a917efa52dfc25639d7e46fc1b7e2142e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013의 환경 테스트 관련 문제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

모범 사례 분석기는 Lync Server 2013 환경이 지원 되는 구성 인지 확인할 수 있는 방법을 제공 합니다. 모범 사례 분석기는 Active Directory 도메인 서비스 검사의 일부로서 다음을 수행합니다.

  - Active Directory 도메인 서비스 포리스트 및 스키마 준비 상태를 확인합니다.

  - 배포에서 Active Directory 도메인 서비스 사이트 및 도메인 수를 식별합니다.

  - 포리스트 및 도메인 수준을 확인합니다.

  - 도메인 컨트롤러 버전을 확인합니다.

  - 도메인, 구성 및 스키마 명명 컨텍스트를 식별합니다.

  - 활성화된 사용자 수를 식별합니다.

  - 전역 Active Directory 도메인 서비스 설정이 저장된 위치를 확인합니다.

  - Lync Server에 대 한 Scp (서비스 연결 지점)를 확인 합니다.

  - 데이터베이스 버전을 식별합니다.

<div>

## <a name="resolving-issues-with-the-environment"></a>환경 관련 문제 해결

환경 테스트 시 환경 관련 문제가 발견된 경우 대개 Active Directory 구성이나 특정 서버에서 실행 중인 소프트웨어 수준과 관련된 문제가 원인입니다. 예를 들어 모범 사례 분석기를 통해 환경에서 Windows Server 2000을 실행 중인 도메인 컨트롤러가 식별되는 경우 이로 인해 경고가 발생하며 이러한 도메인 컨트롤러를 지원되는 Windows Server로 업그레이드해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

