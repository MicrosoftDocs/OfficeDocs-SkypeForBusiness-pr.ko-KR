---
title: '10 단계: 레거시 사이트 서비스 해제'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04054c158f1c97f5090328e1277dcdb63b1d823
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>10 단계: 레거시 사이트 서비스 해제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-16_

다음 항목에서는 Office Communications Server 2007 R2의 레거시 배포에서 서버 및 풀을 비활성화 하거나 제거 하는 방법에 대 한 지침을 제공 합니다. 이 섹션에 나열 된 절차 중 일부는 필요 하지 않습니다. 각 항목의 정보를 읽고 사용할 역할 해제 프로시저를 결정 합니다.

<div>


> [!WARNING]  
> 전화 접속 회의를 위한 회의 디렉터리를 Lync Server 2013으로 가져온 경우, 풀을 서비스 해제 하기 전에 먼저 Lync Server 2013로 전화 회의 디렉터리 소유권을 전환 하는 것이 중요 합니다. 우선 회의 디렉터리 소유권을 전환 하지 않고 풀을 역할 해제 한 경우 마이그레이션된 모든 모임의 전화 접속 기능이 더 이상 작동 하지 않습니다. 이전 풀의 각 회의 디렉터리에 대해 소유권을 한 번씩 전환 하는 단계를 수행 해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> 레거시 환경을 서비스 해제 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (사용자 MA) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [회의 디렉터리 이동](move-conference-directories.md)

  - [DNS SRV 레코드 업데이트](update-dns-srv-records_1.md)

  - [서버 및 풀 서비스 해제](decommissioning-servers-and-pools.md)

  - [BackCompatSite 제거](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

