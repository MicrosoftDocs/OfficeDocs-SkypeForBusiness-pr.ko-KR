---
title: 'Lync Server 2013: 직접 SIP 배포 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d3d51c8323ab448951255ac9f7cf8d284896ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013의 직접 SIP 배포 옵션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

이 항목에서는 직접 SIP 연결을 배포 하기 위한 예제 토폴로지를 제공 합니다.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server 독립 실행형

조직에서이 섹션에 설명 된 배포 중 하나를 사용 하는 경우 Lync Server 2013를 조직의 일부 또는 전체에 대 한 유일한 전화 통신 솔루션으로 사용할 수 있습니다. 이 섹션에서는 다음 배포에 대해 자세히 설명 합니다.

  - **증분 배포:** 이 옵션은 기존 PBX (private branch exchange) 인프라가 있고 조직 내의 더 작은 그룹 또는 팀에 엔터프라이즈 음성을 점진적으로 도입 하려는 경우를 가정 합니다.

  - **Lync Server VoIP 전용 배포:** 이 옵션은 기존 전화 통신 인프라가 없는 사이트에서 Enterprise Voice를 배포 한다고 가정 합니다.

<div>

## <a name="incremental-deployment"></a>증분 배포

증분 배포에서 Lync Server 2013은 개별 팀 또는 부서에 대 한 유일한 전화 통신 솔루션 이지만 조직의 나머지 사용자는 계속 해 서 PBX를 사용 합니다. 이 증분 배포 전략은 제어 되는 파일럿 프로그램을 통해 기업에 IP 전화 통신을 도입 하는 한 가지 방법을 제공 합니다. Microsoft 통합 통신에서 제공 하는 통신 요구 사항이 가장 적합 한 작업 그룹은 Enterprise Voice로 이동 되 고 다른 사용자는 기존 PBX에 남아 있습니다. 필요한 경우 추가 작업 그룹을 Enterprise Voice로 마이그레이션할 수 있습니다.

통신 요구 사항이 공통 되 고 중앙 집중식 관리에 도움이 되는 사용자 그룹을 명확 하 게 정의 해야 하는 경우에는 증분 옵션을 사용 하는 것이 좋습니다. 또한이 옵션은 장거리 비용 절약이 중요할 수 있는 국내 지역에 흩어져 있는 팀 이나 부서가 있는 경우에도 효과적입니다. 실제로이 옵션은 구성원이 전 세계에 분산 될 수 있는 가상 팀을 만드는 데 유용 합니다. 비즈니스 요구 사항 변화에 대 한 신속한 대응을 위해 이러한 팀을 만들거나 수정 하거나 제거할 수 있습니다.

다음 그림에서는 PBX 뒤에 Enterprise Voice를 배포 하기 위한 일반 토폴로지를 보여 줍니다. 다음은 증분 배포에 권장 되는 토폴로지입니다.

**증분 배포 옵션**

![부서별 마이그레이션 옵션 다이어그램](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "부서별 마이그레이션 옵션 다이어그램")

<div>


> [!NOTE]  
> Lync Server 배포를 인증 된 직접 SIP 파트너에 연결 하는 경우 중재 서버와 PBX 사이에 PSTN (공중 전화망) 게이트웨이가 필요 하지 않습니다. 인증 된 직접 SIP 파트너 목록은에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요.



</div>

<div>


> [!NOTE]  
> 이 그림에 표시 된 미디어 경로는 미디어 바이패스 사용 (권장 구성)입니다. 미디어 바이패스를 사용 하지 않도록 설정한 경우 미디어 경로가 중재 서버를 통해 라우팅됩니다.



</div>

이 토폴로지에서는 선택한 부서나 작업 그룹이 Enterprise Voice를 사용 하도록 설정 됩니다. PSTN 게이트웨이는 VoIP (Voice over Internet Protocol) 사용이 가능한 작업 그룹을 PBX에 연결 합니다. 원격 작업자를 포함 하 여 Enterprise Voice를 사용할 수 있도록 설정 된 사용자는 IP 네트워크를 통해 통신 합니다. Enterprise voice 사용자가 PSTN으로 통화 하거나 Enterprise Voice를 사용 하도록 설정 하지 않은 동료에 게 해당 PSTN 게이트웨이로 라우팅됩니다. PBX 시스템에 있는 동료 또는 PSTN의 발신자가 보낸 통화는 PSTN 게이트웨이로 라우팅되며이는 라우팅을 위해 Lync Server에 호출을 전달 합니다.

Enterprise Voice를 기존 PBX 인프라에 연결 하는 데 사용할 수 있는 두 가지 권장 구성 (PBX 앞에 PBX 및 Enterprise Voice 뒤에 Enterprise voice)이 있습니다.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 뒤의 Enterprise Voice

Enterprise Voice가 PBX 뒤에 배포 되 면 PSTN 으로부터의 모든 전화가 PBX에 도착 하 여 Enterprise Voice 사용자에 게 통화를 PSTN 게이트웨이로 라우팅하고, pbx 사용자를 PBX로 호출 합니다.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 앞의 Enterprise Voice

Enterprise Voice가 PBX 앞에 배포 되 면 모든 전화가 PSTN 게이트웨이에서 도착 하 여 Enterprise Voice 사용자에 대 한 통화를 Lync Server로 라우팅하고 pbx 사용자에 대 한 통화를 PBX에 전달 합니다. Enterprise Voice 및 PBX 사용자에 게 서 PSTN에 대 한 통화는 IP 네트워크를 통해 가장 비용 효율적인 PSTN 게이트웨이로 라우팅됩니다. 다음 표에서는이 구성의 장점과 단점을 보여 줍니다.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>PBX 앞에 Enterprise Voice를 배포 하는 경우의 장점과 단점

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>장점</th>
<th>단점</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX는 여전히 Enterprise Voice를 사용 하도록 설정 되지 않은 사용자를 지원 합니다.</p></td>
<td><p>기존 게이트웨이가 원하는 기능이 나 용량을 지원 하지 않을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>PBX는 이전의 모든 장치를 처리 합니다.</p></td>
<td><p>게이트웨이에서 PBX로 및 게이트웨이에서 중재 서버로의 트렁크가 필요 합니다. 서비스 공급자 로부터 더 많은 트렁크 필요할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice 사용자는 동일한 전화 번호를 유지 합니다.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP 전용 배포

Enterprise Voice는 새로운 기업과 기존 비즈니스를 위한 새로운 office 사이트를 제공 하며, PBX 통합에 대 한 걱정 없이 전체 기능을 갖춘 VoIP 솔루션을 구현 하거나, 실제 배포 및 유지 관리를 수행 하지 않아도 됩니다. IP PBX 인프라 비용 이 솔루션은 사이트 및 원격 작업자를 모두 지원 합니다.

이 배포에서는 모든 통화가 IP 네트워크를 통해 라우팅됩니다. PSTN 통화는 적절 한 PSTN 게이트웨이로 라우팅됩니다. Lync 2013 또는 Lync Phone Edition은 softphone 역할을 합니다. 사용자가 제어할 PBX 전화가 없기 때문에 원격 통화 제어를 사용할 수 없으며 필요 하지 않습니다. 음성 메일 및 자동 전화 교환 서비스는 Exchange UM (통합 메시징)의 선택적 배포를 통해 제공 됩니다.

<div>


> [!NOTE]  
> Lync Server 2013을 지 원하는 데 필요한 네트워크 인프라 외에, VoIP 전용 배포는 소규모의 자격 있는 게이트웨이를 사용 하 여 팩스 컴퓨터 및 아날로그 장치를 지원할 수 있습니다.



</div>

다음 그림에서는 VoIP 전용 배포의 일반적인 토폴로지를 보여 줍니다.

**VoIP 전용 배포 옵션**

![Greenfidle 배포 옵션](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 배포 옵션")

<div>


> [!NOTE]  
> 이 그림에 표시 된 미디어 경로는 미디어 바이패스 사용 (권장 구성)입니다. 미디어 바이패스를 사용 하지 않도록 설정한 경우 미디어 경로가 중재 서버를 통해 라우팅됩니다.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

