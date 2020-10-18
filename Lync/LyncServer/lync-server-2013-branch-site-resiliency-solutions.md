---
title: 'Lync Server 2013: 분기 사이트 복구 솔루션'
description: 'Lync Server 2013: 분기 사이트 복구 솔루션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 796ed22344f02bca16571ff5f156c6bb80b1fcfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572964"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013의 분기 사이트 복구 솔루션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-10_

조직에 분기 사이트 복구 기능을 제공 하면 분명 한 이점이 있습니다. 특히 중앙 사이트에 대 한 연결이 끊어지면 분기 사이트 사용자에 게 엔터프라이즈 음성 서비스 및 음성 메일이 계속 해 서 표시 됩니다 (음성 메일 다시 라우팅 설정을 구성 하는 경우 자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항](lync-server-2013-branch-site-resiliency-requirements.md)참조). 그러나 사용자가 25 명 미만인 사이트의 경우 복구 솔루션은 투자 수익률을 충분히 제공 하지 못할 수 있습니다.

분기 사이트 탄성을 제공하려는 경우 세 가지 방법 중 하나를 사용할 수 있습니다. 다음 표를 사용하면 조직에 가장 적합한 옵션을 선택하는 데 도움이 될 수 있습니다.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>상황</th>
<th>권장 방법</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>분기 사이트에서 25~1000명의 사용자를 호스팅하려는 경우(ROI(투자 수익률)가 전체 배포를 지원하지 않거나 로컬 관리 지원을 사용할 수 없음)</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Sba (survivable 분기 어플라이언스는 Windows Server 2008 r 2에서 Lync Server 등록자 및 중재 서버가 실행 되는 업계 표준 블레이드 서버입니다. Sba (survivable 분기 기기에는 PSTN (공중 전화망) 게이트웨이도 포함 되어 있습니다. SBA(Survivable Branch Appliance) 자격 검증/인증 프로그램에서 Microsoft 파트너가 개발한 적격 타사 장치는 WAN 오류 시에도 지속적인 PSTN 연결을 제공하지만, 이러한 기능은 중앙 사이트의 프런트 엔드 서버를 기반으로 하기 때문에 이 접근 방식이 탄력적인 현재 상태 및 회의 기능을 제공하지는 못합니다.</p>
<p>Sba (survivable 분기 기기에 대 한 자세한 내용은 &quot; 이 항목의 뒷부분에 나오는 Sba (survivable Branch 어플라이언스 details를 참조 하십시오 &quot; .</p>
<p><strong>참고:</strong> Sba (survivable Branch 기기와 함께 SIP 트렁크를 사용 하기로 결정 한 경우에는 Sba (survivable Branch 어플라이언스 공급 업체에 문의 하 여 조직에 가장 적합 한 서비스 공급자를 알아봅니다.</p></td>
</tr>
<tr class="even">
<td><p>분기 사이트에서 1000와 2000 사용자 간의 호스트, 복원 가능한 WAN 연결이 부족 한 경우 교육 된 Lync Server 관리자를 사용할 수 있습니다.</p></td>
<td><p>Sba (survivable 분기 서버 또는 두 개의 Sba (survivable Branch 기기</p>
<p>Sba (survivable Branch Server는 Lync Server 등록자 및 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 회의 지정 하드웨어 요구 사항입니다. 이 서버는 전화 서비스 공급자에 대한 SIP 트렁크 또는 PSTN 게이트웨이에 연결되어야 합니다.</p>
<p>Sba (survivable 분기 서버에 대 한 자세한 내용은 &quot; 이 항목의 뒷부분에 나오는 Sba (survivable Branch Server details를 참조 하십시오 &quot; .</p></td>
</tr>
<tr class="odd">
<td><p>최대 5000 명의 사용자에 대 한 음성 기능 외에도 현재 상태 및 회의 기능이 필요 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우</p></td>
<td><p>Standard Edition 서버를 분기 사이트가 아니라 중앙 사이트로 배포합니다.</p>
<p>전체 수평 Lync Server 배포는 WAN 오류가 발생 하는 경우 지속적인 PSTN 연결 및 탄성 현재 상태 및 회의를 제공 합니다.</p>
<p>이 솔루션을 준비 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013의 조직 계획</a>, lync server 2013에 대 한 <a href="lync-server-2013-determining-your-system-requirements.md">시스템 요구 사항 결정</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013의 인프라 요구 사항 결정</a>, 계획 설명서의 기타 관련 섹션을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>복구 토폴로지

다음 그림에서는 분기 사이트 복구를 지원하는 권장 토폴로지를 보여 줍니다.

**분기 사이트 복구 옵션**

![음성 분기 복구 옵션](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "음성 분기 복구 옵션")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>SBA(Survivable Branch Appliance) 세부 정보

Lync Server Sba (survivable Branch 기기에는 다음과 같은 구성 요소가 포함 되어 있습니다.

  - 사용자 인증, 등록 및 통화 라우팅을 수행하는 등록자

  - 등록자와 PSTN 게이트웨이 간의 신호를 처리하는 중재 서버

  - WAN 중단 시 PSTN 통화를 대체 전송으로 라우팅하는 PSTN 게이트웨이

  - 로컬 사용자 데이터를 저장하는 SQL Server Express

또한 Sba (survivable Branch 기기에는 PSTN 트렁크, 아날로그 포트 및 이더넷 어댑터만 포함 됩니다.

중앙 사이트에 대 한 분기 사이트의 WAN 연결을 사용할 수 없는 경우 내부 분기 사용자는 계속 해 서 Sba (survivable Branch 기기 등록자를 사용 하 여 등록 되 고 PSTN에 대 한 Sba (survivable Branch 기기 연결을 통해 음성 서비스가 중단 되지 않도록 합니다. 홈 또는 다른 원격 위치에서 연결하는 분기 사이트 사용자는 분기 사이트의 WAN 링크를 사용할 수 없어도 중앙 사이트의 등록자 서버에 등록할 수 있습니다. 이러한 사용자는 분기 사이트로의 인바운드 통화가 음성 메일로 이동하는 것을 제외하고는 전체 통합 통신 기능을 사용할 수 있습니다. WAN 연결이 복구되면 분기 사이트 사용자를 위한 전체 기능이 복원됩니다. Sba (survivable 분기 어플라이언스 또는 서비스 복원에 대 한 장애 조치 (failover)를 수행 하려면 IT 관리자가 있어야 합니다.

Lync Server는 분기 사이트에서 최대 2 개의 Sba (survivable 분기 기기를 지원 합니다.

<div>


> [!NOTE]  
> Lync Server Sba (survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 대화방 카드를 볼 수 없습니다.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>SBA(Survivable Branch Appliance) 배포 개요

Sba (survivable 분기 어플라이언스는 Microsoft와의 파트너 관계를 설정 하는 원래 장비 제조업체에서 제조 되었으며, 부가 가치 소매 업체를 대신 하 여 배포 됩니다. 이 배포는 Lync Server가 중앙 사이트에 배포 되 고, 분기 사이트에 대 한 WAN 연결이 설정 되 고, 분기 사이트 사용자가 Enterprise Voice를 사용할 수 있는 경우에만 발생 합니다.

이러한 단계에 대 한 자세한 내용은 배포 설명서에서 [a Lync Server 2013을 사용 하 여 a Sba (survivable Branch 어플라이언스 또는 Server 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 를 참조 하십시오.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>사용자 권한</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sba (survivable 분기 기기에 대 한 Active Directory 도메인 서비스 설정</p></td>
<td><p><strong>중앙 사이트에서 다음을 수행합니다.</strong></p>
<ol>
<li><p>분기 사이트에서 Sba (survivable Branch 기기를 설치 및 활성화 하는 기술자에 대 한 도메인 사용자 계정 (또는 엔터프라이즈 id)을 만듭니다.</p></li>
<li><p>Active Directory 도메인 서비스에서 Sba (survivable Branch 기기에 대해 해당 FQDN (정규화 된 도메인 이름)을 사용 하 여 컴퓨터 계정을 만듭니다.</p></li>
<li><p>토폴로지 작성기에서 Sba (survivable 분기 기기를 만들고 게시 합니다.</p></li>
</ol></td>
<td><p>기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다. Sba (survivable 분기 어플라이언스는 RTCSBAUniversalServices 그룹에 속해야 하며 토폴로지 작성기를 사용할 때 자동으로 수행 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Sba (survivable Branch 기기를 설치 하 고 정품 인증 합니다.</p></td>
<td><p><strong>분기 사이트에서 다음을 수행합니다.</strong></p>
<ol>
<li><p>Sba (survivable Branch 기기를 이더넷 포트 및 PSTN 포트에 연결 합니다.</p></li>
<li><p>Sba (survivable Branch 기기를 시작 합니다.</p></li>
<li><p>중앙 사이트에서 Sba (survivable Branch 기기에 대해 만든 도메인 사용자 계정을 사용 하 여 Sba (survivable Branch 기기를 도메인에 참가 시킵니다. FQDN 및 IP 주소를 컴퓨터 계정에 만든 FQDN과 일치하도록 설정합니다.</p></li>
<li><p>OEM 사용자 인터페이스를 사용 하 여 Sba (survivable Branch 기기를 구성 합니다.</p></li>
<li><p>PSTN 연결을 테스트합니다.</p></li>
</ol></td>
<td><p>기술자 사용자 계정은 RTCUniversalSBATechnicians의 구성원이어야 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>지속 가능 분기 서버 세부 정보

토폴로지 작성기에서 분기 사이트를 만들고 해당 사이트에 Sba (survivable 분기 서버를 추가한 다음 역할을 설치 하려는 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.

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

