---
title: 'Lync Server 2013: 대역폭 정책 프로필 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다. Microsoft Lync Server 2013에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다. 다음 절차를 사용 하 여 대역폭 정책 프로필을 만들거나 수정 합니다. 대역폭 정책 프로필을 삭제 하려면 [Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제](lync-server-2013-deleting-network-bandwidth-policy-profiles.md) 를 참조 하세요.

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>새 대역폭 정책 프로필을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 대역폭 정책 프로필**의 **이름** 필드에 이름을 입력 합니다. 이 이름은 모든 대역폭 정책 프로필에서 고유 해야 합니다.

6.  **오디오 제한** 필드에 숫자 값을 입력 합니다. 이 값은 모든 오디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps로 표시 됨)입니다.

7.  **오디오 세션 제한** 필드에 숫자 값을 입력 합니다. 이 값은 kbps로 표시 되는 개별 오디오 연결에 할당할 수 있는 대역폭의 최대 양입니다. 이 값은 40 이상 이어야 합니다.

8.  **비디오 제한** 필드에 숫자 값을 입력 합니다. 이 값은 모든 비디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps)입니다.

9.  **비디오 세션 제한** 필드에 숫자 값을 입력 합니다. 이 값은 kbps로 표시 되는 개별 비디오 연결에 할당할 수 있는 대역폭의 최대 양입니다. 이 값은 100 이상 이어야 합니다.

10. ) 이름 만으로 표현할 수 없는이 대역폭 정책 프로필에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

11. **커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 새 대역폭 정책 프로필을 만들면 자동으로 대역폭 제한이 적용 되지는 않습니다. 먼저 정책 프로필을 사이트와 연결 해야 합니다. 사이트에 정책 프로필을 연결 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 수정 하려는 대역폭 정책 프로필을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **대역폭 정책 프로필 편집** 페이지에서 필요에 따라 필드를 수정 합니다 (자세한 내용은이 항목의 앞부분에 나오는 "대역폭 정책 프로필 만들기" 섹션을 참조 하세요.).

7.  **커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 대역폭 정책 프로필을 수정 하면이 대역폭 정책 프로필에 연결 된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트 됩니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)  
[새로운 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

