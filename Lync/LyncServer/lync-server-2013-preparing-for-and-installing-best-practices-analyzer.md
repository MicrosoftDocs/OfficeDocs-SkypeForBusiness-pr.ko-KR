---
title: 'Lync Server 2013: 모범 사례 분석기 준비 및 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013에서 모범 사례 분석기 준비 및 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

이 항목에서 설명 하는 작업을 수행 하려면 관리자 그룹의 구성원으로 로그온 해야 합니다.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>모범 사례 분석기 설치에 대 한 시스템 요구 사항

Lync Server 2013, 모범 사례 분석기를 실행 하 여 환경을 검색 하려면 컴퓨터에서 다음 운영 체제 중 하나의 64 비트 버전을 실행 해야 합니다.

  - Windows Server 2008 R2 SP1 (Service Pack 1) 표준 운영 체제

  - Windows Server 2008 R2 SP1 엔터프라이즈 운영 체제

  - Windows Server 2008 R2 SP1 데이터 센터 운영 체제

  - Windows Server 2012 데이터 센터 운영 체제

  - Windows Server 2012 표준 운영 체제

  - Windows Server 2012 엔터프라이즈 운영 체제

  - Windows Server 2012 R2 Datacenter 운영 체제

  - Windows Server 2012 R2 표준 운영 체제

  - Windows Server 2012 R2 엔터프라이즈 운영 체제

  - Windows 8 운영 체제

  - Windows 7 운영 체제

또한 컴퓨터는 다음을 실행 해야 합니다.

  - Microsoft .NET Framework 4.5. Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.

  - Lync Server 2013, Core 구성 요소.

  - WMI 이전 버전과의 호환성 패키지. 자세한 내용은 마이그레이션 설명서에서 [WMI 이전 버전과 호환성 패키지 설치](install-wmi-backward-compatibility-package.md) 를 참조 하세요.

  - Windows PowerShell 3.0. 자세한 내용은 배포 설명서에서 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md) 를 참조 하세요.

Lync Server 2013, Core 구성 요소 또는 WMI 이전 버전과의 호환성 패키지를 실행 하 고 있지 않은 지원 되는 운영 체제를 사용 하는 컴퓨터에 모범 사례 분석기를 설치할 수 있지만, 해당 컴퓨터에 대 한 모범 사례 분석기를 사용 하 여 보고서를 볼 수는 없습니다. 스캔을 실행 합니다.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>설치할 컴퓨터 선택

Lync server 2013 관리 전용 컴퓨터에 Lync Server 2013, 모범 사례 분석기를 설치 하는 것이 좋습니다. Lync Server 2013를 실행 하는 서버 또는 Lync Server 2013 관리 도구를 실행 하는 관리 컴퓨터에이 도구를 설치할 수 있습니다. Lync Server를 실행 하는 서버에이 도구를 설치 하는 경우 도구를 사용 하 여 해당 서버만 검색 하는 것이 좋습니다.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>모범 사례 분석기 설치

Lync Server 2013에 대 한 모범 사례 분석기를 다운로드할 수 [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)있습니다.

모범 사례 분석기를 설치 하려면 도구를 설치 하려는 컴퓨터에서 Microsoft 설치 관리자 파일인 RtcBPA를 시작 하 고 화면의 지침을 따릅니다. 프로그램 파일을 설치 하는 기본 위치는 \<시스템 드라이브\>\\프로그램 파일\\입니다. Lync\\Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

