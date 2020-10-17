---
title: 'Lync Server 2013: 원격 통화 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99cf4d98f02554e7de344ded843b60406e755a3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526455"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013의 원격 통화 제어 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-05_

Lync Server 2013에서 원격 통화 제어 시나리오를 지원 하면 사용자가 데스크톱 컴퓨터에서 Lync 2013을 사용 하 여 PBX (private branch exchange) 전화를 제어할 수 있습니다. 이 섹션에서는 원격 통화 제어 기능을 배포 하는 데 필요한 원격 통화 제어 기능과 요구 사항에 대해 설명 합니다.

PBX와 Lync Server 2013 간 통합을 사용 하면 원격 통화 제어를 사용 하도록 설정 된 사용자가 Lync 2013 UI (사용자 인터페이스)를 통해 다음과 같은 방식으로 PBX 전화에서 통화를 제어할 수 있습니다.

<div>


> [!NOTE]  
> 궁극적으로 사용자의 PBX 전화를 호스팅하는 PBX의 기능에 따라 해당 사용자에 게 제공 되는 원격 통화 제어 기능이 결정 됩니다.



</div>

  - 발신 전화 만들기

  - 수신 전화에 응답

  - 인스턴트 메시지로 수신 전화에 응답
    
    <div>
    

    > [!NOTE]  
    > 즉, 발신자의 전화 번호를 조직의 GAL (전체 주소 목록)에 있는 인스턴트 메시지 주소 (수신자의 Lync 대화 상대 목록 또는 페더레이션 파트너의 조직)에 연결할 수 있습니다.

    
    </div>

  - 통화 전송

  - 수신 전화 전달

  - 통화 대기

  - 여러 동시 통화 간 전환

  - 통화 중에 두 번째 전화 받기 (통화 대기)

  - DTMF (이중 톤 dual-tone multifrequency) 자리 다이얼

  - 대화 창에서 Microsoft Office OneNote 노트 기록 프로그램에 메모를 입력 합니다.

또한 사용자가 원격 통화 제어를 사용 하도록 설정 된 경우 Lync 2013에서는 다음 통화 정보를 사용자에 게 제공 합니다.

  - 발신자의 전화 번호가 원격 통화 제어 사용 사용자의 Microsoft Office Outlook 메시징 및 공동 작업 클라이언트, Lync 연락처 목록 또는 조직의 GAL에 대 한 대화 상대 목록에 있는 경우 이름별로 발신자의 id입니다.

  - Outlook의 대화 내용 폴더에 저장 되는 이전의 수신 및 발신 전화

  - 부재 중 전화 알림-사용자의 Outlook 받은 편지함 폴더로 보내지며, 수신 전화를 받으면 Lync가 실행 되는 경우에만 생성 됩니다.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>원격 통화 제어 및 Enterprise Voice

원격 통화 제어 기능은 Enterprise Voice 기능과 구분 되지만 사용자를 둘 다에 대해 사용 하도록 설정할 수는 없지만 Enterprise Voice에서는 원격 통화 제어를 사용 하도록 설정 된 사용자도 사용할 수 있는 기능 하위 집합을 제공 합니다. Enterprise Voice를 배포 하는 경우 원격 통화 제어를 사용 하도록 설정 된 사용자는 Lync를 사용 하 여 다음 Enterprise Voice 기능에 액세스할 수 있습니다.

  - 다른 Lync 클라이언트에 대 한 음성 통화 만들기 및 수신

  - Enterprise Voice를 사용 하도록 설정 된 사용자가 만든 회의의 오디오 부분에 참가

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 원격 통화 제어에 대 한 배포 작업](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

