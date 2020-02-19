---
title: 'Lync Server 2013: 미디어 포트 범위 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 207acda151acb02e73b5fb3d6192356e8cdd7b37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Lync Server 2013에서 미디어 포트 범위 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

미디어 포트 범위 설정은 클라이언트 성능에 큰 영향을 줄 수 있으므로 구성해야 합니다. Lync Server 관리 셸을 사용 하 여 이러한 설정을 구성할 수 있습니다.

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
<td><p>사용자가 서버에서 전송된 포트 범위를 미디어 및 신호 전달에 사용해야 하는지 여부를 지정합니다. 하위 값인 MinMediaPort 및 MaxMediaPort와 함께 사용됩니다.</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>미디어에 사용할 시작 포트 번호를 지정합니다. MaxMediaPort와 함께 포트 범위를 지정합니다. 권장되는 최소 범위는 40포트입니다.</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPort(클라이언트 미디어에 사용할 시작 포트 번호를 나타냄)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>미디어에 사용할 최대 포트 번호를 지정합니다. MinMediaPort와 함께 포트 범위를 지정합니다. 권장되는 최소 범위는 40포트입니다.</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPortRange(클라이언트 미디어에 사용할 수 있는 총 포트 수를 나타내며, 기본값은 40임)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>미디어 포트 범위 설정을 구성하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 cmdlet을 실행합니다.
    
        Get-CsConferencingConfiguration
    
    이 cmdlet는 회의 구성 설정을 반환합니다.

3.  변경 하려는 매개 변수 및 값을 사용 하 여 다음 cmdlet을 실행 합니다 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서 참조).
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 특정 사이트에 대한 추가 회의 구성 설정 집합을 만들 수 있습니다. 사이트 ID로 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet를 사용합니다. 사이트에 대한 새 회의 구성 설정을 만들면 사이트 설정이 전역 설정보다 우선합니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

