---
title: 'Lync Server 2013: 미디어 포트 범위 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Lync Server 2013에서 미디어 포트 범위 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

미디어 포트 범위 설정은 클라이언트 성능에 큰 영향을 미칠 수 있으므로 구성 해야 합니다. Lync Server Management Shell을 사용 하 여 이러한 설정을 구성할 수 있습니다.

### <a name="media-port-range-settings"></a>미디어 포트 범위 설정

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>설정</th>
<th>설명</th>
<th>Lync Server 관리 셸 cmdlet</th>
<th>Cmdlet 매개 변수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>서버에서 보낸 포트 범위를 클라이언트에서 미디어 및 신호에 사용할지 여부를 지정 합니다. 하위 값 MinMediaPort 및 MaxMediaPort와 함께 사용 됩니다.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>미디어에 사용할 시작 포트 번호를 지정 합니다. MaxMediaPort와 결합 하 여 포트 범위를 지정 합니다. 권장 되는 최소 범위는 40 포트입니다.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (클라이언트 미디어에 사용할 시작 포트 번호를 나타냄)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>미디어에 사용할 가장 높은 포트 번호를 지정 합니다. MinMediaPort와 결합 하 여 포트 범위를 지정 합니다. 권장 되는 최소 범위는 40 포트입니다.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (클라이언트 미디어에 사용할 수 있는 총 포트 수를 나타냅니다. 기본값은 40입니다.)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>미디어 포트 범위 설정을 구성 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 cmdlet을 실행 합니다.
    
        Get-CsConferencingConfiguration
    
    이 cmdlet은 회의 구성 설정을 반환 합니다.

3.  변경 하려는 매개 변수 및 값을 사용 하 여 다음 cmdlet을 실행 합니다 (이 cmdlet에 대 한 매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서 참조):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 특정 사이트에 대 한 추가 회의 구성 설정 집합을 만들 수 있습니다. 사이트 id에 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet을 사용 합니다. 사이트에 대 한 새 회의 구성 설정을 만들면 사이트 설정이 전역 설정 보다 우선적으로 적용 됩니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

