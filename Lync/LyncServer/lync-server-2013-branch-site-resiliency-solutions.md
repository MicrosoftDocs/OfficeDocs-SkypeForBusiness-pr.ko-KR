---
title: 'Lync Server 2013: 분기 사이트 복구 솔루션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013의 분기 사이트 복구 솔루션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-10_

조직에 지점 사이트 복원을 제공 하는 것은 명백한 장점이 있습니다. 특히 중앙 사이트에 대 한 연결이 끊어지면 지점 사이트 사용자는 계속 해 서 엔터프라이즈 음성 서비스와 음성 메일을 받을 수 있습니다 (음성 메일 다시 라우팅 설정을 구성 하는 경우 자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복구 요구 사항](lync-server-2013-branch-site-resiliency-requirements.md)참조). 그러나 사용자가 25 명 미만인 사이트의 경우 복원 솔루션은 투자 수익률을 충분히 제공 하지 않을 수 있습니다.

지점 사이트 탄력성을 제공 하기로 결정 한 경우 세 가지 옵션이 있습니다. 다음 표에서는 조직에 가장 적합 한 옵션을 결정 하는 데 도움이 될 수 있습니다.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>...</th>
<th>다음을 사용 하는 것이 좋습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>지사 사이트에서 25 명에서 1000 사용자 간 호스팅, 투자 수익률이 전체 배포를 지원 하지 않거나, 지역 관리 지원을 사용할 수 없는 경우</p></td>
<td><p>Survivable 분기 기기</p>
<p>Survivable Branch 기기는 Windows Server 2008 R2에서 실행 되는 Lync Server 등록자와 중재 서버가 있는 업계 표준 블레이드 서버입니다. Survivable Branch 기기에는 PSTN (공용 전환 전화 네트워크) 게이트웨이도 포함 되어 있습니다. 정식 타사 장치 (Survivable Branch 기기 (SBA) 검증/인증 프로그램)는 WAN 장애가 발생 했을 때 지속적인 PSTN 연결을 제공 하지만,이 접근 방법은 중앙 사이트의 프런트 엔드 서버에 종속 되어 있기 때문에 복원 현재 상태와 회의를 제공 하지 않습니다.</p>
<p>Survivable Branch 기기에 대 한 자세한 내용은 &quot;이 항목의&quot; 뒷부분에 나오는 Survivable branch 기기 세부 정보를 참조 하세요.</p>
<p><strong>참고:</strong> Survivable Branch 기기에도 SIP 트렁크를 사용 하기로 결정 한 경우, Survivable Branch 기기 공급 업체에 문의 하 여 조직에 가장 적합 한 서비스 공급자에 대해 알아보세요.</p></td>
</tr>
<tr class="even">
<td><p>지점 사이트의 1000 및 2000 사용자 간 호스팅, 복원성 WAN 연결이 부족 하 고, 교육 된 Lync Server 관리자를 사용할 수 있습니다.</p></td>
<td><p>Survivable Branch 서버 또는 두 개의 Survivable Branch 기기.</p>
<p>Survivable Branch 서버는 Lync Server 등록자와 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 모임에서 지정 된 하드웨어 요구 사항입니다. 전화 서비스 공급자에 게 PSTN 게이트웨이나 SIP 트렁크에 연결 해야 합니다.</p>
<p>Survivable Branch 서버에 대 한 자세한 내용은 &quot;이 항목의 뒷부분에&quot; 나오는 Survivable branch 서버 세부 정보를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>최대 5000 사용자를 위한 음성 기능 외에도 현재 상태 및 회의 기능이 필요 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우</p></td>
<td><p>지점 사이트가 아닌 표준 버전 서버를 사용 하 여 중앙 사이트로 배포 합니다.</p>
<p>전체 규모 Lync Server 배포는 WAN 장애가 발생 하는 경우 지속적인 PSTN 연결 및 탄성 현재 상태 및 회의를 제공 합니다.</p>
<p>이 솔루션을 준비 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013에 대 한 조직 계획</a>, lync server <a href="lync-server-2013-determining-your-system-requirements.md">2013의 시스템 요구 사항 결정</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013의 인프라 요구 사항</a>결정, 기타 관련 섹션을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>복원 토폴로지

다음 그림은 지점 사이트 탄력성에 대해 권장 되는 토폴로지를 보여줍니다.

**지점 사이트 복구 옵션**

![음성 분기 복원 옵션](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "음성 분기 복원") 옵션

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch 기기 세부 정보

Lync Server Survivable Branch 기기는 다음 구성 요소를 포함 합니다.

  - 사용자 인증, 등록 및 통화 라우팅과 같은 등록 기관

  - 레지스트라와 PSTN 게이트웨이 간의 신호를 처리 하기 위한 중재 서버

  - WAN이 중단 되는 경우 PSTN에 대 한 대체 전송으로 호출을 라우팅하는 PSTN 게이트웨이

  - 로컬 사용자 데이터 저장소에 대 한 SQL Server Express

Survivable Branch 기기에는 PSTN trunks, 아날로그 포트, 이더넷 어댑터도 포함 됩니다.

중앙 사이트에 대 한 지점 사이트의 WAN 연결을 사용할 수 없게 되 면 내부 지점 사용자는 계속 해 서 Survivable Branch 기기 등록 기관에 등록 하 고 Survivable Branch 기기 연결을 사용 하 여 중단 없는 음성 서비스를 얻을 수 있습니다. PSTN에 연결할 수 있습니다. 지사 사이트에 대 한 WAN 연결을 사용할 수 없는 경우 홈 또는 다른 원격 위치에서 연결 하는 지점 사이트 사용자는 중앙 사이트의 레지스트라 서버에 등록할 수 있습니다. 이러한 사용자는 전체 통합 커뮤니케이션 기능을 사용할 수 있으며,이는 지점 사이트에 대 한 인바운드 호출이 음성 메일로 이동 한다는 한 가지 예외를 발생 하는 것입니다. WAN 연결을 사용할 수 있게 되 면 전체 기능을 지사 사이트 사용자에 게 복원 해야 합니다. Survivable Branch 기기 또는 서비스 복원에 대 한 장애 조치는 IT 관리자의 존재를 요구 하지 않습니다.

Lync Server는 지점 사이트에서 최대 2 개의 Survivable Branch 기기를 지원 합니다.

<div>


> [!NOTE]  
> Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch 기기 배포 개요

Survivable Branch 기기는 Microsoft와 파트너 관계를 사용 하 여 원래 장비 제조업체에서 제조 하 고 부가 가치 소매 업체에 의해 배포 됩니다. 이 배포는 Lync Server가 중앙 사이트에 배포 되 고, 지점 사이트에 대 한 WAN 연결이 있으며, 지사 사이트 사용자가 엔터프라이즈 음성을 사용할 수 있는 경우에만 발생 합니다.

이러한 단계에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 를 참조 하세요.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>사용자 권한</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Survivable Branch 기기에 대 한 Active Directory 도메인 서비스 설정</p></td>
<td><p><strong>중앙 사이트:</strong></p>
<ol>
<li><p>지점 사이트에서 Survivable Branch 기기를 설치 하 고 활성화 하는 기술자에 대 한 도메인 사용자 계정 (또는 엔터프라이즈 id)을 만듭니다.</p></li>
<li><p>Active Directory 도메인 서비스의 Survivable Branch 기기에 대해 해당 FQDN (정규화 된 도메인 이름)을 사용 하 여 컴퓨터 계정을 만듭니다.</p></li>
<li><p>토폴로지 작성기에서 Survivable Branch 기기를 만들고 게시 합니다.</p></li>
</ol></td>
<td><p>기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원 이어야 합니다. Survivable Branch 기기는 토폴로지 작성기를 사용할 때 자동으로 일어나는 RTCSBAUniversalServices 그룹에 속해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Survivable Branch 기기를 설치 하 고 정품 인증 합니다.</p></td>
<td><p><strong>지점 사이트에서 다음을 수행 합니다.</strong></p>
<ol>
<li><p>Survivable Branch 기기를 이더넷 포트 및 PSTN 포트에 연결 합니다.</p></li>
<li><p>Survivable Branch 기기를 시작 합니다.</p></li>
<li><p>중앙 사이트에서 Survivable Branch 기기에 대해 만든 도메인 사용자 계정을 사용 하 여 Survivable Branch 기기를 도메인에 참가 합니다. FQDN과 IP 주소를 컴퓨터 계정에서 만든 FQDN과 일치 하도록 설정 합니다.</p></li>
<li><p>OEM 사용자 인터페이스를 사용 하 여 Survivable Branch 기기를 구성 합니다.</p></li>
<li><p>PSTN 연결을 테스트 합니다.</p></li>
</ol></td>
<td><p>기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원 이어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Survivable Branch 서버 세부 정보

토폴로지 작성기에서 지점 사이트를 만들고 해당 사이트에 Survivable Branch 서버를 추가한 다음 역할을 설치 하려는 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

