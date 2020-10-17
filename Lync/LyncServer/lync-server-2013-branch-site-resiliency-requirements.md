---
title: 'Lync Server 2013: 분기 사이트 복구 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76107fc419891561b8c98cf0989bbb0cbddbee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504845"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 분기 사이트 복구 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-25_

이 항목에서는 사용자의 분기 사이트 복구 준비, 음성 메일 지속성 준비 및 관련 하드웨어/소프트웨어 요구 사항에 대한 정보를 제공합니다.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>사용자의 분기 사이트 복구 준비

등록자 풀을 Sba (survivable Branch 기기 (SBA) 또는 Sba (survivable 분기 서버로 설정 하 여 분기 사이트 복구를 위한 사용자를 준비 합니다.

<div>

## <a name="registrar-assignments-for-branch-users"></a>분기 사용자에 대한 등록자 할당

선택한 분기 사이트 복구 솔루션에 관계 없이 각 사용자에 게 기본 등록자를 할당 해야 합니다. 분기 사이트 사용자는 해당 등록자가 Sba (survivable Branch 기기, Sba (survivable Branch Server 또는 독립 실행형 Lync Server 2013 Standard 또는 Enterprise Edition Server에 있는지 여부에 관계 없이 분기 사이트의 등록자를 항상 등록 해야 합니다. 클라이언트에서 해당 등록자 풀을 검색하려면 DNS(Domain Name System) SRV(서비스 리소스 레코드)가 필요합니다. Sba (survivable Branch 기기를 사용할 수 없는 경우 분기 사이트 클라이언트에서 백업 등록자를 자동으로 검색 하 게 됩니다.

분기 사이트에 DNS 서버가 없는 경우에는 두 가지 방법을 통해 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버의 검색을 구성할 수 있습니다.

  - Sba (survivable branch 기기 또는 Sba (survivable 분기 서버의 FQDN (정규화 된 도메인 이름)을 가리키도록 분기 사이트의 DHCP (동적 호스트 구성 프로토콜) 서버에서 DHCP 옵션 120을 구성 합니다.

  - DHCP 120 쿼리에 응답 하도록 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 구성 합니다.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>분기 사용자를 위한 음성 라우팅

분기 사이트의 사용자를 위한 별도의 사용자 수준 VoIP(Voice over Internet Protocol) 정책을 만드는 것이 좋습니다. 이 정책에는 Sba (survivable Branch 기기 또는 분기 서버 게이트웨이를 사용 하는 기본 경로와 중앙 사이트에서 PSTN (공중 전화망) 게이트웨이와 함께 트렁크를 사용 하는 하나 이상의 백업 경로가 포함 되어야 합니다. 기본 경로를 사용할 수 없는 경우 하나 이상의 중앙 사이트 게이트웨이를 사용하는 백업 경로가 대신 사용됩니다. 이 방식을 사용하면 사용자가 등록된 위치(분기 사이트 등록자 또는 중앙 사이트의 백업 등록자 풀)에 관계없이 사용자의 VoIP 정책이 항상 적용됩니다. 이 방식은 장애 조치(failover) 시나리오에서 중요한 고려 사항입니다. 예를 들어 Sba (survivable 분기 기기의 이름을 바꾸거나 중앙 사이트에서 백업 등록자 풀에 연결 하도록 Sba (survivable Branch 기기를 다시 구성 해야 하는 경우 분기 사이트 사용자를 해당 기간 동안 중앙 사이트로 이동 해야 합니다. Sba (survivable 분기 기기의 이름을 바꾸거나 다시 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [부록 B: Sba (survivable Branch 어플라이언스 In Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) 을 참조 하십시오. 해당 사용자에 게 사용자 수준 VoIP 정책이 나 사용자 수준 다이얼 플랜이 없는 경우 사용자를 다른 사이트로 이동 하면 중앙 사이트의 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 분기 사이트 사이트 수준 VoIP 정책 및 다이얼 플랜 대신 사용자에 게 기본적으로 적용 됩니다. 이 시나리오에서는 백업 등록자 풀에서 사용되는 사이트 수준 VoIP 정책 및 사이트 수준 다이얼 플랜이 분기 사이트 사용자에게도 적용될 수 있지 않는 한 해당 통화가 실패합니다. 예를 들어 일본에 있는 분기 사이트의 사용자가 레드몬드의 중앙 사이트로 이동될 경우 모든 7자리 숫자 통화에 +1425를 추가하는 정규화 규칙의 다이얼 플랜은 해당 사용자에 대한 통화를 올바르게 변환하지 않을 수 있습니다.

<div>


> [!IMPORTANT]  
> 지점 백업 경로를 만드는 경우 두 개의 PSTN 전화 사용 레코드를 지점 사용자 정책에 추가하고 각 레코드에 별도의 경로를 할당하는 것이 좋습니다. 첫 번째 또는 기본 경로는 SBA (Sba (survivable Branch 어플라이언스) 또는 분기 서버와 연결 된 게이트웨이에 직접 통화 합니다. 두 번째 또는 백업 경로는 중앙 사이트에서 게이트웨이로 전화를 연결 하는 것입니다. 통화를 전달할 때 SBA(fea-boa) 또는 분기 서버는 두 번째 사용 레코드를 시도하기 전에 첫 번째 PSTN 사용 레코드에 할당된 모든 경로를 시도합니다.



</div>

분기 게이트웨이 또는 Sba (survivable Branch 기기 사이트의 Windows 구성 요소를 사용할 수 없는 경우 분기 사이트 사용자에 대 한 인바운드 호출이 해당 사용자에 게 전달 되도록 하려면 (즉, 예를 들어 유지 관리를 위해 Sba (survivable Branch 기기 또는 분기 게이트웨이가 다운 된 경우, 게이트웨이에서 장애 조치 (failover) 경로를 만들거나 (직접 안쪽 전화 걸기) 공급자와 함께 작업을 수행 하 여 수신 전화를 중앙 사이트의 백업 등록자 풀로 리디렉션합니다. 여기에서 통화는 WAN 링크를 통해 분기 사용자에게 라우팅됩니다. 경로가 PSTN 게이트웨이 또는 기타 트렁크 피어의 허용되는 전화 번호 형식을 따르도록 경로가 숫자로 변환되는지 확인하십시오. 장애 조치 (failover) 경로를 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 장애 조치 (failover) 경로 구성을](lync-server-2013-configuring-a-failover-route.md)참조 하십시오. 또한 수신 통화를 정규화하도록 분기 사이트의 게이트웨이와 연결된 트렁크에 대한 서비스 수준의 다이얼 플랜을 만듭니다. 분기 사이트에 Sba (survivable 분기 기기가 두 개 있는 경우 별도의 서비스 수준 요금제가 필요한 경우가 아니면 둘 다에 대해 사이트 수준 다이얼 플랜을 만들 수 있습니다.

<div>


> [!NOTE]  
> 현재 상태, 회의 또는 장애 조치를 중앙 사이트에 의존하는 분기 사이트 사용자의 중앙 사이트 리소스 사용을 계산하려면 각 분기 사이트 사용자를 중앙 사이트에 등록된 사용자로 간주하는 것이 좋습니다. 현재 Sba (survivable 분기 기기에 등록 된 사용자를 포함 하 여 분기 사이트 사용자 수에 대 한 제한이 없습니다.



</div>

사용자 수준 다이얼 플랜 및 음성 정책을 만들어 분기 사이트 사용자에게 할당하는 것도 좋습니다. 자세한 내용은 배포 설명서의 [lync server 2013에서 전화 걸기 계획 만들기](lync-server-2013-create-a-dial-plan.md) 및 [lync server 2013에서 분기 사용자에 대 한 VoIP 라우팅 정책 만들기](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) 를 참조 하십시오.

<div>

## <a name="routing-extension-numbers"></a>내선 번호 라우팅

분기 사이트 사용자에 대 한 다이얼 플랜 및 음성 정책을 준비 하는 경우에는 Msrtcsip-gateways line (또는 Line URI) 특성에 사용 되는 문자열 및 숫자 형식과 일치 하는 정규화 규칙 및 변환 규칙을 포함 하 여 분기 사이트 사용자와 중앙 사이트 사용자 간에 사용 하도록 설정 된 Lync 2013 통화가 제대로 라우팅될 수 있도록 해야 합니다 (특히, WAN 링크를 사용할 수 없음). 전화 번호만 있는 것이 아니라 내선이 포함된 전화 접속 번호의 경우에는 특별한 추가 고려 사항이 있습니다.

내선 번호를 포함하는 줄 URI와 일치하는 정규화 규칙 및 변환 규칙은 배타적으로 사용되든 전체 E.164 전화 번호에 추가로 사용되든 간에 추가적인 요구 사항이 있습니다. 이 섹션에서는 내선 번호가 포함된 줄 URI에 대한 통화를 라우팅하는 몇 가지 예제 시나리오에 대해 설명합니다.

조직에 개별 사용자에 대한 DID(Direct Inward Dial) 전화 번호가 구성되어 있지 않고 각 사용자의 줄 URI에 내선 번호*만* 구성된 경우 내부 사용자는 내선 번호만 사용하여 서로 통화할 수 있습니다. 하지만 분기 사이트 사용자와 중앙 사이트 사용자 간의 통화에 적용되는 내선 번호와 일치하는 정규화 규칙을 구성해야 합니다.

분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 있는 시나리오에서는 분기 사이트 사용자로부터 중앙 사이트 사용자로의 통화에는 통화가 PSTN을 통해 라우팅되지 않으므로 번호를 변환할 일치하는 정규화 규칙이 필요하지 않습니다. 예를 들면 다음과 같습니다.


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>규칙 이름</th>
<th>설명</th>
<th>발신 제한</th>
<th>Translation</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>5자리 숫자를 변환하지 않음</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>$1</p></td>
<td><p>10001이 변환되지 않음</p></td>
</tr>
</tbody>
</table>


또한 분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 없고 분기 사이트로부터의 통화를 PSTN을 통해 라우팅해야 하는 경우와 같은 특정 시나리오를 위한 내선 번호를 수용할 수 있어야 합니다. WAN을 사용할 수 없는 동안 분기 사이트 사용자가 중앙 사이트 사용자의 내선만 사용하여 중앙 사이트 사용자에게 통화를 시작할 경우 중앙 사이트 사용자의 전체 전화 번호를 추가하는 아웃바운드 변환 규칙을 설정해야 합니다. 사용자의 줄 URI에 조직의 전체 전화 번호가 포함되고 사용자에게 고유한 전체 전화 번호 대신 사용자의 고유한 내선 번호가 포함된 경우 대신 조직의 전체 전화 번호를 추가하는 아웃바운드 변환 규칙을 설정해야 합니다. 예를 들면 다음과 같습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>일치 패턴</th>
<th>Translation</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5자리 숫자를 사용자의 전화 번호 및 내선으로 변환</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>+ 14255550123; ext = $1</p></td>
<td><p>10001이 +14255550123;ext=10001로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>5자리 숫자를 사용자의 조직 전화 번호 및 사용자의 내선으로 변환</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>+ 14255550100으로; ext = $1</p></td>
<td><p>10001이 +14255550100;ext=10001로 변환됨</p></td>
</tr>
</tbody>
</table>


이 시나리오에서 PSTN에 대한 재라우팅을 처리하는 트렁크 피어가 내선 번호를 지원하지 않을 경우에는 아웃바운드 변환 규칙에서도 내선 번호를 제거해야 합니다. 예를 들면 다음과 같습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>일치 패턴</th>
<th>Translation</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내선이 포함된 전화 번호에서 내선 제거</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+14255550123;ext=10001이 +14255550123으로 변환됨</p></td>
</tr>
</tbody>
</table>


WAN 링크를 사용할 수 있는지 여부에 관계없이 조직에 개별 사용자에 대한 DID 번호가 구성되어 있지 않고 사용자의 줄 URI에 조직의 전화 번호 및 사용자의 고유한 내선 번호가 포함된 경우 트렁크 피어 또는 분기 사이트의 PSTN 게이트웨이가 연결할 수 있는 번호를 사용하여 조직의 전화 번호 줄 URI를 구성해야 합니다. 통화가 또한 해당 번호로 라우팅되도록 고유한 내선을 포함하도록 조직 전화 번호 줄 URI를 구성해야 합니다.

사이트 간의 WAN 링크를 사용할 수 없을 때 중앙 사이트 사용자에서 분기 사이트 사용자로의 통화에 대한 자세한 내용은 이 항목의 뒷부분에 있는 음성 메일 지속성 준비를 참조하십시오. 기타 샘플 규칙을 비롯 한 다이얼 플랜 및 정규화 규칙에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) , 배포 설명서의 [lync server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md) 을 참조 하십시오. 아웃 바운드 변환 규칙에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 변환 규칙](lync-server-2013-translation-rules.md) 및 배포 설명서의 [lync server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>음성 메일 지속성 준비

Exchange UM (통합 메시징)은 일반적으로 분기 사이트가 아닌 중앙 사이트 에서만 설치 됩니다. 발신자는 분기 사이트와 중앙 사이트 간의 WAN 링크를 사용할 수 없는 경우에도 음성 메일 메시지를 남길 수 있어야 합니다. 따라서 분기 사이트 사용자에 게 음성 메일을 제공 하는 Exchange UM 자동 전화 교환 전화 번호에 대 한 줄 URI를 구성 하려면 음성 정책, 다이얼 플랜, 그리고 해당 voice 메일 번호에 해당 하는 정규화 규칙 외에도 특별히 고려해 야 할 사항이 있습니다.

Sba (survivable branch 기기 (SBAs) 및 Sba (survivable 분기 서버는 WAN 중단 시 분기 사용자에 게 음성 메일 지 속성 제공 합니다. 특히 Sba (survivable Branch 기기나 Sba (survivable Branch Server를 사용 하는 경우 WAN을 사용할 수 없는 경우 SBA 또는 Sba (survivable 분기 서버는 PSTN을 통해 응답 하지 않은 통화를 중앙 사이트의 Exchange UM으로 다시 라우팅합니다. SBA 또는 Sba (survivable 분기 서버를 사용 하는 경우 사용자는 WAN 중단 시 PSTN을 통해 음성 메일 메시지를 검색할 수도 있습니다. 마지막으로, WAN 중단 중에 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버는 누락 된 호출 알림을 큐에 대기 시키고 WAN이 복원 되 면 Exchange UM 서버에 업로드 합니다. 음성 메일 다시 라우팅 기능을 다시 사용할 수 있도록 하려면 중앙 사이트 풀의 FQDN에 대 한 항목과에 지 서버 FQDN에 대 한 항목을 Sba (survivable Branch Server의 hosts 파일에 추가 해야 합니다. 그렇지 않으면 분기 사이트에 DNS 서버가 없는 경우 DNS 확인 시간이 초과될 수 있습니다.

분기 사이트 사용자에 대해 음성 메일 지속성을 제공하려면 다음과 같이 구성하는 것이 좋습니다.

  - Microsoft Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 해야 합니다. 이 구성은 사용자에게 전송 또는 교환원에게 전송과 같은 다른 모든 일반 기능을 비활성화하고 메시지만 허용하도록 AA를 제한합니다. 또는 Exchange 관리자는 일반 AA를 사용하거나 통화를 교환원에게 라우팅하도록 사용자 지정된 AA를 사용할 수 있습니다.

  - Lync Server 관리자는 AA 전화 번호를 사용 하 여 Sba (survivable Branch 기기 또는 분기 서버에 대 한 음성 메일 다시 경로 설정에서이 전화 번호를 **exchange um 자동 전화 교환** 번호로 사용할 수 있어야 합니다.

  - Lync Server 관리자는 Exchange UM 구독자 액세스 전화 번호를 가져오고 해당 번호를 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에 대 한 음성 메일 다시 경로 설정의 **구독자 액세스** 번호로 사용 해야 합니다.

  - Lync Server 관리자는 WAN 중단 시 음성 메일에 액세스 해야 하는 모든 분기 사용자에 게 하나의 다이얼 플랜이 연결 되도록 Exchange UM을 구성 해야 합니다.

  - WAN 링크를 사용할 수 없으면 분기 사이트 사용자에 대한 통화를 사용자의 Exchange UM(통합 메시징) 음성 사서함으로 라우팅할 수 있지만 통화에 적용되는 음성 정책이 고유하고 내선 번호를 포함하지 않는 음성 메일 전화 번호를 지정하는 경우에만 가능합니다.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>분기 사이트 복구를 위한 하드웨어 및 소프트웨어 요구 사항

하드웨어 및 소프트웨어 요구 사항은 복구 솔루션에 따라 다릅니다.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>SBA(Survivable Branch Appliance)에 대한 요구 사항

필요한 하드웨어 및 소프트웨어는 Sba (survivable Branch 기기에 기본 제공 됩니다. 그러나 각 분기 사이트에서 DHCP 서버를 배포 하 여 클라이언트 IP 주소를 구하는 것이 좋습니다. 그렇지 않으면 DHCP 임대가 만료 되는 경우 클라이언트에 IP 연결이 없습니다.

엔터프라이즈 DNS 서버가 중앙 사이트에만 있는 경우에는 WAN을 중단 하는 동안 분기 사이트 사용자에 게 연결할 수 없으며, 따라서 DNS SRV (서비스 (SRV) 리소스 레코드)를 사용 하는 Lync Server 검색이 실패 합니다. WAN 중단 중에 프롬프트 재라우팅을 보장하려면 DNS 레코드가 분기 사이트에서 캐시되어야 합니다. 분기 라우터에서 지원할 경우에는 DNS 캐싱을 사용하도록 설정하십시오. 또는 분기 사이트에 DNS 서버를 배포할 수 있습니다. 이는 독립 실행형 서버 이거나 DNS 기능을 지 원하는 Sba (survivable Branch 기기의 버전일 수 있습니다. 자세한 내용은 Sba (survivable Branch 기기 공급자에 게 문의 하십시오.

<div>


> [!NOTE]  
> 분기 사이트에서 도메인 컨트롤러를 사용할 필요는 없습니다. Sba (survivable 분기 기기는 로그인 시 클라이언트의 인증서 요청에 대 한 응답으로 클라이언트를 전송 하는 특수 한 인증서를 사용 하 여 클라이언트를 인증 합니다.



</div>

Lync 클라이언트는 DHCP 옵션 120 (SIP 등록자 옵션)을 사용 하 여 Lync Server를 검색할 수 있습니다. 이 작업은 다음 두 가지 방법 중 하나로 구성할 수 있습니다.

  - 분기 사이트에서 DHCP 서버를 구성 하 여 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 등록자의 FQDN을 반환 하는 DHCP 120 쿼리에 회신 합니다.

  - Lync Server DHCP를 켭니다. 이 옵션을 설정 하면 Lync Server 등록자는 DHCP Option 120 쿼리에 응답 합니다. 등록자는 DHCP 옵션 120이 아닌 모든 DHCP 쿼리에 응답 하지 않습니다.

또한 여러 서브넷이 있는 대규모 분기 사이트의 경우 dhcp 옵션 120 쿼리를 DHCP 서버 (구성 1) 또는 등록자 (구성 2)로 전달 하도록 dhcp 릴레이 에이전트를 사용 하도록 설정 해야 합니다.

마지막으로 분기 사이트 사용자는 Enterprise Voice에 대해 구성 하 고 적절 한 통합 통신 끝점을 사용 하 여 프로 비전 해야 합니다.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Sba (survivable 분기 서버에 대 한 요구 사항

Sba (survivable 분기 서버에 대 한 요구 사항은 프런트 엔드 서버에 대 한 요구 사항과 동일 합니다. 자세한 내용은 계획 설명서에서 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Lync Server Branch-Site 배포 Full-Scale에 대 한 요구 사항

자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 인프라 요구 사항 결정](lync-server-2013-determining-your-infrastructure-requirements.md) 을 참조 하십시오.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

