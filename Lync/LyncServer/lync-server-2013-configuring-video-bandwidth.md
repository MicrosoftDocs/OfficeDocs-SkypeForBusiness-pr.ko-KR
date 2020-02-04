---
title: 'Lync Server 2013: 비디오 대역폭 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Lync Server 2013에서 비디오 대역폭 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

Lync Server 2013에는 두 개의 타사 통화와 단체 회의를 위한 비디오 관리 설정이 포함 되어 있습니다. Lync Server 2013을 배포 하는 경우 기본 설정이 조직에 적합 한지 평가 하 고 필요에 따라 수정 해야 합니다.

이 섹션에 설명 된 매개 변수는 두 개의 파티 통화와 단체 회의에 모두 적용 됩니다. 다음 cmdlet 중 하나를 사용 하 여 이러한 설정을 보거나 수정 합니다.

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

회의 정책에서 다음 설정을 확인 합니다.

  - **VideoBitRateKb**   이 설정은 사용자가 보내는 비디오에 사용 되는 최대 비디오 비트 전송률을 kbps 단위로 지정 합니다. 기본값은 5만 kbps입니다. 유효한 값은 0 ~ 5만입니다.
    
    이 설정은 기본 비디오 및 파노라마 비디오에 별도로 적용 됩니다.
    
    예: 2000 kbps를 지정 하는 경우 Lync Server는 파노라마 비디오 스트림에 대 한 기본 비디오 스트림 및 2000 kbps에 대해 2000 kbps를 보낼 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > Lync 2013 끝점의 최대 비디오 네트워크 대역폭은 기본 비디오 2500와 파노라마 비디오의 경우 9kbps에 대 한 8000 kbps입니다. 이 최대 값에는 여러 개의 비디오를 받거나 전송 하는 경우에만 해당 됩니다. 자세한 내용은 <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013의 미디어 트래픽에 대 한 네트워크 대역폭 요구 사항</A>에서 "미디어 트래픽 네트워크 사용량" 섹션을 참조 하세요. 이 섹션에는 지원 되는 모든 해상도에 대 한 최대 및 표준 비디오 스트림 대역폭이 나열 됩니다.

    
    </div>

  - ****   Lync Server 2013의 새로운 설정인이 설정을 TotalReceiveVideoBitRateKb 클라이언트에서 받은 모든 비디오 스트림에 대해 허용 되는 최대 비트 전송률 (초당 킬로 비트)을 지정 합니다. 즉, 클라이언트가 수신할 수 있는 파노라마 비디오 스트림을 제외한 모든 비디오 스트림의 총 합계를 지정 합니다. 예를 들어 1500 kbps를 지정 하는 경우, 클라이언트는 최대 1500 kbps의 비디오를 받을 수 있으며,이 경우 여러 비디오 스트림 또는 단일 비디오 스트림으로 구성 될 수 있습니다. 이 설정은 Lync Server 2013 클라이언트에만 적용 됩니다.
    
    **TotalReceiveVideoBitRateKb** 의 기본값은 5만 kbps입니다. 갤러리 보기에 대 한 **EnableMultiviewJoin** 설정이 True로 설정 되어 있으면 **TotalReceiveVideoBitRateKb** 420 kbps 미만으로 설정 되지 않아야 합니다. 갤러리 보기의 **EnableMultiviewJoin** 설정이 False로 설정 된 경우 **TotalReceiveVideoBitRateKb** 는 100 kbps 미만으로 설정 되지 않아야 합니다. **EnableMultiviewJoin** 가 True로 설정 되 고 420 kbps 미만으로 설정 되 면 값이 기본적으로 threshold 값이 됩니다. 이 임계값은 실수로 잘못 구성 되어 사용자 환경이 저하 될 수 있는 것을 방지 하는 데 도움이 됩니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>EnableMultiviewJoin</STRONG> 설정에 대 한 자세한 내용은 <A href="lync-server-2013-configuring-gallery-view.md">Lync Server 2013의 갤러리 보기 구성을</A>참조 하세요.

    
    </div>

  - **MaxVideoConferencingResolution**   이 매개 변수는 lync server 2013 컨퍼런스의 lync server 2013 클라이언트에 더 이상 사용 되지 않습니다. Lync Server 2013 컨퍼런스는이 섹션의 앞부분에서 설명한 비트 전송률 컨트롤을 사용 합니다. 이 설정은 Lync Server 2013 컨퍼런스에 참가 하는 레거시 클라이언트에도 계속 사용 됩니다. 이 매개 변수는 Lync Server 2013에 있는 사용자가 구성한 컨퍼런스에서 레거시 클라이언트에 허용 되는 최대 해상도를 결정 합니다. 즉, 레거시 클라이언트는 이전 버전의 Lync Server 또는 Office Communications Server와 동일 하 게 취급 됩니다.

사용자에 게 적용 되는 회의 정책 설정 외에 미디어 구성 설정을 평가 합니다. 다음 cmdlet 중 하나를 사용 하 여 이러한 설정을 보거나 수정 합니다.

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **새로운 CsMediaConfiguration**

다음 설정을 확인 합니다.

  - **MaxVideoRateAllowed**   이 설정에 따라 클라이언트 끝점에서 비디오 신호를 전송할 최대 속도를 지정 합니다. 이전 버전의 Lync Server 클라이언트에만 적용 됩니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 클라이언트는이 설정을 무시 하 고 대신 회의 정책에서 TotalReceiveVideoBitRateKb 설정을 사용 합니다.

    
    </div>
    
    기본 값은 HD720P입니다. 유효한 값은 HD720p15M, VGA600K 및 CIF250K입니다.
    
    예: 1500 kbps를 지정 하는 경우 풀의 모든 레거시 클라이언트는 두 사람이 나 단체 회의에서 최대 1500 kbps의 비디오를 받을 수 있습니다.

다음 절차에서는 Lync Server Management Shell을 사용 하 여이 섹션에서 설명 하는 설정을 수정 하는 예를 보여 줍니다.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>비디오 설정에 대 한 회의 정책을 수정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄에서 다음 cmdlet을 실행 하 여 회의 정책을 편집 합니다.
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>레거시 클라이언트에 대 한 미디어 구성을 수정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄에서 다음 cmdlet을 실행 하 여 미디어 구성을 편집 합니다.
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

