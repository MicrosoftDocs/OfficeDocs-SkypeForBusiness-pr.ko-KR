---
title: '단계 10: 레거시 사이트 해제'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e46c2977289ae8fec1db26e4eb33dfd6736f838
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>단계 10: 레거시 사이트 해제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-16_

다음 항목에서는 Office Communications Server 2007 R2의 레거시 배포에서 서버 및 풀을 비활성화 하 고 제거 하는 방법에 대 한 지침을 제공 합니다. 이 섹션에 나열된 모든 절차가 필수는 아닙니다. 사용할 해제 절차를 확인하려면 이러한 각 항목의 정보를 확인하십시오.

<div>


> [!WARNING]  
> 전화 접속 회의에 대 한 회의 디렉터리를 Lync Server 2013로 가져온 경우에는 풀 해제를 시작 하기 전에 전화 회의 디렉터리 소유권을 Lync Server 2013로 전환 하는 것이 중요 합니다. 먼저 회의 디렉터리 소유권을 전환하지 않고 풀을 해제할 경우 모든 마이그레이션된 모임에 대한 전화 접속 기능이 더 이상 작동하지 않습니다. 레거시 풀에 있는 각 회의 디렉터리에 대해 소유권을 한 번 전환하는 단계를 수행해야 합니다.



</div>

<div>


> [!IMPORTANT]  
> 레거시 환경을 제거 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (c) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [회의 디렉터리 이동](move-conference-directories.md)

  - [DNS SRV 레코드 업데이트](update-dns-srv-records_1.md)

  - [서버 및 풀 해제](decommissioning-servers-and-pools.md)

  - [BackCompatSite 제거](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

