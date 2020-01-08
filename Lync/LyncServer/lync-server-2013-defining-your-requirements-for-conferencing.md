---
title: 'Lync Server 2013: 회의 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60193673efff29ec877626a9c5c18be23507e6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 회의 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

배포할 회의 기능을 결정 하는 경우 사용자와 네트워크 대역폭 기능에 사용할 수 있는 기능을 고려해 야 합니다. 다음 질문 목록은 조직의 요구 사항에 따라 배포 해야 하는 회의 기능을 결정 하는 회의 계획 프로세스를 안내 합니다.

  - **문서 공동 작업 및 응용 프로그램 공유를 포함 하는 웹 회의를 사용 하도록 설정 하 시겠습니까?**
    
    이 경우 Microsoft Lync Server 2013, 계획 도구 또는 토폴로지 작성기에서 프런트 엔드 풀에 대해 회의를 사용 하도록 설정 해야 합니다. 회의를 사용 하도록 설정 하면 웹 회의와 A/V 회의를 모두 사용할 수 있습니다.
    
    응용 프로그램 공유에는 문서 공동 작업 보다 더 많은 네트워크 대역폭이 필요 합니다. Lync Server 2013에서는 각 응용 프로그램 공유 세션을 제어 하는 스로틀 메커니즘을 제공 합니다. 기본적으로 각 세션에 대해 1.5 KB/초로 설정 됩니다.
    
    응용 프로그램 공유를 사용 하지 않고 문서를 공동 작업을 수행 하려는 경우에는 회의를 사용 하도록 설정 하 고, 모임 정책을 사용 하 여 응용 프로그램 공유를 사용 하지 않도록 설정할 수 있습니다. 모임 정책 구성에 대 한 자세한 내용은 [Lync Server 2013의 회의 정책을](lync-server-2013-conferencing-policies.md)참조 하세요.
    
    사용자가 PowerPoint 프레젠테이션을 공유할 수 있도록 설정 하려면 Office Web Apps 서버를 구성 해야 합니다. Office Web Apps 서버를 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - **A/V 회의를 사용 하 고 싶으세요?**
    
    그렇다면 Lync Server 2013, 계획 도구 또는 토폴로지 작성기에서 프런트 엔드 풀에 대해 회의를 사용 하도록 설정 해야 합니다. 회의를 사용 하도록 설정 하면 웹 회의와 A/V 회의를 모두 사용할 수 있습니다.
    
    A/V 회의는 웹 회의 보다 더 많은 네트워크 대역폭 (문서 공동 작업 및 응용 프로그램 공유 포함)을 사용 해야 합니다. A/V 회의를 사용 하 고 있지 않지만 웹 회의를 사용 하도록 설정 하려는 경우에는 회의를 사용 하도록 설정 하 고 모임 정책을 사용 하 여 A/V 회의를 사용 하지 않도록 설정할 수 있습니다.
    
    오디오 회의를 사용 하도록 설정 하 고 비디오 회의를 할 수 없는 경우에는 A/V 회의를 사용 하도록 설정 하 고, 모임 정책을 사용 하 여 비디오 회의를 방지 하세요. 또는 A/V 회의를 사용 하도록 설정 하 고 특정 사용자만이 A/V 회의를 시작 하거나이에 참여 하도록 할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > A/V 회의를 사용 하는 데 엔터프라이즈 음성이 필요 하지는 않습니다. A/V 회의를 사용 하는 경우 사용자는 전화 솔루션에 PBX를 사용 하는 경우에도 오디오 장치가 있는 경우 해당 회의에 오디오를 추가할 수 있습니다.

    
    </div>

  - **PSTN 전화기를 사용할 때 사용자가 오디오 회의에 참가할 수 있도록 하 시겠습니까?**
    
    그렇다면 전화 접속 회의를 배포 하 고 사용 하도록 설정 합니다. 조직 내부와 외부 모두에서 초대 받은 사용자는 PSTN 전화기를 사용 하 여 오디오 부분을 회의에 참가할 수 있습니다.

  - **Lync Server 2013 클라이언트를 사용 하 여 외부 사용자가 사용 하도록 설정한 회의 유형에 참가할 수 있도록 하 시겠습니까?**
    
    그렇다면 Edge 서버를 배포 해야 합니다. 모임에서 외부 참여를 허용 하 여 Lync Server 2013에서 투자를 극대화할 수 있습니다. 예를 들어 Lync Server 2013를 사용 하는 랩톱 사용자는 집, 공항 또는 고객 사이트의 어디에서 나 회의에 참가할 수 있습니다.
    
    또한 Edge 서버를 배포한 경우 고객 또는 공급 업체와 같은 다른 조직과의 페더레이션 관계를 만들 수 있으며 이러한 조직의 사용자가 사용자와 보다 쉽게 공동 작업할 수 있습니다.
    
    Edge 서버 배포에 대 한 자세한 내용은 lync [server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참조 하세요. Office Web Apps 서버에서 외부 액세스를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [리버스 프록시 서버를 사용 하 여 Lync server 2013에서 Office Web Apps 서버 게시](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)를 참조 하세요.

  - **Lync Server 2013 모임에 참가할 수 있는 클라이언트를 제어 하 고 싶으신가요?**
    
    이 경우 지원 하려는 클라이언트 옵션만 사용할 수 있도록 모임 참가 페이지를 구성 해야 합니다. 사용자가 예약 된 모임에 참가 하기 위한 링크를 클릭할 때마다 Lync Server 2013에서 클라이언트가 이미 컴퓨터에 설치 되어 있는지 여부를 감지 합니다. 그런 다음 기본 클라이언트를 시작 하 고 대체 클라이언트에 대 한 링크가 포함 된 모임 참가 페이지를 엽니다. 모임 참가 페이지에는 항상 Microsoft Lync Web App을 사용 하는 옵션이 있습니다. 이 옵션 외에도 참석자와 이전 버전의 Communicator에 대 한 링크를 포함할지 여부를 결정할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 모임 참가 페이지 구성을](lync-server-2013-configuring-the-meeting-join-page.md)참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 웹 회의 요구 사항](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013의 A/V 회의 요구 사항](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013의 전화 접속 회의 요구 사항](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 회의 계획](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013의 회의에 대한 배포 검사 목록](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

