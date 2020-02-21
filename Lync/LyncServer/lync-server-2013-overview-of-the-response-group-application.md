---
title: 'Lync Server 2013: 응답 그룹 응용 프로그램 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 007d6b21ab37aee16ae8c98b202bd3900f4dab45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 응용 프로그램 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-11_

발신자가 응답 그룹을 호출 하면 통화가 헌트 그룹을 기반으로 하는 에이전트로 또는 발신자의 IVR (대화형 음성 응답) 질문에 대 한 답변으로 라우팅됩니다. 응답 그룹 응용 프로그램은 표준 응답 그룹 라우팅 메서드를 사용 하 여 다음 사용 가능한 에이전트로 통화를 라우팅합니다. 통화 라우팅 방법에는 직렬, 가장 오래 된 유휴, 병렬, 라운드 로빈 및 전화 교환 라우팅이 포함 됩니다 (현재 현재 상태에 관계 없이 모든 수신 전화에 대해 동시에 모든 에이전트가 호출 됨). 사용할 수 있는 에이전트가 없는 경우에는 에이전트를 사용할 수 있을 때까지 통화가 큐에 보관 됩니다. 큐에서 발신자는 사용 가능한 에이전트가 통화를 수락할 때까지 음악을 듣습니다. 큐가 꽉 찼거나 통화 시간이 초과 되 면 발신자가 메시지를 듣고 연결이 끊어지거나 다른 대상으로 전송 될 수 있습니다. 에이전트에서 통화를 수락 하면 관리자가 응답 그룹을 구성 하는 방법에 따라 발신자가 에이전트의 id를 확인할 수 있습니다. 에이전트는 공식 일 수 있으며,이 경우 그룹에 대 한 호출을 수락 하기 전에 그룹에 로그인 해야 하거나 비공식를 사용 하 여 호출을 수락 하는 그룹에 로그인 하거나이를 제외 하지 않는 것이 좋습니다.

<div>


> [!NOTE]  
> 온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.



</div>

<div>


> [!NOTE]  
> 응답 그룹 응용 프로그램은 일치 하는 내부 서비스를 사용 하 여 통화를 대기 시키고 사용 가능한 에이전트를 찾습니다. 응답 그룹 응용 프로그램을 실행 하는 각 컴퓨터는 Match service를 실행 하지만 Lync Server 풀 당 서비스를 수행 하는 하나의 일치가 동시에 활성화 됩니다. 계획 되지 않은 중단 중에 현재 서비스를 사용할 수 없게 되는 active Match 서비스를 만드는 수동 일치 중 하나가 활성화 됩니다. 응답 그룹 응용 프로그램은 계속 해 서 통화 라우팅과 큐가 중단 되지 않도록 하는 데 유용 합니다. 그러나 서비스 전환이 일치 하 게 되 면 전송 중인 모든 통화는 손실 됩니다. 예를 들어 다운 되는 프런트 엔드 서버로 인해 전환이 발생 하는 경우 해당 프런트 엔드 서버에서 서비스를 수행 하는 활성 일치에 의해서도 현재 처리 중인 통화도 모두 손실 됩니다.



</div>

Lync Server 2013에서는 응답 그룹 관리를 위해 두 가지 관리 역할 (응답 그룹 관리자 및 응답 그룹 관리자)을 사용할 수 있습니다. 응답 그룹 관리자는 모든 응답 그룹의 모든 측면을 관리할 수 있습니다. 응답 그룹 관리자는 특정 측면과 자신이 소유한 응답 그룹만 관리할 수 있습니다. Enterprise Voice를 사용 하도록 설정 된 사용자에 게 특정 응답 그룹에 대 한 제한 된 책임을 위임할 수 있으므로 새 관리자 역할은 관리 비용을 줄이는 데 도움이 될 수 있습니다.

새 관리자 역할을 수용할 수 있도록 Lync Server 2013 Response 그룹 응용 프로그램은 관리 되거나 관리 되지 않는 **워크플로 유형을** 소개 합니다. 다음 표에서는 관리 및 관리 되지 않는 응답 그룹에 대해 설명 합니다.

### <a name="managed-and-unmanaged-response-groups"></a>관리 및 관리 되지 않는 응답 그룹

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>응답 그룹 유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>관리 되지 않는</p></td>
<td><ul>
<li><p>관리 되지 않는 응답 그룹에는 할당 된 관리자가 없습니다. 응답 그룹 관리자만 이러한 응답 그룹을 구성할 수 있습니다.</p></li>
<li><p>여러 관리 되지 않는 응답 그룹이 큐 또는 에이전트 그룹을 공유할 수 있습니다.</p></li>
<li><p>응답 그룹을 이전 버전에서 Lync Server 2013로 마이그레이션하는 경우 유형이 관리 되지 않는 것으로 설정 됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>되</p></td>
<td><ul>
<li><p>응답 그룹 관리자는 관리 되는 응답 그룹의 모든 측면을 구성할 수 있습니다.</p></li>
<li><p>응답 그룹 관리자는 명시적으로 할당 되지 않은 응답 그룹을 보거나 수정할 수 없습니다.</p></li>
<li><p>응답 그룹 관리자는 명시적으로 할당 된 응답 그룹에 대 한 일부 설정만 구성할 수 있습니다.</p></li>
<li><p>관리 되는 응답 그룹은 다른 응답 그룹 (관리 또는 비관리)과 큐 또는 에이전트 그룹을 공유할 수 없습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


다음 표에서는 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹에 대해 수행할 수 있는 작업 및 수행이 불가능 한 조치에 대해 설명 합니다.

### <a name="response-group-manager-capabilities"></a>응답 그룹 관리자 기능

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>다음을 구성할 수 있습니다.</th>
<th>만들기, 삭제 또는 구성할 수 있습니다.</th>
<th>수 없습니다</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agent</p></li>
<li><p>환영 메시지</p></li>
<li><p>응답 그룹 이름</p></li>
<li><p>설명</p></li>
<li><p>표시 번호</p></li>
<li><p>업무 시간</p></li>
<li><p>통화 대기음</p></li>
<li><p>상태 (활성/비활성)</p></li>
<li><p>헌트 그룹 워크플로 또는 IVR (대화형 음성 응답) 워크플로</p></li>
</ul></td>
<td><ul>
<li><p>에이전트 그룹</p></li>
<li><p>큐</p></li>
<li><p>휴일 집합</p></li>
</ul></td>
<td><ul>
<li><p>모든 유형의 워크플로 만들기 또는 삭제</p></li>
<li><p><strong>SIP URI</strong>, <strong>전화 번호</strong>또는 <strong>워크플로 유형과</strong>같은 핵심 응답 그룹 설정을 수정 합니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


응답 그룹 관리자는 다음 도구를 사용 하 여 지정 된 응답 그룹을 관리할 수 있습니다.

  - Lync Server 제어판
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 관리자는이 도구를 사용 하 여 응답 그룹 설정만 관리할 수 있습니다. 관리자가 다른 Lync Server 설정을 사용할 수 없습니다.

    
    </div>

  - 응답 그룹 구성 도구

  - Communications Server 관리 셸

응답 그룹은 부서나 작업 그룹 환경에 맞게 확장 되며 자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)및 완전히 새로운 전화 통신 설치 환경에서 배포할 수 있습니다 .를 참조 하십시오. 엔터프라이즈 음성 배포 및 로컬 반송파 네트워크에서 들어오는 호출을 지원 합니다. 상담원은 Lync 2013, Lync 2010, Lync 2010 Attendant 또는 Lync Phone Edition을 사용 하 여 전달 된 통화를 가져올 수 있습니다.

응답 그룹 응용 프로그램은 Enterprise Voice의 구성 요소입니다. Enterprise Voice를 배포 하면 응답 그룹 응용 프로그램이 자동으로 설치 되 고 활성화 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

