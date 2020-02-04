---
title: 'Lync Server 2013: 네트워크 지역 링크 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40b9d569cbc571fe931a53b6f399b6273efd055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 링크 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

네트워크 내의 영역은 실제 WAN 연결을 통해 연결 됩니다. *네트워크 지역 링크* 는 CAC (호출 허용 제어)에 대해 구성 된 두 지역 간에 링크를 만들고 이러한 지역 간의 오디오 및 비디오 트래픽에 대 한 대역폭 제한을 설정 합니다.

네트워크 지역 링크 작업에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [-Csnetwork국가 링크 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

이 예제 토폴로지에는 북미와 APAC 지역 간의 링크와 EMEA와 APAC 지역 간의 링크가 있습니다. 이러한 지역 링크는 다음 예의 지역 링크 대역폭 정보 표에 설명 된 대로 WAN 대역폭에 따라 제한 되며, 계획 설명서의 [Lync Server 2013 섹션에서 통화 허용 제어에 대 한 요구 사항을 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 합니다.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 네트워크 지역 링크를 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새-Csnetworkregion 링크 cmdlet을 실행 하 여 지역 링크를 만들고 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 지역 링크를 만들려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **지역 링크** 탐색 단추를 클릭 합니다.

4.  **새로 만들기**를 클릭 합니다.

5.  **새 지역 링크** 페이지에서 **이름을** 클릭 한 다음 네트워크 지역 링크의 이름을 입력 합니다.

6.  **네트워크 지역 \#1**을 클릭 한 다음 목록에서 네트워크 지역 \#2에 연결할 네트워크 지역을 클릭 합니다.

7.  **네트워크 지역 \#2**를 클릭 한 다음 목록에서 네트워크 지역 \#1에 연결할 네트워크 지역을 클릭 합니다.

8.  필요에 따라 **대역폭 정책을**클릭 한 다음 네트워크 지역 링크에 적용 하려는 대역폭 정책 프로필을 선택 합니다.
    
    <div class=" ">
    

    > [!NOTE]  
    > 네트워크 지역 링크에 대역폭이 제한 되어 있고 CAC를 사용 하 여 해당 링크의 미디어 트래픽을 제어 하려는 경우에만 대역폭 정책을 적용 합니다.

    
    </div>

9.  **커밋**을 클릭합니다.

10. 토폴로지에 대 한 네트워크 지역 링크 만들기를 마치려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>
