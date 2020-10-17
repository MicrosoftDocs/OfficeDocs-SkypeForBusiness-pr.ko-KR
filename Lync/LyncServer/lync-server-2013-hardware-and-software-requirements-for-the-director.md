---
title: 'Lync Server 2013: 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536865"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013의 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

이 섹션에서는 디렉터에 대 한 하드웨어 및 소프트웨어 요구 사항과 디렉터에 대해 지원 되는 배치 시나리오에 대해 자세히 설명 합니다.

<div>

## <a name="hardware-requirements-for-the-director"></a>디렉터에 대한 하드웨어 요구 사항

다음 표에는 디렉터에 대 한 하드웨어 요구 사항이 나와 있습니다.

### <a name="hardware-requirements-for-the-director"></a>디렉터에 대한 하드웨어 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>최소 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64비트 프로세서, 쿼드 코어, 2.0GHz 이상</p></li>
<li><p>64비트 듀얼 프로세서, 듀얼 코어, 2.0GHz 이상</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>메모리</p></td>
<td><p>4GB(기가바이트)</p></td>
</tr>
<tr class="odd">
<td><p>공간이</p></td>
<td><ul>
<li><p>10K RPM HDD(하드 디스크 드라이브)</p></li>
<li><p>성능이 10K RPM HDD 이상인 고성능 SDD(반도체 드라이브)</p></li>
<li><p>2x RAID 10(스트라이프 및 미러) 15K RPM 디스크(데이터베이스 데이터 파일용)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>네트워크</p></td>
<td><ul>
<li><p>1Gbps(초당 기가비트) 네트워크 어댑터 2개(권장)</p></li>
<li><p>1Gbps 네트워크 어댑터 1개(지원)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>디렉터에 대 한 소프트웨어 요구 사항

디렉터 역할은 Lync Server 2013 Enterprise Edition을 실행 하는 서버에만 배포할 수 있습니다.

디렉터에는 다음과 같은 64 비트 운영 체제 중 하나가 필요 합니다.

  - Windows Server 2008 R2 Standard 운영 체제 서비스 팩 1

  - Windows Server 2008 R2 Enterprise 운영 체제 서비스 팩 1

  - 서비스 팩 1이 포함 된 Windows Server 2008 R2 Datacenter 운영 체제

  - Windows Server 2012 Standard 운영 체제

  - Windows Server 2012 Datacenter 운영 체제

또한 lync Server 2013에서는 [추가 서버 지원 및 Lync server 2013의 요구 사항](lync-server-2013-additional-server-support-and-requirements.md)항목에 설명 된 대로 다음 프로그램 및 업데이트를 설치 해야 합니다.

</div>

<div>

## <a name="supported-collocation"></a>지원되는 배치

Lync Server 2013의 다른 서버 역할을 사용 하 여 디렉터 서버 역할을 배치 된 수 없습니다. 그러나 디렉터를 배포 하지 않으면 프런트 엔드 서버에서이 역할을 가정 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

