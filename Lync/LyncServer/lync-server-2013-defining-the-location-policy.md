---
title: 'Lync Server 2013: 위치 정책 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Lync Server 2013의 위치 정책 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

각 위치 정책에는 다음 정보가 포함 됩니다.

  - **응급 서비스 사용**  
    이 값이 **Yes**인 경우 클라이언트는 E9-1-1에 대해 설정 됩니다. 클라이언트가 등록 되 면 위치 정보 서비스에서 위치를 얻으려고 시도 하 고 비상 전화의 일부로 위치 정보를 포함 하 게 됩니다.

<!-- end list -->

  - **위치 필요**  
    이 설정은 **Emergence 서비스 사용** 이 **Yes**로 설정 된 경우에만 사용 됩니다.
    
    **위치** 설정을 구성 하 여 클라이언트 동작을 정의할 수 있습니다. 값을 **No** 로 설정 하면 사용자에 게 위치를 묻지 않는다는 의미입니다. 값을 **예/y e s** 로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되지만 메시지가 해제 될 수 있습니다. 값을 고로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되 **고, 프롬프트** 를 해제 하려고 할 경우에도 고 지 사항이 표시 됩니다. 모든 경우에 사용자는 계속 해 서 클라이언트를 사용할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > E9-1-1에 대해 사용 하도록 설정 하기 전에 사용자가 수동으로 위치를 입력 한 경우에는 고 지 사항 텍스트가 표시 되지 않습니다. 부인 내용에 대 한 업데이트는 이미 고 지를 본 사용자가 볼 수 없습니다.

    
    </div>

<!-- end list -->

  - **향상 된 응급 서비스 책임의 부인**  
    이 설정은 위치에 대 한 프롬프트를 해제할 때 사용자에 게 표시 되는 부인 여부를 지정 합니다. Lync Server 2013에서 위치 정책을 사용 하 여 다양 한 로캘 또는 사용자 집합에 대해 다른 법적 고 지를 설정할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 이 위치 정책 설정은 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet을 사용 하 여 전체 조직에 대 한 전역 고 지 사항을 설정한 Lync Server 2010와 다릅니다. 전역 부인 내용이 이미 있는 경우에는 위치 정책에서 부인를 지정 해야 합니다. 즉, Lync 서버 2013는 위치 정책에 지정 된 부인만 사용 합니다.

    
    </div>

<!-- end list -->

  - **비상 다이얼 문자열**  
    이 다이얼 문자열 (선행 "+"는 제외 하 고 Lync 사용자의 다이얼 플랜에서 표준화를 포함 하 여)는 통화가 비상 통화 임을 나타냅니다. **비상 다이얼 문자열** 을 사용 하면 클라이언트는 전화와 함께 위치 및 콜백 정보를 포함 합니다.
    
    <div>
    

    > [!NOTE]  
    > 조직에서 외부 회선 액세스 접두사를 사용 하지 않는 경우에는 Lync 풀 서버의 아웃 바운드 라우팅에 대 한 통화를 전송 하기 전에 911 문자열에 "+"를 추가 하는 해당 다이얼 플랜 정규화 규칙을 만들 필요가 없습니다. 위치 정책의 결과로 Lync 클라이언트에서 "+"가 자동으로 앞에 놓이게 됩니다. 그러나 사이트에서 외부 액세스 접두사를 사용 하는 경우 외부 액세스 접두사를 제거 하 고 "+"를 추가 하는 해당 다이얼 플랜 정책에 정규화 규칙을 추가 해야 합니다. 예를 들어 위치에 외부 액세스 접두사 9를 사용 하는 경우 사용자가 9&nbsp;911로 비상 전화를 걸고 있으면 클라이언트는 전화 걸기 계획 정책을 사용 하 여 전화를 건 사람의 위치 프로필에 있는 경로에 따라이 번호를 + 911로 정규화 합니다.

    
    </div>

<!-- end list -->

  - **응급 전화 접속 문자열 마스크**  
    지정 된 **긴급 전화 걸기 문자열로**번역 된 다이얼 문자열의 세미콜론으로 구분 된 목록입니다. 예를 들어 대부분의 유럽에 대 한 응급 서비스 번호로 112를 추가할 수 있습니다. 유럽의 Lync 사용자 방문에 911는 미국 비상 전화 번호로 인식 하지 못할 수 있지만, 112를 사용 하 여 동일한 결과를 얻을 수 있습니다. 비상 다이얼 문자열의 경우 각 번호 앞에 "+"를 포함 하지 않으며, 외부 회선 액세스 코드를 사용 하는 경우 사용자의 다이얼 플랜 정책에 정규화 규칙이 있어야 access 코드 자릿수를 제거할 수 있습니다.

<!-- end list -->

  - **PSTN 사용 현황**  
    게이트웨이 비상 전화의 SIP 트렁크, PSTN 게이트웨이 또는 ELIN 결정 하는 라우팅 경로를 포함 하는 PSTN 사용의 이름으로 이동 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 위치 정책에는 하나의 사용만 할당할 수 있습니다. 이 PSTN 사용은 사용자의 음성 정책에 할당 된 PSTN 사용량 보다 우선 하지만 비상 다이얼 문자열 또는 비상 다이얼 문자열 마스크 중 하나에 대 한 통화에만 적용 됩니다.

    
    </div>

<!-- end list -->

  - **알림 URI**  
    긴급 통화를 할 때 IM (인스턴트 메시징) 알림을 받는 보안 인력의 하나 이상의 SIP Uri를 지정 합니다. 배포 그룹이 지원 됩니다.

<!-- end list -->

  - **컨퍼런스 URI**  
    비상 전화를 걸 때 conferenced 되는 직접적인 안쪽 전화 걸기 (연결 된) 번호 (일반적으로 보안 데스크 번호)를 지정 합니다.

<!-- end list -->

  - **컨퍼런스 모드**  
    회의 URI가 단방향 또는 양방향 통신을 사용 하 여 긴급 통화에 conferenced 여부를 지정 합니다.

<!-- end list -->

  - **위치 새로 고침 간격**  
    위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 사이의 시간 (시간)을 지정 합니다. 값을 1에서 12 사이의 값으로 설정할 수 있습니다. 기본값은 4입니다.

</div>

<span> </span>

</div>

</div>

</div>

