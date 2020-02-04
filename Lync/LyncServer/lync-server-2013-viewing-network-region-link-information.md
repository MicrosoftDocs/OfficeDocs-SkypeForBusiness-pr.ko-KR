---
title: 'Lync Server 2013: 네트워크 지역 링크 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 링크 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

호출 허용 제어 (CAC)의 일부로 두 네트워크 지역 간 링크를 볼 수 있습니다. 네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다. Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다. 네트워크 지역 링크를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 구성을](lync-server-2013-configuring-network-region-links.md)참조 하세요.

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Lync Server 제어판에서 네트워크 지역 링크를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 보려는 지역 링크를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 하나의 지역 링크에 대 한 정보만 볼 수 있습니다.

    
    </div>

5.  **편집** 메뉴에서 **세부 정보 표시**를 선택 합니다.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 네트워크 지역 링크 정보 보기

Windows PowerShell 및 **Get-Csnetworkregion 링크** cmdlet을 사용 하 여 네트워크 지역 링크를 볼 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-network-region-link-information"></a>네트워크 지역 링크 정보를 보려면

  - 모든 네트워크 지역 링크에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkRegionLink
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

자세한 내용은 [Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 사이트 링크 구성](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

