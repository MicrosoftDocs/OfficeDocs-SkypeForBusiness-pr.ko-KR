---
title: 'Lync Server 2013: 데이터 수집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013의 데이터 수집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Microsoft Lync Server 2013 통신 소프트웨어에서 기존 및 제안 된 IP 주소와 Edge Server의 Fqdn (정규화 된 도메인 이름)을 문서화 하지 않고 Microsoft Lync Server 2013, 계획 도구를 실행할 수 있지만, 매우 어렵습니다. 때문에 구성 오류가 발생 하지 않습니다. 예를 들어 일정 기간 동안 공존이 필요한 경우에는 Lync Server 2013 Edge 배포에 대 한 기존 Edge 배포의 Fqdn을 다시 사용 하는 것이 일반적인 실수입니다. 스프레드시트, 테이블 또는 다른 시각적 양식에서 기존 및 제안 된 IP 주소와 Fqdn을 적어 두면 설치 중에 설치 문제가 발생 하는 것을 방지 하는 데 도움이 됩니다.

<div>


> [!WARNING]  
> 이전 버전의 계획 도구를 사용 하는 경우 토폴로지를 만들기 위해 도구를 사용 하 고 토폴로지 작성기에서 토폴로지를 게시 하는 데 사용할 토폴로지 문서를 내보낸 것입니다. 토폴로지 내보내기 기능은 계획 도구에서 제거 되었습니다. 이전 버전의 계획 도구를 사용 하 여 Lync Server 2013에 대 한 토폴로지 문서를 만드는 것은 바람직하지 않으며 예기치 않은 결과가 생성 됩니다.



</div>

따라서 권장 접근 방법은 Edge 토폴로지에 해당 하는 다음 데이터 컬렉션 템플릿을 사용 하 여 계획 도구에 입력 해야 하는 다양 한 FQDN과 IP 주소를 수집 하는 것입니다. 현재 및 제안 된 구성을 문서화 하 여 프로덕션 환경의 적절 한 컨텍스트에 값을 추가할 수 있습니다. 간단한 Url, 파일 공유, 부하 분산 등의 공존 및 기능을 구성 하는 방법을 고려해 야 합니다.

Microsoft Lync Server 2013를 성공적으로 배포 하려면 개별 구성 요소에 대 한 조작 및 의존을 이해 해야 합니다. 기존 네트워크 및 서버 인프라에서 데이터를 수집 하 고 이러한 섹션에서 계획 지침을 적용 하 여 Lync Server 2013 Edge 서버 구성 요소를 인프라에 통합할 수 있습니다.

[Lync Server 2013에서 토폴로지 선택](lync-server-2013-choosing-a-topology.md)에 도입 된 세 가지 주요 아키텍처가 있고 총 5 개의 배포 시나리오를 사용할 수 있습니다. 이러한 시나리오 중 하나는 데이터 수집을 시작 하는 출발점입니다. IP 주소, 서버 이름, 도메인 이름은 전체 계획 솔루션에 필요한 정보를 자세히 설명 하는 일치 하는 인증서, 방화벽 및 DNS 다이어그램과 일치 하는 예제입니다. 팀에서 인증 기관, 방화벽 구성 및 DNS를 관리 하는 팀에 의해 관리 되는 조직 간 통신에서 필요한 인증서, DNS 및 방화벽 값에 대 한 다이어그램이 나 채우기는 특히 중요 합니다. 배포 계획 다이어그램은 팀 간 공동 작업을 위해 이러한 요구 사항을 전달 하는 데 사용할 수 있는 필수 구성 요소에 대 한 정보를 제공 합니다.

제공 된 다이어그램은 일부러 제네릭이 되지만, 네트워킹, 방화벽, 인증서 만들기 및 관리, 서버 등의 교차 팀 시나리오에서 요구 사항 통신에 필요한 모든 관련 데이터를 수집할 수 있습니다. 배포 및 서버 관리는 여러 그룹에 의해 처리 됩니다. Lync Server의 배포를 진행 하는 동안 네트워킹, 방화벽, 포트, 프로토콜, 인증서 및 서버 구성에 필요한 세부 정보를 제공 하는 것은 매우 중요 합니다.

**Edge 서버 및 Edge 풀**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**역방향 프록시**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**이사 또는 이사 은행**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

