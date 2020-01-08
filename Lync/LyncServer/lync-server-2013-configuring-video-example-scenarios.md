---
title: 'Lync Server 2013: 비디오 예제 시나리오 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Lync Server 2013에 대 한 비디오 구성 예제 시나리오

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

Lync 2013는 1920 x 1080 full 고화질 (HD) 비디오 및 갤러리 보기 비디오를 지원 하기 위해 새로운 비디오 기능을 추가 합니다. 고객 데이터를 기반으로 하는 측정값은 일반적인 비디오 대역폭이 Lync 2010에 비해 약간만 증가 했지만 전체 HD 지원으로 인해 최대 비디오 스트림 대역폭이 증가 함 (자세한 내용은 [Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)"미디어 트래픽 네트워크 사용량" 섹션을 참조 하세요.) 따라서 관리자는 특정 사용자 (예: 네트워크 용량이 적은 지점의 사용자)에 대 한 비디오 대역폭을 제한 하 고 다른 사용자에 게 최상의 화질 (예: 임원)을 적용할 수 있습니다.

다음 표에서는 다양 한 네트워크 용량에 대해 비디오를 구성 하기 위한 권장 설정 목록을 제공 합니다. 이러한 설정은 일부 사용자 시나리오가 더 높은 해상도 동영상을 보내고 받지 못하도록 제한 합니다 (맨 오른쪽 열 참조). 최소 설정으로 인해 최대 수신 네트워크 대역폭 때문에 갤러리 비디오를 사용할 수 없게 됩니다.

### <a name="recommended-video-settings"></a>권장 되는 비디오 설정

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
<th>우수한 품질의 동영상을 위한 비디오 해상도가 필요 합니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>방법은</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>피어 투 피어: 최대 1920 x 1080 비디오 해상도</p>
<p>갤러리 보기: 최대 2 1920 x 1080 비디오 또는 여러 개의 작은 해상도 비디오</p></td>
</tr>
<tr class="even">
<td><p>적합</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>피어 투 피어: 최대 1280 x 720 비디오 해상도</p>
<p>갤러리 보기: 최대 5 640 x 360 해상도 비디오</p></td>
</tr>
<tr class="odd">
<td><p>높음이나</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>피어 투 피어: 최대 960 x 540 비디오 해상도</p>
<p>갤러리 보기: 최대 5 424 x 240 해상도 비디오</p></td>
</tr>
<tr class="even">
<td><p>솟</p></td>
<td><p>False</p></td>
<td><p>해제</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>피어 투 피어: 최대 424 x 240 비디오 해상도</p>
<p>갤러리 보기: 사용할 수 없음</p></td>
</tr>
</tbody>
</table>


위의 표에 나와 있는 정보를 사용 하 여 조직의 일부 사용자에 대 한 새 HD 비디오 및 갤러리 보기 비디오 회의 기능을 배포 하는 동시에 다른 사용자에 대 한 비디오 해상도를 허용할 수 있습니다.

다음 예제에서는 관리자가 최고 화질으로 경영진만 사용할 수 있는 새로운 비디오 기능을 제공 합니다. 네트워크 용량이 낮은 원격 지점 사무실의 경우에는 앞 테이블의 최소 설정만 배포 됩니다. 다른 모든 직원의 경우 앞의 표에 나와 있는 "좋은" 설정이 배포 됩니다.

관리자가 경영진에 게 새 기능을 배포 하기 위해 ExecutiveVideo 이라는 회의 정책을 만듭니다. 이 회의 정책에는 다음과 같은 설정이 있습니다.

  - VideoBitRateKB는 8000 Kbps로 설정 됩니다.

  - TotalReceiveVideoBitRateKB는 8000 Kbps로 설정 됩니다.

  - AllowMultiview가 True로 설정 되어 있습니다.

  - EnableMultiviewJoin가 True로 설정 되어 있습니다.

지사의 직원의 경우 관리자가 BranchOfficeVideo 이라는 회의 정책을 만듭니다. 이 회의 정책에는 다음과 같은 설정이 있습니다.

  - VideoBitRateKB는 350 Kbps로 설정 됩니다.

  - TotalReceiveVideoBitRateKB는 350 Kbps로 설정 됩니다.

  - AllowMultiview가 True로 설정 되어 있습니다.

  - EnableMultiviewJoin가 False로 설정 됨

다른 모든 직원의 경우 관리자가 StandardVideo 라는 회의 정책을 만듭니다. 이 회의 정책에는 다음과 같은 설정이 있습니다.

  - VideoBitRateKB는 2500 Kbps로 설정 됩니다.

  - TotalReceiveVideoBitRateKB는 2500 Kbps로 설정 됩니다.

  - AllowMultiview가 True로 설정 되어 있습니다.

  - EnableMultiviewJoin가 True로 설정 되어 있습니다.

관리자가 사용자에 게 다음과 같이 회의 정책을 할당 합니다.

  - ExecutiveVideo 회의 정책은 경영진에 게 배정 됩니다.

  - BranchOfficeVideo 회의 정책은 지사에 있는 모든 직원에 게 할당 됩니다.

  - StandardVideo 회의 정책은 다른 모든 직원에 게 할당 됩니다.

이러한 회의 정책 할당을 통해 다음 사용자 환경이 생성 됩니다.

  - 모든 사용자 지원 갤러리 보기를 사용 하 여 구성 되었지만 지점에 있는 직원이 갤러리 보기를 경험해 볼 수 없습니다.

  - 2-파티 또는 단체 회의의 경우, 해당 하드웨어와 네트워크 링크가 지 원하는 경우 1920 x 1080 full HD 비디오를 보낼 수 있으며, 다른 참가자 클라이언트가이를 지 원하는 경우 1920 x 1080 full HD 비디오를 받을 수 있습니다.

  - 임원을 보유 하 고 있지 않은 직원은 2 자 또는 단체 회의에서 경영진 보다 저렴 한 해상도를 경험할 수 있지만 좋은 해상도를 제공 합니다.

  - Lync에서 기본 비디오 창 크기를 표시할 때 지사에 거주 하는 직원이 두 대의 영상 품질을 잘 알 수 있습니다. 그러나 Lync 창이 전체 화면으로 최대화 되어 있으면 비디오 해상도가 증가 하지 않습니다. 단체 컨퍼런스의 경우 지사에 있는 직원이 하나의 활성 비디오만 볼 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

