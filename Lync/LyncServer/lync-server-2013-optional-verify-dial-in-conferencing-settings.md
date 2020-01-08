---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 설정 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>(선택 사항) Lync Server 2013에서 전화 접속 회의 설정 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2010-11-02_

전화 접속 회의 구성을 최종적으로 확인 하면 전화 접속 회의 영역을 사용 하 여 액세스 번호와 전화 접속 회의 영역을 지정 하지 않은 액세스 번호를 검색 하는 다이얼 플랜을 검색할 수 있습니다. 이 단계는 선택 사항입니다.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>액세스 번호에서 사용 하지 않는 전화 접속 회의 영역을 사용 하 여 다이얼 플랜을 찾으려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음을 실행 합니다.
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    이 cmdlet은 액세스 번호에 사용 되지 않는 전화 접속 회의 영역이 있는 모든 다이얼 플랜을 반환 합니다.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>할당 된 지역이 없는 액세스 번호를 찾으려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음을 실행 합니다.
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    이 cmdlet은 지역과 연결 되지 않은 모든 전화 접속 회의 액세스 번호를 반환 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

