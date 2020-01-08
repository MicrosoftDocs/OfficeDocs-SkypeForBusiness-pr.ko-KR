---
title: 조정된 디렉터 풀 - DNS 부하 분산 및 하드웨어 부하 분산 장치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013의 조정된 디렉터 풀 - DNS 부하 분산 및 하드웨어 부하 분산 장치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

추가 용량을 처리 하 고 고가용성을 제공 하기 위해 배포 된 디렉터가 두 개 이상 있는 확장 된 디렉터 풀에는 클라이언트 및 서버 통신을 풀의 모든 구성원에 게 배포 하기 위한 부하 분산이 필요 합니다. 디렉터는 프런트 엔드 풀과 매우 비슷한 웹 서비스를 호스팅합니다. 부하 분산을 제공 하기 위해 하드웨어 로드 균형 조정 또는 DNS (domain name system) 부하 분산 및 하드웨어 부하 분산을 사용할 수 있습니다. 웹 서비스에 대 한 하드웨어 부하 분산이 필요 하며, DNS 부하 분산만이 웹 서비스에 필요한 접근 권한 값을 제공 하지 않습니다.

다음 항목에서는 하드웨어 로드 균형 조정과 함께 DNS 부하 분산을 사용 하 여 디렉터 풀을 배포 하기 위한 계획 고려 사항에 대해 설명 합니다. 하드웨어 부하 분산을 사용 하지만 디렉터 풀에 대 한 DNS 부하 분산이 아닌 경우 해당 토폴로지의 계획 요구 사항을 설명 하는 [Lync Server 2013의 확장 된 디렉터 풀 하드웨어 부하 분산](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 항목을 참조 하세요.

![확장 된 감독 풀이](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "확장 된 디렉터 풀")

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [인증서 요약 - Lync Server 2013에서 DNS 및 HLB 부하 분산됨](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013의 포트 요약 - DNS 및 HLB 부하 분산됨](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013의 DNS 요약 - DNS 및 HLB 부하 분산됨](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

