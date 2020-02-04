---
title: 'Lync Server 2013: 지점 사이트 SIP 트렁크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c31f0f42a10905f784536b08f10370be9694800
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Lync Server 2013의 지점 사이트 SIP 트렁크

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

경우에 따라 선택한 지점 사이트에서 분산 SIP 트렁크을 구현 해야 할 수 있습니다. 지점 사이트에 대 한 SIP 트렁크가 필요한 지 여부를 확인 하려면 [Lync Server 2013에서 sip 트렁크를 구현 하는 방법](lync-server-2013-how-do-i-implement-sip-trunking.md)에 대 한 정보를 검토 하세요.

지점 사이트에서 SIP trunks를 배포 하기 위한 지원 되는 토폴로지 옵션에 대 한 자세한 내용은 [Lync Server 2013의 지점 사이트 복원 솔루션](lync-server-2013-branch-site-resiliency-solutions.md)을 참조 하세요.

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>예제 지점 사이트 SIP 트렁크 요구 사항 분석

지점 사이트의 SIP 트렁크를 배포 하기로 결정 한 경우 사이트별 비용 분석을 수행 해야 합니다. 예를 들어 Redmond, 워싱턴, 뉴욕에 있는 지사에 중앙 사이트가 있는 기업은 분석을 수행 하 여 뉴욕 사이트에서 로컬 서비스 공급자로 SIP 트렁크를 구현할지 여부를 결정 해야 합니다.

뉴욕에 있는 분산 된 SIP 트렁크가 비용 효율적인 지 여부를 확인 하려면 직접 안쪽으로 거는 전화 접속 (예)에서 SIP 트렁크를 사용 하는 것을 확인 하 고 Redmond (425) 이외의 영역에 대해 뉴욕의 통화 수를 분석 합니다. 중앙 사이트에서 지점 사이트를 종료 했을 수 있습니다. 예를 들어 Redmond 중앙 사이트는 뉴욕 분기 사이트에 대 한 번호를 호스트할 수 있습니다. 분산 된 SIP 트렁크를 구현 하는 비용이 해당 통화 비용 보다 낮은 경우 뉴욕 지점 분기 사이트에서 SIP 트렁크를 구현 하는 것이 좋습니다.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>다른 지사 사이트 SIP 트렁크 요구 사항

게이트웨이 대신 SIP 트렁크 배포 중에서 선택 하는 것은 각 옵션의 PSTN (공개 통신 네트워크) 시외 전화 요금 간의 차이를 기반으로 하는 것입니다. 지점 사이트 SIP 트렁크를 배포 하는 경우에는 회복성 및 대역폭 요구 사항도 확인 해야 합니다. 지점 사이트와 중앙 사이트 간의 링크가 탄력적이 고 충분 한 대역폭을 보유 하 고 있는 경우 SIP 트렁크 또는 게이트웨이를 배포할 수 있습니다. 지점 사이트에서 Survivable Branch 기기를 배포할 필요는 없습니다. 지점 사이트와 중앙 사이트 간의 링크가 복원성이 없는 경우 Survivable Branch 기기를 배포 하거나 지점 사이트의 게이트웨이나 SIP 트렁크를 사용 하 여 Survivable Branch 서버를 배포 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

