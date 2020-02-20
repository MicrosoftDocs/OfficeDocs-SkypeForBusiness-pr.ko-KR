---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 설정 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bff47410f46516061a5a3be64bce17476b453e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>반드시 Lync Server 2013에서 전화 접속 회의 설정 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2010-11-02_

전화 접속 회의 구성의 최종 확인 작업으로 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜 및 전화 접속 회의 지역이 할당되지 않은 액세스 번호를 검색할 수 있습니다. 이 단계는 선택 사항입니다.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜을 찾으려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    이 cmdlet은 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 모든 다이얼 플랜을 반환합니다.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>지역이 할당되지 않은 액세스 번호를 찾으려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    이 cmdlet은 지역과 연관되지 않은 모든 전화 접속 회의 액세스 번호를 반환합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

