---
title: 'Lync Server 2013: 대역폭 정책 프로필 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1e44f7c8c0d81757d6d10a63194de7c0d12c08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013에서 대역폭 정책 프로필 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

*대역폭 정책*은 실시간 오디오 및 비디오 형식의 대역폭 사용량에 대한 제한을 정의하며, 통화 허용 제어에 대한 여러 네트워크 사이트에 적용할 수 있는 *대역폭 정책 프로필*에 적용됩니다.

CAC 배포에서 설정 해야 하는 대역폭 제한에 대 한 지침은 계획 설명서에서 [Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의](lync-server-2013-defining-your-requirements-for-call-admission-control.md) 를 참조 하십시오.

대역폭 정책 및 정책 프로필로 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Get-csnetworkbandwidthpolicyprofile을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

다음 절차에서 만들어진 예 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽 및 개별 비디오 세션에 대한 제한을 설정합니다. 예를 들어, 5Mb\_링크 대역폭 정책 프로필은 다음과 같은 제한을 설정 합니다.

  - 오디오 제한: 2,000kbps

  - 오디오 세션 제한: 200kbps

  - 비디오 제한: 1,400kbps

  - 비디오 세션 제한: 700kbps

<div class=" ">


> [!NOTE]  
> 최소 오디오 세션 제한 값은 40kbps이며, 최소 비디오 세션 제한 값은 100kbps입니다.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>관리 셸을 사용하여 대역폭 정책 프로필을 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  만들려는 각 대역폭 정책 프로필에 대해 New-CsNetworkBandwidthPolicyProfile cmdlet을 실행합니다. 예를 들어 다음을 실행합니다.
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용하여 대역폭 정책 프로필을 만들려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **정책 프로필** 탐색 단추를 클릭합니다.

4.  **새로 만들기**를 클릭합니다.

5.  **새 프로필 정책** 페이지에서 **이름**을 클릭한 후 대역폭 정책 프로필에 대한 이름을 입력합니다.

6.  **오디오 제한**을 클릭하고 결합된 모든 오디오 세션에 허용할 최대 kbps를 입력합니다.

7.  **오디오 세션 제한**을 클릭하고 각 개별 오디오 세션에 허용할 최대 kbps를 입력합니다.

8.  **비디오 제한**을 클릭하고 결합된 모든 비디오 세션에 허용할 최대 kbps를 입력합니다.

9.  **비디오 세션 제한**을 클릭하고 각 개별 비디오 세션에 허용할 최대 kbps를 입력합니다.

10. 경우에 따라 **설명**을 클릭하고 이 대역폭 정책 프로필을 설명하는 추가 정보를 입력합니다.

11. **커밋**을 클릭합니다.

12. 토폴로지에 대한 대역폭 정책 프로필 만들기를 종료하려면 다른 대역폭 정책 프로필에 대한 설정을 사용하여 4-11단계를 반복합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

