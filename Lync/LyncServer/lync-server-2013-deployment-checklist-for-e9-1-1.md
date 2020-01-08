---
title: 'Lync Server 2013: E9에 대 한 배포 검사 목록-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013의 E9-1-1에 대 한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

향상 된 9-1-1 (E9-1)을 효과적으로 계획 하려면 다음과 같은 배포 요구 사항을 포함 해야 합니다.

  - E9를 배포 하기 위한 필수 조건-1-1

  - E9를 배포 하는 데 필요한 단계는-1-1입니다.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9에 대 한 배포 전제 조건-1-1

E9를 배포 하기 전에 먼저 중앙 관리 저장소, 프론트 엔드 풀 또는 스탠더드 버전 서버, 하나 이상의 중재 서버 또는 조정 서버 풀, Lync Server 클라이언트를 포함 하 여 Lync Server 내부 서버를 배포 해야 합니다. 또한 E9-1 배포의 경우 자격 있는 E9-1-1 서비스 공급자에 대 한 SIP 트렁크가 필요 하거나 PSTN (공개 전환 전화 네트워크) 게이트웨이에서 긴급 한 위치 Id 번호 (ELIN) 게이트웨이를 사용 해야 합니다. Lync Server는 미국 내 에서만 E9-1 서비스 공급자 사용을 지원 합니다.

</div>

<div>

## <a name="deployment-process"></a>배포 프로세스

다음 표에서는 E9-1-1 배포 프로세스에 대해 간략하게 설명 합니다. 배포 단계에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 향상 된 9-1-1 구성을](lync-server-2013-configure-enhanced-9-1-1.md) 참조 하세요.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>음성 용도, 경로 및 트렁크 구성 구성</p></td>
<td><ol>
<li><p>새 PSTN 사용 레코드를 만듭니다. 이것은 위치 정책의 <strong>PSTN 사용</strong> 설정에 사용 되는 이름과 같습니다.</p></li>
<li><p>이전 단계에서 만든 PSTN 사용 레코드에 대 한 음성 경로를 만들거나 할당 한 다음 게이트웨이 특성을 E9-1-1 SIP 트렁크 또는 ELIN gateway에 놓습니다.</p></li>
<li><p>SIP 트렁크 E9-1-1 서비스 공급자의 경우 SIP를 통해 E9-1-1 통화를 처리할 트렁크를 설정 하 여 <strong>set-cstrunkconfiguration – EnablePIDFLOSupport</strong> cmdlet을 사용 하 여 pidf-낮음 데이터를 전달 합니다.</p></li>
<li><p>선택적으로 SIP 트렁크 E9-1-1 서비스 공급자의 경우 E9-1 서비스 공급자의 SIP 트렁크에서 처리 되지 않는 통화에 대 한 로컬 PSTN 경로를 만들거나 지정 합니다. 이 경로는 E9 서비스 공급자에 대 한 연결을 사용할 수 없는 경우에 사용 됩니다. E9 서비스 공급자에서 지원 되는 경우 911 다이얼 문자열을 국가/지역 긴급 통화 응답 센터의 직접 안쪽 전화 걸기 () 번호로 변환 하는 트렁크 구성 규칙을 게이트웨이에 할당 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013의 E9-1-1 음성 경로 구성</a></p></td>
</tr>
<tr class="even">
<td><p>위치 정책 만들기 및 사용자 및 서브넷에 할당</p></td>
<td><ol>
<li><p>전역 위치 정책을 검토 합니다.</p></li>
<li><p>사용자 수준 범위를 사용 하 여 위치 정책을 만듭니다. 또는 조직에 응급 용도가 서로 다른 사이트가 여러 개 있는 경우 네트워크 수준 범위를 사용 하 여 위치 정책을 만듭니다.</p></li>
<li><p>네트워크 사이트에 위치 정책을 할당 합니다.</p></li>
<li><p>네트워크 사이트에 적절 한 서브넷을 추가 합니다.</p></li>
<li><p>) 위치 정책을 사용자 정책에 할당 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (위치 정책 만들기 제외)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Lync Server 2013에서 위치 정책 만들기</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013에서 네트워크 사이트에 위치 정책 추가</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">E9의 네트워크 사이트와 서브넷 연결 Lync Server 2013에서-1-1</a></p></td>
</tr>
<tr class="odd">
<td><p>위치 데이터베이스 구성</p></td>
<td><ol>
<li><p>네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다.</p></li>
<li><p>게이트웨이에서 ELIN 대해 &lt;CompanyName&gt; 열에 elin를 추가 합니다.</p></li>
<li><p>주소 유효성 검사를 위해 E9-1 서비스 공급자에 대 한 연결을 구성 합니다.</p></li>
<li><p>E9-1-1 서비스 공급자로 주소의 유효성을 검사 합니다.</p></li>
<li><p>업데이트 된 데이터베이스를 게시 합니다.</p></li>
<li><p>게이트웨이에서 ELIN 대해, ELIN을 PSTN 캐리어의 자동 위치 확인 (ALI) 데이터베이스에 업로드 합니다.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 구성</a></p></td>
</tr>
<tr class="even">
<td><p>고급 기능 구성 (선택 사항)</p></td>
<td><ol>
<li><p>SNMP 응용 프로그램의 URL을 구성 합니다.</p></li>
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

