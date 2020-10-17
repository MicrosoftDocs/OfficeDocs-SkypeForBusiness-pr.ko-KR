---
title: 'Lync Server 2013: 데이터 수집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516575"
---
# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013의 데이터 수집

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

Microsoft Lync Server 2013 통신 소프트웨어에서는 기존 및 제안 된 IP 주소와에 지 서버 Fqdn (정규화 된 도메인 이름)을 문서화 하지 않고 Microsoft Lync Server 2013, 계획 도구를 실행할 수 있지만 구성 오류가 발생 하지 않고이 작업을 수행 하는 것이 훨씬 더 어렵습니다. 예를 들어 일정 기간 동안 동시 사용이 필요한 경우에는 Lync Server 2013에 지 배포에 대 한 기존에 지 배포에서 Fqdn을 다시 사용 하는 것이 일반적인 실수입니다. 기존의 제안된 IP 주소 및 FQDN을 스프레드시트, 테이블 또는 기타 시각적 양식에 작성해두면 설치하는 동안 이러한 설치 문제를 방지할 수 있습니다.

<div>


> [!WARNING]  
> 계획 도구의 이전 버전을 사용한 적이 있는 경우이 도구를 사용 하 여 토폴로지를 만들고 토폴로지 작성기에서 사용 하 여 토폴로지를 게시 하기 위해 내보낸 토폴로지 문서를 내보내야 할 수 있습니다. 토폴로지를 내보내는 기능은 계획 도구에서 제거 되었습니다. 이전 버전의 계획 도구를 사용 하 여 Lync Server 2013에 대 한 토폴로지 문서를 만드는 것은 권장 되지 않으며 예기치 않은 결과가 생성 됩니다.



</div>

따라서 권장 방법은에 지 토폴로지에 해당 하는 다음 데이터 모음 템플릿을 사용 하 여 계획 도구에 입력 해야 하는 다양 한 FQDN 및 IP 주소를 수집 하는 것입니다. 현재 제안된 구성을 기록해 두면 프로덕션 환경에 대한 적합한 컨텍스트에 값을 입력할 수 있습니다. 그리고 단순 URL, 파일 공유, 부하 분산 등의 기능과 동시 사용성을 구성하는 방법을 생각하게 됩니다.

Microsoft Lync Server 2013를 배포 하려면 개별 구성 요소에 대 한 상호 작용과 의존도를 이해 해야 합니다. 기존 네트워크 및 서버 인프라에서 데이터를 수집 하 고 이러한 섹션에서 계획 지침을 적용 하면 Lync Server 2013에 지 서버 구성 요소를 인프라에 통합할 수 있습니다.

[Lync Server 2013에서 토폴로지를 선택](lync-server-2013-choosing-a-topology.md)하는 데 도입 되었으며, 두 가지 유형의 주요 아키텍처가 있는데, 여기서는 총 5 개 배포 시나리오를 사용할 수 있습니다. 이러한 시나리오 중 하나가 데이터 수집을 위한 시작점이 될 것입니다. IP 주소, 서버 이름 및 도메인 이름은 전체 계획 솔루션에 필요한 세부 정보를 제공하는 해당 인증서, 방화벽 및 DNS 다이어그램과 일치함을 보여주는 예입니다. 다이어그램과 필요한 인증서, DNS 및 방화벽 값 입력은 배포를 계획하는 팀이 아닌 다른 팀이 인증 기관, 방화벽 구성 및 DNS 관리를 관리하는 교차 팀 통신에서 특히 중요합니다. 이 다이어그램은 교차 팀 공동 작업의 이러한 요구 사항을 전달하는 데 사용할 수 있는 필수 구성 요소에 대한 정보를 제공합니다.

제공된 다이어그램은 일반용이지만, 이러한 다이어그램을 사용하면 네트워킹, 방화벽, 인증서 작성 및 관리, 서버 배포 및 서버 관리가 다양한 그룹에 의해 처리되는 교차 팀 시나리오에서 요구 사항을 전달하는데 반드시 필요한 모든 관련 데이터를 수집할 수 있습니다. Lync Server의 배포를 진행 하는 경우 네트워크, 방화벽, 포트 및 프로토콜, 인증서 및 서버를 구성 하는 데 필요한 세부 정보를 매우 유용 하 게 사용할 수 있습니다.

**에 지 서버 및에 지 풀**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**역방향 프록시**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**디렉터 또는 디렉터 풀**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

