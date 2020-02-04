---
title: Lync Server 2013 회의의 구성 요소 및 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의의 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-04_

토폴로지 작성기에서 회의를 선택 하면 회의가 프런트 엔드 서버 또는 Standard Edition 서버의 일부로 배포 됩니다. 전화 접속 회의 및 PowerPoint 공유에는 추가 구성 요소 및 구성이 필요 합니다. 다음 섹션에서는 웹 회의, A/V 회의 및 전화 접속 회의에 지원 되는 구성 요소와 토폴로지에 대해 설명 합니다.

<div>

## <a name="supported-components"></a>지원 되는 구성 요소

유일한 구성 요소인 웹 회의와 A/V 회의는 조직의 프런트 엔드 서버 또는 Standard Edition 서버입니다. 프런트 엔드 서버 및 Standard Edition 서버에 대 한 하드웨어 및 소프트웨어 요구 사항 목록은 lync server [2013의 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 및 [lync Server 2013의 서버 소프트웨어 및 인프라 지원을](lync-server-2013-server-software-and-infrastructure-support.md)참조 하세요.

Lync Server 2013는 Office Web Apps 및 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

전화 접속 회의는 웹 회의와 A/V 회의에 대 한 요구 사항 외에도 다음과 같은 Lync Server 2013 구성 요소를 사용 합니다.

  - **응용 프로그램 서비스**   응용 프로그램 서비스는 통합 커뮤니케이션 (UC) 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다. 전화 접속 회의는 응용 프로그램 서비스가 필요한 두 개의 UC 응용 프로그램 (회의 수행자 및 회의 알림)을 사용 합니다. 응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 사용자가 회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 모든 Standard Edition 서버에 기본적으로 설치 및 활성화 됩니다.

  - **회의 수행자 응용**   프로그램 회의 수행자 응용 프로그램은 공용 전환 통신 네트워크 (PSTN) 통화를 수락 하 고, 메시지를 재생 하 고, 전화를 a/V 회의에 연결 하는 통합 커뮤니케이션 응용 프로그램입니다. 회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 수행자 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다.

  - **회의 알림**   응용 프로그램 회의 알림 응용 프로그램은 참가자가 회의에 참가 하거나 탈퇴할 때, 참가자가 음소거 또는 음소거 됨 경우, 다른 사용자가 컨퍼런스 로비에 들어가거나 회의가 잠겨 있거나 잠금이 해제 되는 등의 특정 작업을 수행 하는 통합 커뮤니케이션 응용 프로그램입니다. 회의 알림 응용 프로그램은 또한 휴대폰 키패드의 DTMF (multifrequency) 명령을 지원 합니다. 회의 작업 부하를 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 알림 응용 프로그램이 기본적으로 자동으로 설치 되 고 활성화 됩니다.

  - **전화 접속 회의 설정 페이지**   전화 접속 회의 설정 페이지에 사용 가능한 언어와 전화 회의 전화 접속 번호가 표시 되 고, 회의 정보 (예약할 필요가 없는 모임의 경우), 전화 회의 DTMF 컨트롤 및 PIN (개인 식별 번호) 및 지정 된 회의 정보 관리를 지원 합니다. 전화 접속 회의 설정 페이지는 웹 서비스의 일부로 자동으로 설치 됩니다.

  - **Lync server 2013, 중재 서버 및 pstn 게이트웨이**   전화 회의에는 lync server 2013와 pstn 게이트웨이 간의 신호 (및 미디어)를 변환 하는 조정 서버가 필요 하며, 조정 서버와 pstn 게이트웨이 간에 신호 및 미디어를 번역 하는 PSTN 게이트웨이를 사용 해야 합니다. 전화 접속 회의의 경우 하나 이상의 중재 서버와 다음 중 하나 이상을 배포 해야 합니다.
    
      - PSTN 게이트웨이
    
      - IP-PBX
    
      - SBC (세션 경계 컨트롤러) (SIP 트렁크 구성으로 연결 되는 인터넷 전화 통신 서비스 공급자의 경우)
    
    <div>
    

    > [!NOTE]  
    > 또한 엔터프라이즈 음성을 배포 하는 경우 중재 서버 및 PSTN 게이트웨이는 엔터프라이즈 음성 배포의 일부입니다. 엔터프라이즈 음성을 배포 하지 않는 경우에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이, IP-PBX 또는 전화 접속 회의를 위한 SBC를 배포 해야 합니다.

    
    </div>

  - **파일 저장소**   파일 저장소는 기록 된 이름 오디오 파일에 사용 됩니다. 파일 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포의 표준 구성 요소입니다.

  - **사용자 스토어**   사용자 저장소는 사용자 Lync Server 2013 pin을 저장 하는 데 사용 됩니다. 핀이 해시 됩니다. 사용자 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포의 표준 구성 요소입니다.

  - **Lync server 제어판**   일부 전화 접속 설정은 lync server 제어판을 사용 하 여 구성할 수 있습니다.

  - **Lync server 관리 셸**   모든 전화 접속 설정은 Lync server management shell cmdlet을 사용 하 여 구성할 수 있습니다. Lync Server 관리 셸 cmdlet은 회의 수행자 응용 프로그램 및 회의 알림 신청 배포, 구성, 실행, 모니터링, 문제 해결에 사용할 수 있습니다. 특정 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

</div>

<div>

## <a name="supported-topologies"></a>지원 되는 토폴로지

Lync Server 2013에서 회의 서비스를 실행 하는 서버는 항상 프런트 엔드 서버 또는 Standard Edition 서버와 collocated 됩니다. 초기 배포 중에 토폴로지 작성기는 토폴로지에 회의를 포함 하는 옵션을 제공 합니다. 토폴로지 작성기를 사용 하 여 기존 배포에 회의를 추가할 수도 있습니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.

<div>

## <a name="dial-in-conferencing-toplogies"></a>전화 회의 Toplogies

전화 접속 회의는 다음 토폴로지와 구성으로 배포할 수 있습니다.

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - 기업 음성이 있거나 없는 경우

중앙 사이트에는 응용 프로그램 서비스, 회의 수행자 응용 프로그램, 회의 알림 응용 프로그램을 배포할 수 있지만 분기 사이트에 있는 것은 아닙니다.

<div>


> [!NOTE]  
> 전화 접속 회의를 배포 하는 경우 Lync Server 2013 회의를 배포 하는 모든 풀에 배포 해야 합니다. 모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포 해야 합니다. 이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀의 Lync Server 2013 컨퍼런스에 참가 하는 경우 기록 된 이름 기능을 지원 합니다.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 및 Office Web Apps에서 지원 되는 토폴로지

Lync Server 2013에서는 다음과 같은 방법으로 Office Web Apps 서버를 구성할 수 있습니다. 필요 사항에 따라 다음을 수행할 수 있습니다.

  - **조직의 방화벽 및 동일한 네트워크 영역에 Lync Server 2013 및 Office Web Apps 서버를 모두 설치 합니다.** 이 토폴로지에서는 역방향 프록시 서버를 통해 Office Web Apps 서버에 대 한 외부 액세스가 제공 됩니다. Lync Server 2013과 Office Web apps 서버 (또는 Office Web Apps 서버 팜)는 모두 온-프레미스와 조직의 방화벽 뒤에 설치 됩니다. Lync Server와 동일한 네트워크 영역에 Office Web Apps 서버를 설치 하는 것이 가장 좋습니다.
    
    외부 Lync 클라이언트는 인터넷에서 요청을 받아서 내부 네트워크에 전달 하는 서버 인 리버스 프록시 서버를 사용 하 여 Lync Server 2013 및 Office Web Apps 서버에 연결할 수 있습니다. (내부 클라이언트는 Office Web Apps 서버에 직접 연결할 수 있기 때문에 역방향 프록시 서버를 사용할 필요가 없습니다.) 이 토폴로지는 Lync Server 2013에서 사용 하는 전용 Office Web Apps 서버 팜을 사용 하려는 경우에 가장 적합 합니다.

  - **외부에서 배포 된 Office Web Apps 서버 사용**
    
    이 토폴로지에서는 Lync Server 2013를 온-프레미스에 배포 하 고 Lync Server 네트워크 영역 외부에 배포 된 Office Web Apps 서버를 사용 합니다. 이 문제는 Office Web Apps 서버를 회사의 여러 응용 프로그램에서 공유 하 고 Lync Server에서 Office Web Apps 서버의 외부 인터페이스를 사용 하 고 그 반대의 경우를 위해 네트워크에 배포 하는 경우에 발생할 수 있습니다.
    
    역방향 프록시 서버를 설치할 필요는 없습니다. 대신, Office Web Apps 서버에서 Lync Server 2013 까지의 모든 요청이 Edge 서버를 통해 라우팅됩니다. 내부 및 외부 Lync 클라이언트 모두 외부 URL을 사용 하 여 Office Web Apps 서버에 연결 합니다.
    
    Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버가 토폴로지 작성기에서 외부 네트워크 (즉, 외곽/인터넷)에 배포 됨** 옵션을 선택 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

선택 하는 토폴로지에 관계 없이 올바른 방화벽 포트를 열어야 하는 것이 중요 합니다. Office Web Apps 서버, 부하 분산 장치 또는 Lync 서버의 방화벽에서 DNS 이름, IP 주소 및 포트가 차단 되지 않았는지 확인 해야 합니다.

<div>


> [!NOTE]  
> Office Web Apps 서버에 대 한 외부 액세스를 제공 하는 또 다른 옵션은 주변 네트워크에 서버를 배포 하는 것입니다. 이 작업을 수행 하는 경우 Office Web Apps 서버를 설치 하려면 서버 컴퓨터가 Active Directory 도메인의 구성원 이어야 한다는 점에 유의 하세요. 네트워크 정책에서 주변 네트워크의 컴퓨터를 Active Directory 도메인 구성원으로 사용할 수 있도록 허용 하지 않는 한 주변 네트워크에 Office Web Apps 서버를 설치 하지 않는 것이 좋습니다. 대신 내부 네트워크에 Office Web Apps 서버를 설치 하 고 리버스 프록시 서버를 통해 외부 사용자 액세스를 제공 해야 합니다.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

