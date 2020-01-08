---
title: 'Lync Server 2013: 직접 SIP 배포 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013의 직접 SIP 배포 옵션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

이 항목에서는 직접 SIP 연결을 배포 하기 위한 예제 토폴로지를 제공 합니다.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server 독립 실행형

조직에서이 섹션에 설명 된 배포 중 하나를 사용 하는 경우에는 Lync Server 2013을 조직의 일부 또는 전체에 대 한 유일한 전화 통신 솔루션으로 사용할 수 있습니다. 이 섹션에서는 다음 배포에 대해 자세히 설명 합니다.

  - **증분 배포:** 이 옵션은 기존 PBX (개인 분기 교환) 인프라를 보유 하 고 있으며 조직 내 보다 작은 그룹 또는 팀에 게 엔터프라이즈 음성을 점진적으로 도입 하려는 것으로 가정 합니다.

  - **Lync Server VoIP 전용 배포:** 이 옵션은 기존 전화 통신 인프라가 없는 사이트에서 Enterprise Voice 배포를 고려 한다고 가정 합니다.

<div>

## <a name="incremental-deployment"></a>증분 배포

점진적 배포에서 Lync Server 2013는 개별 팀 또는 부서에 대 한 유일한 전화 통신 솔루션 이지만 조직의 나머지 사용자는 계속 해 서 PBX를 사용 합니다. 이 증분 배포 전략은 제어 되는 파일럿 프로그램을 통해 기업에 IP 전화 통신을 도입 하는 한 가지 방법을 제공 합니다. Microsoft 통합 커뮤니케이션에서 제공 하는 의사 소통 요구 사항이 엔터프라이즈 음성으로 이동 하는 동시에 다른 사용자는 기존 PBX에 남아 있는 작업 그룹입니다. 필요에 따라 추가 작업 그룹을 Enterprise Voice로 마이그레이션할 수 있습니다.

증분 옵션은 통신 요구 사항이 공통 된 사용자 그룹을 명확히 정의 하 고 중앙 집중식으로 관리할 수 있는 경우에 사용 하는 것이 좋습니다. 이 옵션은 장거리 요금을 절약 하는 팀 또는 부서가 광범위 한 지리적 지역에 걸쳐 있는 경우에도 효과적입니다. 사실이 옵션은 전세계에 분산 될 수 있는 가상 팀을 만드는 데 유용 합니다. 비즈니스 요구 사항 변화에 대 한 신속한 응답으로 이러한 팀을 만들거나 수정 하거나 제거할 수 있습니다.

다음 그림은 PBX 뒤의 엔터프라이즈 음성을 배포 하기 위한 일반적인 토폴로지를 보여 줍니다. 이는 증분 배포에 권장 되는 토폴로지입니다.

**증분 배포 옵션**

![부서별 마이그레이션 옵션 다이어그램](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "부서별 마이그레이션 옵션 다이어그램")

<div>


> [!NOTE]  
> Lync Server 배포를 인증 된 직접 SIP 파트너에 연결 하는 경우 중재 서버와 PBX 간의 PSTN (공개 통신 네트워크) 게이트웨이가 필요 하지 않습니다. 인증 된 직접 SIP 파트너 목록은 Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요 <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.



</div>

<div>


> [!NOTE]  
> 이 그림에 표시 된 미디어 경로에는 미디어 바이패스 사용 (권장 구성)이 있습니다. 미디어 바이패스를 사용 하지 않도록 선택 하는 경우 미디어 경로는 중재 서버를 통해 라우팅됩니다.



</div>

이 토폴로지에서는 Enterprise Voice에 대해 선택한 부서나 작업 그룹을 사용할 수 있습니다. PSTN 게이트웨이는 Voice VoIP (인터넷 프로토콜) 사용 가능 작업 그룹을 PBX에 연결 합니다. 원격 작업자를 포함 하 여 Enterprise Voice를 사용할 수 있도록 설정한 사용자는 IP 네트워크를 통해 통신 합니다. PSTN으로 엔터프라이즈 음성 사용자를 호출 하는 경우 Enterprise Voice를 사용할 수 없는 동료에 게는 적절 한 PSTN 게이트웨이로 라우팅됩니다. PBX 시스템에 남아 있거나 PSTN의 발신자 로부터 받은 통화는 PSTN 게이트웨이로 라우팅되며,이는 라우팅에 대 한 통화를 Lync Server에 전달 합니다.

엔터프라이즈 음성을 상호 운용성을 위해 기존 PBX 인프라에 연결 하는 데는 두 가지 권장 구성 (PBX 앞의 PBX 및 Enterprise Voice 뒤쪽의 엔터프라이즈 음성)이 있습니다.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 뒤의 엔터프라이즈 음성

기업 음성이 PBX 뒤에 배포 되 면 PSTN의 모든 통화가 PBX에 도착 하 여 Enterprise Voice users에 대 한 통화를 PSTN 게이트웨이로 라우팅하고, pbx 사용자에 대 한 통화를 pbx에 보냅니다.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 앞의 엔터프라이즈 음성

PBX 앞에 엔터프라이즈 음성이 배포 되 면 모든 통화가 PSTN 게이트웨이에 도달 하 여 Enterprise Voice users에 대 한 통화를 Lync 서버로 라우팅하고 PBX 사용자에 대 한 통화를 pbx에 전달 합니다. 기업 음성과 PBX 사용자 모두의 PSTN으로 거는 통화는 IP 네트워크를 통해 가장 비용 효율적인 PSTN 게이트웨이로 전달 됩니다. 다음 표에는이 구성의 장점과 단점이 나와 있습니다.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>PBX 앞에서 엔터프라이즈 음성을 배포 하는 경우의 장점 및 단점

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>된다는</th>
<th>같은</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX는 여전히 엔터프라이즈 음성에 대해 사용 하도록 설정 되지 않은 사용자를 처리 합니다.</p></td>
<td><p>기존 게이트웨이는 원하는 기능이 나 용량을 지원 하지 않을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>PBX는 이전의 모든 장치를 처리 합니다.</p></td>
<td><p>게이트웨이에서 PBX와 게이트웨이에서 중재 서버로의 트렁크가 필요 합니다. 서비스 공급자 로부터 더 trunks 필요할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>기업 음성 사용자는 동일한 전화 번호를 유지 합니다.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP 전용 배포

엔터프라이즈 음성은 새로운 비즈니스와 기존 비즈니스를 위한 새로운 office 사이트를 제공 하며, PBX 통합에 대 한 걱정 없이 완전 한 기능을 갖춘 VoIP 솔루션을 구현 하거나, 실제 배포 및 유지 관리를 할 필요가 없습니다. IP PBX 인프라의 비용. 이 솔루션은 사이트 및 원격 작업자를 모두 지원 합니다.

이 배포에서는 모든 통화가 IP 네트워크를 통해 라우팅됩니다. PSTN으로 거는 통화는 적절 한 PSTN 게이트웨이로 라우팅됩니다. Lync 2013 또는 Lync Phone Edition은 softphone 역할을 합니다. 원격 통화 제어는 사용자가 제어할 수 있는 PBX 전화가 없기 때문에 사용할 수 없으며 필요 하지 않습니다. 음성 메일 및 자동 전화 교환 서비스는 Exchange UM (통합 메시징)의 선택적 배포를 통해 사용할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013을 지 원하는 데 필요한 네트워크 인프라 외에도, VoIP 전용 배포는 소형의 적격 게이트웨이를 사용 하 여 팩스 컴퓨터와 아날로그 장치를 지원할 수 있습니다.



</div>

다음 그림에는 VoIP 전용 배포에 대 한 일반적인 토폴로지가 나와 있습니다.

**VoIP 전용 배포 옵션**

![Greenfidle 배포 옵션](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 배포 옵션")

<div>


> [!NOTE]  
> 이 그림에 표시 된 미디어 경로에는 미디어 바이패스 사용 (권장 구성)이 있습니다. 미디어 바이패스를 사용 하지 않도록 선택 하는 경우 미디어 경로는 중재 서버를 통해 라우팅됩니다.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

