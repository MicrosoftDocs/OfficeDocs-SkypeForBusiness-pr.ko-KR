---
title: Lync Server 2013 회의의 구성 요소 및 토폴로지
description: Lync Server 2013 회의의 구성 요소 및 토폴로지
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
ms.openlocfilehash: 719fe81d0f634b1eab1e79c2e7e665e89b0a791a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576864"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의에 대 한 구성 요소 및 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-04_

토폴로지 작성기에서 회의를 선택 하면 회의가 프런트 엔드 서버 또는 Standard Edition 서버의 일부로 배포 됩니다. 전화 접속 회의 및 PowerPoint를 공유 하려면 추가 구성 요소와 구성을 수행 해야 합니다. 다음 섹션에서는 웹 회의, A/V 회의 및 전화 접속 회의에 지원 되는 구성 요소와 토폴로지에 대해 설명 합니다.

<div>

## <a name="supported-components"></a>지원되는 구성 요소

웹 회의 및 A/V 회의만 있으면 조직의 프런트 엔드 서버 또는 Standard Edition 서버를 구성 해야 합니다. 프런트 엔드 서버 및 Standard Edition 서버에 대 한 하드웨어 및 소프트웨어 요구 사항 목록은 lync server 2013의 Lync Server 2013 및 [서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.

Lync Server 2013에서는 Office Web Apps와 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 및 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

전화 접속 회의는 웹 회의 및 A/V 회의에 대 한 요구 사항 외에도 다음과 같은 Lync Server 2013 구성 요소를 사용 합니다.

  - **응용 프로그램 서비스**     응용 프로그램 서비스는 UC (통합 통신) 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다. 전화 접속 회의에서는 응용 프로그램 서비스가 필요한 두 개의 UC 응용 프로그램 (회의 전화 교환 및 회의 알림)을 사용 합니다. 회의 작업 부하를 배포하고 전화 접속 회의 옵션을 선택하면 프런트 엔드 풀의 모든 프런트 엔드 서버 및 모든 Standard Edition Server에서 응용 프로그램 서비스가 기본적으로 설치 및 활성화됩니다.

  - **회의 전화 교환 응용 프로그램**     회의 전화 교환 응용 프로그램은 공중 전화망 (PSTN) 통화를 허용 하 고, 음성 안내를 재생 하며, A/V 회의에 통화를 참가 시키는 통합 커뮤니케이션 응용 프로그램입니다. 회의 작업을 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 전화 교환 응용 프로그램은 기본적으로 설치 및 활성화 됩니다.

  - **회의 알림 응용 프로그램**     회의 알림 응용 프로그램은 참가자가 전화 회의에 참가 하거나 나갈 때, 참가자가 음소거 또는 음소거 해제 되었는지, 누군가 회의 로비에 들어가거나 전화 회의 잠김 또는 잠금 해제와 같은 특정 작업을 수행 하는 통합 커뮤니케이션 응용 프로그램입니다. 회의 알림 응용 프로그램은 또한 전화 키패드에서 DTMF (dual-tone multifrequency) 명령을 지원 합니다. 회의 작업을 배포 하 고 전화 접속 회의 옵션을 선택할 때 회의 알림 응용 프로그램은 기본적으로 자동으로 설치 및 활성화 됩니다.

  - **전화 접속 회의 설정 페이지**     전화 접속 회의 설정 페이지는 사용 가능한 언어로 전화 회의 전화 걸기 번호를 표시 하 고, 전화 회의 정보 (예약 하지 않아도 되는 모임)를 제공 하며, PIN (개인 식별 번호) 및 할당 된 회의 정보 관리를 지원 합니다. 전화 접속 회의 설정 페이지는 웹 서비스의 일부로 자동으로 설치 됩니다.

  - **Lync server 2013, 중재 서버 및 PSTN 게이트웨이**     전화 접속 회의에는 중재 서버와 PSTN 게이트웨이 간의 신호 및 미디어를 변환 하는 PSTN 게이트웨이 및 신호 (일부 구성에서 미디어 2013)를 변환 하기 위한 중재 서버가 필요 합니다. 전화 접속 회의의 경우 중재 서버와 다음 중 하나를 각각 하나 이상씩 배포해야 합니다.
    
      - PSTN 게이트웨이
    
      - IP-PBX
    
      - SBC (세션 경계 컨트롤러) (SIP 트렁크를 구성 하 여 연결할 인터넷 전화 통신 서비스 공급자)
    
    <div>
    

    > [!NOTE]  
    > Enterprise Voice를 배포 하는 경우에도 중재 서버 및 PSTN 게이트웨이는 Enterprise Voice 배포의 일부입니다. Enterprise Voice를 배포하지 않는 경우 전화 접속 회의에 대한 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이, IP-PBX 또는 SBC를 배포해야 합니다.

    
    </div>

  - **파일 저장소**     파일 저장소는 녹음 된 이름 오디오 파일에 사용 됩니다. 파일 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포에서 표준 구성 요소입니다.

  - **사용자 저장소**     사용자 저장소는 사용자 Lync Server 2013 Pin을 저장 하는 데 사용 됩니다. PIN은 해시됩니다. 사용자 저장소는 모든 Enterprise Edition 또는 Standard Edition 배포에서 표준 구성 요소입니다.

  - **Lync Server 제어판**     일부 전화 접속 설정은 Lync Server 제어판을 사용 하 여 구성할 수 있습니다.

  - **Lync Server 관리 셸**     모든 전화 접속 설정은 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다. Lync Server 관리 셸 cmdlet은 회의 교환 응용 프로그램 및 회의 알림 응용 프로그램의 배포, 구성, 실행, 모니터링 및 문제 해결에 사용할 수 있습니다. 특정 cmdlet에 대 한 자세한 내용은 Lync Server Management Shell 설명서를 참조 하십시오.

</div>

<div>

## <a name="supported-topologies"></a>지원되는 토폴로지

Lync Server 2013에서는 회의 서비스를 실행 하는 서버가 항상 프런트 엔드 서버 또는 Standard Edition 서버를 사용 하 여 배치 된 됩니다. 초기 배포를 수행 하는 동안 토폴로지 작성기에는 토폴로지에 회의를 포함할 수 있는 옵션이 제공 됩니다. 토폴로지 작성기를 사용 하 여 기존 배포에 회의를 추가할 수도 있습니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오.

<div>

## <a name="dial-in-conferencing-toplogies"></a>전화 회의 토폴로지

다음 토폴로지 및 구성에 전화 접속 회의를 배포할 수 있습니다.

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Enterprise Voice가 있거나 없는 경우

응용 프로그램 서비스, 회의 전화 교환 응용 프로그램 및 회의 알림 응용 프로그램을 중앙 사이트에 배포할 수 있지만 분기 사이트에 배포 하는 것은 지원 되지 않습니다.

<div>


> [!NOTE]  
> 전화 접속 회의를 배포 하는 경우 Lync Server 2013 회의를 배포 하는 모든 풀에 배포 해야 합니다. 모든 풀에서 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포 해야 합니다. 이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀에서 Lync Server 2013 회의에 참가 하는 경우 기록 된 이름 기능을 지원 합니다.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 및 Office Web Apps에 대해 지원 되는 토폴로지

Lync Server 2013에서는 Office Web Apps 서버를 구성 하는 다음과 같은 방법을 제공 합니다. 필요에 따라 다음을 수행할 수 있습니다.

  - **Lync Server 2013와 Office Web Apps 서버를 조직의 방화벽 뒤 및 같은 네트워크 영역에 설치 합니다.** 이 토폴로지를 사용 하는 경우에는 역방향 프록시 서버를 통해 Office Web Apps 서버에 대 한 외부 액세스가 제공 됩니다. Lync Server 2013 및 Office Web Apps 서버 (또는 Office web apps 서버 팜)는 모두 온-프레미스와 조직의 방화벽에 설치 됩니다. Lync Server와 동일한 네트워크 영역에 Office Web Apps 서버를 설치 하는 것이 가장 이상적입니다.
    
    외부 Lync 클라이언트는 인터넷에서 요청을 받아서 내부 네트워크로 전달 하는 서버에 해당 하는 역방향 프록시 서버를 사용 하 여 Lync Server 2013 및 Office Web Apps 서버에 연결할 수 있습니다. (내부 클라이언트는 Office Web Apps 서버에 직접 연결할 수 있기 때문에 역방향 프록시 서버를 사용할 필요가 없습니다.) 이 토폴로지는 Lync Server 2013 에서만 사용 되는 전용 Office Web Apps 서버 팜을 사용 하려는 경우에 가장 효과적으로 작동 합니다.

  - **외부에서 배포 된 Office Web Apps 서버 사용**
    
    이 토폴로지에서는 Lync Server 2013이 온-프레미스에 배포 되 고 Lync Server 네트워크 영역 외부에 배포 된 Office Web Apps 서버를 사용 합니다. Office Web Apps 서버를 회사의 여러 응용 프로그램에서 공유 하 고 Lync Server가 Office Web Apps 서버의 외부 인터페이스를 사용 하도록 요구 하는 네트워크에 배포 하는 경우와 그 반대의 경우도 이러한 현상이 발생할 수 있습니다.
    
    역방향 프록시 서버를 설치할 필요는 없습니다. 대신 Office Web Apps 서버에서 Lync Server 2013 까지의 모든 요청이에 지 서버를 통해 라우팅됩니다. 내부 및 외부 Lync 클라이언트는 모두 외부 URL을 사용 하 여 Office Web Apps 서버에 연결 됩니다.
    
    Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버가 토폴로지 작성기에서 외부 네트워크 (경계/인터넷)에 배포 된** 옵션을 선택 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

선택한 토폴로지에 관계 없이 올바른 방화벽 포트를 열어야 합니다. Office Web Apps 서버, 부하 분산 장치 또는 Lync 서버의 방화벽에서 DNS 이름, IP 주소 및 포트가 차단 되지 않았는지 확인 해야 합니다.

<div>


> [!NOTE]  
> Office Web Apps 서버에 대 한 외부 액세스를 제공 하는 또 다른 옵션은 경계 네트워크에 서버를 배포 하는 것입니다. 이 작업을 수행 하도록 선택 하는 경우 Office Web Apps 서버를 설치 하려면 서버 컴퓨터가 Active Directory 도메인의 구성원 이어야 합니다. 네트워크 정책에 따라 경계 네트워크에 있는 컴퓨터를 Active Directory 도메인 구성원으로 사용할 수 없는 경우에는 경계 네트워크에 Office Web Apps 서버를 설치 하지 않는 것이 좋습니다. 대신 내부 네트워크에 Office Web Apps 서버를 설치 하 고 역방향 프록시 서버를 통해 외부 사용자에 게 액세스를 제공 해야 합니다.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

