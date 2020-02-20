---
title: 'Lync Server 2013: 비디오 예제 시나리오 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71eb886bb50f503b43eb757cc41310583fc11303
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Lync Server 2013에 대 한 비디오 예제 시나리오 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

Lync 2013는 새로운 비디오 기능을 지원 합니다. 1920 x 1080 full HD (고화질) 비디오 및 갤러리 보기 비디오 고객 데이터를 기반으로 하는 측정값은 일반적인 비디오 대역폭이 Lync 2010에 비해 약간 비해 증가 했지만, 전체 HD 지원으로 인해 최대 비디오 스트림 대역폭이 증가 함 (자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)에서 "미디어 트래픽 네트워크 사용" 섹션을 참조 하세요.) 따라서 관리자는 특정 사용자 (예: 네트워크 용량이 적은 지점의 사용자)에 대해 비디오 대역폭을 제한 하 고, 다른 사용자에 대해 최상의 가능한 비디오 품질을 유지 하는 데 도움을 받을 수 있습니다 (예: 임원).

다음 표에는 다양한 네트워크 용량에 대한 권장 비디오 구성 설정 목록이 나와 있습니다. 이러한 설정은 일부 사용자 시나리오에 대한 고해상도 비디오 송/수신을 제한합니다(맨 오른쪽 열 참조). 최소 설정으로 인해 최대 수신 네트워크 대역폭이 낮아지므로 갤러리 비디오를 사용할 수 없게 됩니다.

### <a name="recommended-video-settings"></a>권장 비디오 설정

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>표준 화질 비디오에 대한 예상 비디오 해상도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>방법은</p></td>
<td><p>참</p></td>
<td><p>참</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>피어 투 피어: 최대 1920 x 1080 비디오 해상도</p>
<p>갤러리 보기: 최대 1920 x 1080 비디오 두 개 또는 이보다 낮은 해상도의 여러 비디오</p></td>
</tr>
<tr class="even">
<td><p>좋습니다</p></td>
<td><p>참</p></td>
<td><p>참</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>피어 투 피어: 최대 1280 x 720 비디오 해상도</p>
<p>갤러리 보기: 최대 640 x 360 해상도 비디오 5개</p></td>
</tr>
<tr class="odd">
<td><p>보통</p></td>
<td><p>참</p></td>
<td><p>참</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>피어 투 피어: 최대 960 x 540 비디오 해상도</p>
<p>갤러리 보기: 최대 424 x 240 해상도 비디오 5개</p></td>
</tr>
<tr class="even">
<td><p>적어도</p></td>
<td><p>참</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>피어 투 피어: 최대 424 x 240 비디오 해상도</p>
<p>갤러리 보기: 사용할 수 없음</p></td>
</tr>
</tbody>
</table>


위의 표의 정보를 사용하여 조직 내 일부 사용자를 위한 새 HD 비디오와 갤러리 보기 비디오 회의 기능을 배포하면서 나머지 사용자에게 다양한 비디오 해상도를 허용할 수 있습니다.

다음 예제에서는 관리자가 중역만 사용할 수 있는 최고 비디오 품질의 새 비디오 기능을 공개합니다. 네트워크 용량이 적은 원격 지점 직원의 경우 위의 표에 나오는 최소 설정만 배포됩니다. 그 밖의 모든 직원에게는 위의 표에 나오는 "표준" 설정이 배포됩니다.

중역에게 새 기능을 공개하기 위해 관리자는 ExecutiveVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.

  - VideoBitRateKB가 8000Kbps로 설정됨

  - TotalReceiveVideoBitRateKB가 8000Kbps로 설정됨

  - AllowMultiview가 True로 설정됨

  - EnableMultiviewJoin이 True로 설정됨

관리자는 지점 직원을 위해 BranchOfficeVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.

  - VideoBitRateKB가 350Kbps로 설정됨

  - TotalReceiveVideoBitRateKB가 350Kbps로 설정됨

  - AllowMultiview가 True로 설정됨

  - EnableMultiviewJoin이 False로 설정됨

관리자는 그 밖의 모든 직원을 위해 StandardVideo라는 회의 정책을 만듭니다. 이 회의 정책의 설정은 다음과 같습니다.

  - VideoBitRateKB가 2500Kbps로 설정됨

  - TotalReceiveVideoBitRateKB가 2500Kbps로 설정됨

  - AllowMultiview가 True로 설정됨

  - EnableMultiviewJoin이 True로 설정됨

관리자는 다음과 같이 사용자에게 회의 정책을 할당합니다.

  - ExecutiveVideo 회의 정책은 중역에게 할당됩니다.

  - BranchOfficeVideo 회의 정책은 지점의 모든 직원에게 할당됩니다.

  - StandardVideo 회의 정책은 그 밖의 모든 직원에게 할당됩니다.

이러한 회의 정책 할당에 따라 다음과 같은 사용자 환경이 만들어집니다.

  - 사용자에 의해 구성된 모든 회의에서 갤러리 보기를 지원하지만, 지점의 직원은 갤러리 보기를 사용할 수 없습니다.

  - 두 사용자 간 회의 또는 단체 회의에서 중역은 자신의 하드웨어 및 네트워크 링크에서 지원할 경우 1920 x 1080 Full HD 비디오를 전송할 수 있으며, 다른 참여자 클라이언트에서 지원할 경우 1920 x 1080 Full HD 비디오를 수신할 수 있습니다.

  - 중역 이외의 직원은 두 사용자 간 회의 또는 단체 회의에서 중역보다 낮은 표준 화질의 해상도를 사용하게 됩니다.

  - Lync에서 기본 비디오 창 크기를 표시 하는 경우 지사에 거주 하는 직원이 두 명의 사용자에 게 좋은 화질을 얻게 됩니다. 그러나 Lync 창이 전체 화면으로 최대화 되 면 비디오 해상도가 증가 하지 않습니다. 단체 전화 회의의 경우 지사의 직원에 게는 하나의 활성 비디오만 표시 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

