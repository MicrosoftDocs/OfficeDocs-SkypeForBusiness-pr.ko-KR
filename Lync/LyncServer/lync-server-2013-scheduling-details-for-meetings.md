---
title: 'Lync Server 2013: 모임 일정 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Lync Server 2013의 모임에 대 한 일정 세부 정보

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

요청한 시간에 다른 모임이 예약 되어 있지 않은지 확인 한 후, 요청을 처리 하는 대규모 모임 지원 직원이 대용량 모임 풀에서 모임을 예약 합니다. Lync Server 2013 클라이언트에 설치 된 Lync 용 온라인 모임 추가 기능을 사용 하 여 전용 대용량 모임 풀에서 Lync Server에 대해 사용 하도록 설정 된 사용자의 자격 증명을 사용 하 여이 작업을 수행 합니다.

최상의 사용자 환경을 위해서는 모임 이끌이의 요구에 적합 한 적절 한 액세스 수준 및 모임 설정을 사용 하 여 대규모 모임을 예약 하는 것이 중요 합니다. Lync 모임 옵션에서 다음 일정 설정을 구성 하는 것이 좋습니다.

  - 전용 모임 공간을 다시 사용 하는 대신 각 대용량 모임에 대해 새 모임 공간을 사용 합니다.

  - 다음과 같이 모임 액세스 수준을 지정 합니다.
    
      - 하나 이상의 초대 대 상자가 조직의 외부에 있는 경우 모임 액세스 형식을 **모든 사용자 (제한 없음)** 로 설정 합니다. 이를 통해 모임이 진행 중일 때 잠재적으로 큰 로비를 관리 하지 않아도 됩니다.
    
      - 모임이 내부 전용 모임이 면 모임 액세스 형식을 **조직의 모든 사용자**에 게 설정 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 설정을 사용 하는 경우 이끌이는 초대 목록에 모든 사용자 전자 메일 주소를 추가 해야 하 고 메일 그룹을 초대할 수 없기 때문에 <STRONG>회사에서 초대한 사람</STRONG> 에 게 모임 액세스 형식을 설정 하지 마세요.<BR>모임 액세스 형식을 <STRONG>나</STRONG> 자신만으로 설정 하지 마세요 .이 설정을 사용 하려면 발표자를 비롯 한 모든 모임 참가자가 모임 런타임에 대기실에 놓아야 합니다. 대용량 모임 실행을 담당 하는 사람은 로비 명단을 지속적으로 모니터링 하 고 대기실에 있는 새 사용자를 참가 시켜야 합니다.

        
        </div>

  - 전화 접속을 하는 사용자가 전화를 건 사람에 게 **직접 액세스** 를 확인 하 여 모임에 자동으로 들어갈 수 있도록 합니다.

  - 다음 사용자를 명시적으로 초대:
    
      - 모임 이끌이 및 대리인 (요청자)
    
      - 모임 요청 자가 제공 하는 발표자 목록
    
    <div>
    

    > [!NOTE]  
    > 모임 액세스 형식이 <STRONG>선택한 사람</STRONG>으로 설정 된 경우에는 대규모 모임의 각 참가자를 모임의 초대 대 상자를 명시적으로 추가 해야 합니다.

    
    </div>

  - 발표자 옵션을 자동 승격 값 중 하나로 설정 하는 대신 발표자를 명시적으로 관리 합니다. 다음 사용자를 발표자로 추가 해야 합니다.
    
      - 모임 이끌이 및 대리인 (요청자)
    
      - 대규모 모임 요청자에서 제공 하는 발표자 목록
    
    <div>
    

    > [!NOTE]  
    > 발표자를 명시적으로 관리 하 여 발표자 수를 제어 하 여 효율적인 대규모 모임이 가능 하도록 하기에 충분 한 수의 번호로 발표자를 제한할 수 있습니다. 대부분의 모임 참가자가 참석자 역할을 보유 하 고 있는 경우 사용자가 프레젠테이션을 제어할 수 있는 기회, PowerPoint 프레젠테이션 삭제, 음소거/음소거 해제, 모임에 대 한 기타 작업 중단을 줄이는 데 도움이 됩니다.

    
    </div>

  - **모든 참석자 음소거** 설정을 확인 하 여 발표자만 오디오를 모임에 브로드캐스트할 수 있도록 합니다.

  - 참석자의 **비디오** 설정을 확인 하 여 발표자만 모임에 비디오를 브로드캐스트할 수 있도록 합니다.

다음 그림에는 Lync 용 온라인 모임 추가 기능에 대 한 권장 설정이 나와 있습니다.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

