---
title: 'Lync Server 2013: E9-1-1에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52920c81e2055b5151280bbd65e9b2b6a90c0b73
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522805"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013의 E9-1-1에 대 한 배포 검사 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

향상 된 9-1-1 (E9-1-1)을 효과적으로 계획 하려면 다음 배포 요구 사항을 포함 해야 합니다.

  - E9-1-1 배포를 위한 필수 구성 요소

  - E9-1-1을 배포 하는 데 필요한 단계

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 배포 필수 구성 요소

E9-1-1을 배포 하기 전에 먼저 Lync Server 내부 서버 (중앙 관리 저장소, 프런트 엔드 풀 또는 Standard Edition 서버, 하나 이상의 중재 서버 또는 중재 서버 풀 및 Lync Server 클라이언트 포함)를 배포 해야 합니다. 또한 E9-1-1 배포에서는 SIP 트렁크가 적격 E9-1-1 서비스 공급자 또는 공중 전화망 (응급 위치 식별 번호) 게이트웨이를 사용 해야 합니다. Lync Server에서는 미국 내 에서만 E9-1-1 서비스 공급자를 사용할 지를 지원 합니다.

</div>

<div>

## <a name="deployment-process"></a>배포 프로세스

다음 표에서는 E9-1-1 배포 프로세스에 대해 간략하게 설명 합니다. 배포 단계에 대 한 자세한 내용은 배포 설명서의 [Configure 다기능 9-1-1 In Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) 을 참조 하십시오.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>음성 용도, 경로 및 트렁크 구성 구성</p></td>
<td><ol>
<li><p>새 PSTN 사용 레코드를 만듭니다. 이 이름은 위치 정책의 <strong>PSTN 사용</strong> 설정에 사용 되는 이름과 같습니다.</p></li>
<li><p>이전 단계에서 만든 PSTN 사용 레코드에 대 한 음성 경로를 만들거나 할당 한 다음 gateway 특성을 E9-1-1 SIP 트렁크 또는 ELIN gateway로 가리킵니다.</p></li>
<li><p>SIP 트렁크 E9-1-1 서비스 공급자의 경우 SIP를 통해 E9-1-1 통화를 처리할 트렁크를 설정 하 여 <strong>get-cstrunkconfiguration-EnablePIDFLOSupport</strong> cmdlet을 사용 하 여 pidf-로 데이터를 전달 합니다.</p></li>
<li><p>SIP 트렁크 E9-1-1 서비스 공급자의 경우 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리 하지 않는 통화에 대해 로컬 PSTN 경로를 만들거나 할당 합니다. E9-1-1 서비스 공급자에 대 한 연결을 사용할 수 없는 경우이 경로가 사용 됩니다. E9-1-1 서비스 공급자가 지 원하는 경우 911 다이얼 문자열을 국내/지역 긴급 통화 응답 센터 (i/o) 번호로 변환 하는 트렁크 구성 규칙을 게이트웨이에 할당 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013에서 E9-1-1 음성 경로 구성</a></p></td>
</tr>
<tr class="even">
<td><p>위치 정책을 만들고 사용자 및 서브넷에 할당</p></td>
<td><ol>
<li><p>전역 위치 정책을 검토 합니다.</p></li>
<li><p>사용자 수준 범위로 위치 정책을 만듭니다. 또는 조직에 응급 용도가 서로 다른 사이트가 둘 이상 있는 경우 네트워크 수준 범위를 사용 하 여 위치 정책을 만듭니다.</p></li>
<li><p>네트워크 사이트에 위치 정책을 할당 합니다.</p></li>
<li><p>네트워크 사이트에 적절 한 서브넷을 추가 합니다.</p></li>
<li><p>반드시 위치 정책을 사용자 정책에 할당 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (위치 정책 만들기 제외)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Lync Server 2013의 위치 정책 만들기</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013에서 네트워크 사이트에 위치 정책 추가</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대 한 네트워크 사이트와 서브넷 연결</a></p></td>
</tr>
<tr class="odd">
<td><p>위치 데이터베이스 구성</p></td>
<td><ol>
<li><p>데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다.</p></li>
<li><p>ELIN 게이트웨이의 경우에는 CompanyName 열에 Elin를 추가 &lt; &gt; 합니다.</p></li>
<li><p>주소 유효성 검사를 위해 E9-1-1 서비스 공급자에 대 한 연결을 구성 합니다.</p></li>
<li><p>E9-1-1 서비스 공급자를 사용 하 여 주소 유효성을 검사 합니다.</p></li>
<li><p>업데이트된 데이터베이스를 게시합니다.</p></li>
<li><p>ELIN 게이트웨이의 경우 PSTN 캐리어의 ALI (자동 위치 식별) 데이터베이스에 Elin을 업로드 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 구성</a></p></td>
</tr>
<tr class="even">
<td><p>고급 기능 구성 (선택 사항)</p></td>
<td><ol>
<li><p>SNMP 응용 프로그램에 대 한 URL을 구성 합니다.</p></li>
<li><p>보조 위치 정보 서비스의 위치에 대 한 URL을 구성 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013에서 SNMP 응용 프로그램 구성</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

