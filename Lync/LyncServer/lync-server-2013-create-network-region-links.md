---
title: 'Lync Server 2013: 네트워크 지역 링크 만들기'
description: 'Lync Server 2013: 네트워크 지역 링크를 만듭니다.'
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
ms.openlocfilehash: 6510d252ac1534a3a8e9f14d56acc8d0d8b60a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553944"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 링크 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

네트워크 내의 지역은 실제 WAN 연결을 통해 연결됩니다. *네트워크 지역 링크*는 CAC(통화 허용 제어)에 대해 구성된 두 개의 지역 간 링크를 만들며, 이 지역 간 오디오 및 비디오 트래픽에 대한 대역폭 제한을 설정합니다.

네트워크 지역 링크 작업에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [새-Csnetwork지역 링크](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-Csnetwork지역 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [설정-Csnetwork지역 링크](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [-Csnetwork지역 링크 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

이 토폴로지 예에는 북미와 APAC 지역 간 링크 및 EMEA와 APAC 지역 간 링크가 포함됩니다. 이러한 각 지역 링크는 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 섹션의 지역 링크 대역폭 정보 표에서 설명 하는 대로 WAN 대역폭에 따라 제한 됩니다.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Lync Server 관리 셸을 사용하여 네트워크 지역 링크를 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  New-CsNetworkRegionLink cmdlet를 실행하여 지역 링크를 만들고 적합한 대역폭 정책 프로필을 적용합니다. 예를 들어 다음을 실행합니다.
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용하여 네트워크 지역 링크를 만들려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **지역 링크** 탐색 단추를 클릭합니다.

4.  **새로 만들기**를 클릭합니다.

5.  **새 지역 링크** 페이지에서 **이름**을 클릭하고 네트워크 지역 링크에 대한 이름을 입력합니다.

6.  **네트워크 지역 \# 1**을 클릭 하 고 목록에서 네트워크 지역 2에 연결할 네트워크 지역을 클릭 \# 합니다.

7.  **네트워크 지역 \# 2**를 클릭 하 고 목록에서 네트워크 지역 1에 연결할 네트워크 지역을 클릭 \# 합니다.

8.  (선택 사항) **대역폭 정책**을 클릭하고 네트워크 지역 링크에 적용할 대역폭 정책 프로필을 선택합니다.
    
    <div class=" ">
    

    > [!NOTE]  
    > 네트워크 지역 링크에 대역폭 제한이 있고 CAC를 사용하여 해당 링크에 대해 미디어 트래픽을 제어할 경우에만 대역폭 정책을 적용합니다.

    
    </div>

9.  **커밋**을 클릭합니다.

10. 토폴로지에 대한 네트워크 지역 링크 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-9단계를 반복합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>
