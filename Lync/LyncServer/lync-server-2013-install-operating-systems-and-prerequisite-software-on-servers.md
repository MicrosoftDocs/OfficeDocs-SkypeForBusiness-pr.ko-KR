---
title: 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-07-24_

하드웨어 및 소프트웨어 인프라를 설치한 후에는 배포하려는 각 서버의 다른 모든 소프트웨어 필수 구성 요소와 함께 적절한 Windows 운영 체제 및 업데이트를 설치해야 합니다. 여기에는 각 Lync Server 2013 서버 역할과 배포에 필요한 SQL Server를 실행 하는 모든 추가 인프라 서버 또는 서버가 포함 됩니다.

<div>


> [!NOTE]
> 이 섹션에서는 내부 서버용 운영 체제 및 소프트웨어 필수 구성 요소 설치에 대해 설명합니다. 외부 사용자 액세스를 지원 하기 위해에 지 서버를 배포 하는 경우에도에 지 서버 및 역방향 프록시 서버를 포함 하 여 해당 서버에 대 한 운영 체제 및 필수 구성 요소 소프트웨어를 설치 해야 합니다. 외부 사용자 액세스를 지원 하도록 서버를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">경계 2013 네트워크에서 서버 설치 준비</A> 를 참조 하십시오.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>서버에 Windows 운영 체제 설치

배포 하는 각 서버에 다음과 같이 적절 한 Windows 운영 체제를 설치 합니다.

  - **Lync server 2013**   을 실행 하는 서버 lync server 2013 실행 서버에 대 한 운영 체제 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [lync server 2013의 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.

  - **데이터베이스 서버**   백 엔드 데이터베이스, 보관 데이터베이스 및 모니터링 데이터베이스를 포함 하는 데이터베이스 서버의 운영 체제 요구 사항에 대 한 자세한 내용은 SQL Server 설명서를 참조 하십시오. SQL Server 2012의 경우 SQL Server 2012 온라인 설명서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).

<div>


> [!NOTE]
> Windows Server&nbsp;2008&nbsp;R2 s p 1에 Lync Server 2013을 설치 하는 경우 먼저 Microsoft 기술 자료 문서 2646886, "FIX: 모듈에서" IIS 7.5의 insertentitybody 메서드를 호출 하면 힙 손상 발생 합니다. "(여기서 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp는; kbid = 2646886</A>)에 설명 되어 있는 업데이트를 설치 해야 합니다.<BR>또한 기술 자료 문서, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">이벤트 id 32402, 61045은 Windows Server 2012 r 2에 설치 된 Lync Server 2013 프런트 엔드 서버</A>에 설명 된 대로 레지스트리를 수정 해야 합니다.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>서버에 Windows Update 설치

각 서버에 Windows Update에서 다음 업데이트를 설치 합니다.

  - **Lync server 2013**   을 실행 하는 서버에 대 한 windows update lync server 2013을 실행 하는 서버에 필요한 windows update의 업데이트에 대 한 자세한 내용은 계획 설명서에서 [lync server 2013에 대 한 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하십시오.

  - **데이터베이스 서버**   백 엔드 데이터베이스, 보관 데이터베이스 및 모니터링 데이터베이스를 포함 하 여 데이터베이스 서버에 필요한 Windows Update 업데이트에 대 한 자세한 내용은 SQL Server 2012 설명서를 참조 하십시오. SQL Server 2012의 경우 SQL Server 2012 온라인 설명서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>서버에 다른 소프트웨어 필수 구성 요소 설치

Lync Server 2013를 사용 하려면 서버에 다음과 같은 추가 소프트웨어를 설치 해야 합니다.

  - **Lync server 2013**   을 실행 하는 서버의 필수 구성 요소 소프트웨어 lync server 2013 실행 서버에 대 한 추가 소프트웨어 필수 구성 요소는 배포 되는 서버 역할에 따라 다릅니다. 각 서버의 특정 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하십시오.

  - **Windows identity foundation**   Lync server 2013에서는 서버 간 인증 시나리오를 지원 하기 위해 windows identity foundation을 설치 해야 합니다. 컴퓨터에 이미 설치 되어 있는지 확인 하려면 제어판에서 **프로그램 및 기능**을 클릭 하 고 **설치 된 업데이트를 확인**한 다음 **Microsoft Windows**를 확인 하세요. Windows Identity Foundation을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은를 참조 하세요.

  - **Microsoft .net framework 4.5**   Lync Server 2013을 사용 하려면 64 비트 버전의 microsoft .net framework 4.5이 필요 합니다.

  - **데이터베이스 서버용**   필수 구성 요소 소프트웨어 백 엔드 데이터베이스, 보관 데이터베이스 및 모니터링 데이터베이스를 포함 하 여 데이터베이스 서버에 필요한 Windows 업데이트에 대 한 자세한 내용은 SQL Server 2012 설명서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013에서는 각 Standard Edition 서버에 Microsoft SQL Server 2012 Express를 자동으로 설치 하 고, 로컬 구성 저장소가 있는 Lync Server 2013를 실행 하는 각 서버에 대 한 기본 설정 합니다.

    
    </div>

  - **Windows media 형식 런타임**   회의를 배포할 모든 프런트 엔드 서버 및 Standard Edition 서버에 windows media 형식 런타임이 설치 되어 있어야 합니다. Windows Media 형식 런타임은 통화 대기, 알림 및 응답 그룹 응용 프로그램에서 알림 및 음악에 대해 재생하는 Windows Media Audio(.wma) 파일을 실행하는 데 필요합니다.
    
    <div>
    

    > [!NOTE]
    > Windows Server 2012 및 Windows Server 2012 R2의 경우 Windows Media 형식 런타임이 Microsoft Media Foundation과 함께 설치 됩니다.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Windows Server&nbsp;2008 및 windows server&nbsp;2008&nbsp;R2의 경우 Windows Media 형식 런타임이 windows 데스크톱 환경의 일부로 설치 됩니다. Lync Server 2013을 설치 하기 전에 Windows 데스크톱 환경을 설치 하는 것이 좋습니다. Lync Server 2013이 서버에서이 소프트웨어를 찾지 못하는 경우 설치 하 라는 메시지가 표시 되 고 서버를 다시 시작 하 여 설치를 완료 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

