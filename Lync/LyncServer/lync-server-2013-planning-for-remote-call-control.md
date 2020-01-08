---
title: 'Lync Server 2013: 원격 통화 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013의 원격 통화 제어 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-05_

Lync Server 2013에서 원격 통화 제어 시나리오를 지원 하면 사용자가 데스크톱 컴퓨터에서 Lync 2013을 사용 하 여 개인 브랜치 교환 (PBX) 전화를 제어할 수 있습니다. 이 섹션에서는 원격 통화 제어 기능 및 원격 호출 제어를 배포 하기 위한 요구 사항에 대해 설명 합니다.

PBX와 Lync Server 2013를 통합 하면 사용자가 Lync 2013 UI (사용자 인터페이스)를 사용 하 여 다음과 같은 방법으로 PBX 전화기에 대 한 통화를 제어할 수 있도록 원격 통화 제어가 가능 합니다.

<div>


> [!NOTE]  
> 궁극적으로 사용자의 PBX 휴대폰을 호스팅하는 PBX의 기능은 해당 사용자에 게 제공 되는 원격 통화 제어 기능을 결정 합니다.



</div>

  - 발신 통화 만들기

  - 걸려오는 전화에 응답

  - 인스턴트 메시지로 걸려오는 전화에 응답
    
    <div>
    

    > [!NOTE]  
    > 즉, 호출자의 전화 번호를 조직의 GAL (전체 주소 목록)에 있는 인스턴트 메시지 주소, 피호출자의 Lync 대화 상대 목록 또는 페더레이션된 파트너의 조직에 연결할 수 있습니다.

    
    </div>

  - 통화 전송

  - 걸려오는 전화 전달

  - 통화를 대기 상태로 두기

  - 여러 동시 통화 간에 전환할 경우

  - 통화 중에 동시에 두 번째 전화 받기 (즉, 통화 대기)

  - 다이얼 multifrequency (DTMF) 숫자

  - 대화 창에서 Microsoft Office OneNote 노트 작성 프로그램에 노트 입력

또한 사용자가 원격 통화 제어권을 사용할 수 있는 경우 Lync 2013에서 사용자에 게 다음 통화 정보를 제공 합니다.

  - 발신자의 전화 번호가 원격 통화 제어를 사용 하는 사용자의 Microsoft Office Outlook 메시징 및 공동 작업 클라이언트, Lync 대화 상대 목록 또는 조직의 GAL에 대 한 연락처 목록에 있는 경우 이름으로 발신자를 식별 합니다.

  - Outlook의 대화 내용 폴더에 저장 된 이전의 수신 및 발신 통화

  - 부재 중 전화 알림-사용자의 Outlook 받은 편지함 폴더로 전송 되지만 수신 전화를 받았을 때 Lync가 실행 중인 경우에만 생성 됩니다.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>원격 통화 제어 및 엔터프라이즈 음성

원격 통화 제어 기능은 엔터프라이즈 음성 기능과 구분 되지만 사용자를 모두 사용할 수 있는 것은 아니지만 Enterprise Voice는 원격 통화 제어를 사용 하도록 설정 된 사용자도 사용할 수 있는 기능 하위 집합을 제공 합니다. 엔터프라이즈 음성이 배포 되는 경우 원격 통화 제어를 사용 하도록 설정 된 사용자는 Lync를 사용 하 여 다음 엔터프라이즈 음성 기능에 액세스할 수 있습니다.

  - 다른 Lync 클라이언트로 음성 통화 걸기 및 받기

  - 엔터프라이즈 음성 기능을 사용 하도록 설정 된 사용자가 만든 컨퍼런스 오디오 부분 참가

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 원격 통화 제어에 대한 배포 작업](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

