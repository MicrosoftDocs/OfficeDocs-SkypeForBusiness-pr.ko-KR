---
title: 'Lync Server 2013: Lync Server 2013을 실행 하는 서버의 시스템 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d25be2132fdaba58024ba58081656b830ea9fe4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497335"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Lync Server 2013을 실행 하는 서버의 시스템 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-07-24_

<div>


> [!NOTE]
> 하드웨어 요구 사항에 대 한 자세한 내용은 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013에 대 한 서버 하드웨어 플랫폼</A>을 참조 하십시오.



</div>

Standard Edition과 Enterprise Edition 서버는 동일한 소프트웨어 요구 사항을 공유 합니다.

Lync Server 2013, Enterprise Edition을 실행 하는 서버는 주요 조직 배포 환경의 대규모 조직을 대상으로 합니다. Enterprise Edition Server는 풀당 약 80,000명의 홈 사용자로 확장할 수 있도록 설계되었습니다. Lync Server 2013, Standard Edition을 실행 하는 서버는 기본 조직 배포에서 소규모 조직과 원격 위치를 위한 것입니다. Standard Edition 서버 한 쌍은 최대 5000 명의 사용자를 지원할 수 있습니다. Standard Edition 서버와 Enterprise Edition 서버 간의 차이점에 대 한 자세한 내용은 [Deployment overview For Lync Server 2013](lync-server-2013-deployment-overview.md)을 참조 하십시오.

<div>

## <a name="operating-system-installation"></a>운영 체제 설치

<div>


> [!IMPORTANT]
> Lync Server 2013는 64 비트 버전 에서만 사용할 수 있으며, 64 비트 하드웨어와 64 비트 버전의 Windows Server 운영 체제가 필요 합니다. 이 릴리스에서는 32 비트 버전의 Lync Server 2013를 사용할 수 없습니다.



</div>

Standard Edition과 Enterprise Edition 서버는 다음 중 하나를 사용할 수 있습니다.

  - Windows Server 2008 R2 SP1 또는 최신 서비스 팩

  - Windows Server 2012

  - Windows Server 2012 R2

Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 서버에 운영 체제 소프트웨어를 설치 합니다. 그런 다음 모든 업데이트를 순서대로 적용하여 운영 체제에 최신 업데이트를 적용하고, 필요한 업데이트 수준이 조직의 표준과 일치하도록 합니다. 운영 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server and tools 운영 체제 지원에서 Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) 을 참조 하십시오.

> [!NOTE] 
> 운영 체제의 전체 업그레이드는 Lync Server 2013에서 지원 되지 않습니다.  별도의 풀을 배포 하 고 다른 운영 체제를 사용 하 여 새 풀로 사용자를 마이그레이션해야 합니다.

<div>


> [!NOTE]
> Lync Server 2013이 Windows Server 2012 r 2에서 작동 하도록 하려면 Windows Server에서 레지스트리 키의 값을 변경 해야 할 수 있습니다. 이 변경 내용은 인증서가 올바르게 작동 하 고 클라이언트에서 Sba (survivable Branch 기기에 등록 하는 데 필요할 수 있습니다. 자세한 내용은를 참조 <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 하세요.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 용 추가 소프트웨어

Lync Server 2013에서는 운영 체제에 필요한 업데이트 외에 운영 체제 역할, 기능 및 소프트웨어가 작동 해야 합니다. 토폴로지를 게시 하 고 Lync Server 2013을 설치 하기 전에 설치 해야 하는 추가 소프트웨어에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하세요.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>모든 서버 역할에 필요한 추가 소프트웨어

모든 서버 역할에서 Windows PowerShell 명령줄 인터페이스 3.0 및 Microsoft .NET Framework 4.5가 설치 되어 있는지도 확인 해야 합니다.

또한 Lync Server 관리 도구를 실행 하는 모든 컴퓨터에 Windows PowerShell 명령줄 인터페이스 3.0 및 Microsoft .NET Framework 4.5이 필요 합니다.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013를 사용 하려면 Lync Server 토폴로지에서 작업을 수행할 각 컴퓨터에 Windows PowerShell 3.0을 설치 해야 합니다. Windows PowerShell 3.0을 설치 하는 방법에 대 한 자세한 내용은 [설치 Windows powershell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하십시오.

<div>


> [!NOTE]
> Windows Server &nbsp; 2008 &nbsp; R2 SP1에서는 Microsoft .net Framework 4.5을 설치 하기 전에 windows PowerShell 명령줄 인터페이스 3.0를 설치할 수 없습니다.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Windows Server 2012 또는 Windows Server 2012 r 2에서 Lync Server 2013를 실행 하는 서버에 Microsoft .NET Framework 4.5을 설치 하는 경우에는 하나의 추가 단계를 수행 해야 합니다. .NET Framework 4.5이 설치 되 면 서버 관리자를 사용 하 여 HTTP 정품 인증을 설치 합니다.

**Windows Server 2012 또는 Windows Server 2012 r 2에서 .NET 4.5 HTTP 정품 인증을 설치 하려면**

1.  **시작** 메뉴에서 **프로그램**, **관리 도구**를 차례로 클릭 한 다음 **서버 관리자**를 클릭 합니다.

2.  서버 관리자의 **기능 요약**에서 **기능 추가**를 선택 합니다.

3.  **.Net Framework 4.5**를 확장 합니다.

4.  **WCF 활성화** 가 아직 선택 되어 있지 않으면 선택 합니다. 그런 다음 **HTTP 정품 인증**을 선택 합니다.

5.  **다음** 을 클릭 하 고 화면의 지시에 따라 설치를 완료 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

