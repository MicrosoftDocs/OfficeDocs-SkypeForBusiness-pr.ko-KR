---
title: 'Lync Server 2013: 모범 사례 분석기 준비 및 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c97657b42ec4ea26f5300b1d28215d0360b63cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013에서 모범 사례 분석기 준비 및 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

이 항목에 설명된 작업을 수행하려면 Administrators 그룹 구성원으로 로그온해야 합니다.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>모범 사례 분석기 설치를 위한 시스템 요구 사항

Lync Server 2013, 모범 사례 분석기를 실행 하 여 환경을 검색 하려면 컴퓨터에서 다음 운영 체제 중 하나의 64 비트 버전을 실행 하 고 있어야 합니다.

  - Windows Server 2008 R2 SP1 (서비스 팩 1) 표준 운영 체제

  - Windows Server 2008 R2 SP1 엔터프라이즈 운영 체제

  - Windows Server 2008 R2 SP1 Datacenter 운영 체제

  - Windows Server 2012 Datacenter 운영 체제

  - Windows Server 2012 Standard 운영 체제

  - Windows Server 2012 엔터프라이즈 운영 체제

  - Windows Server 2012 R2 Datacenter 운영 체제

  - Windows Server 2012 R2 Standard 운영 체제

  - Windows Server 2012 R2 Enterprise 운영 체제

  - Windows 8 운영 체제

  - Windows 7 운영 체제

또한 컴퓨터에서 다음을 실행해야 합니다.

  - Microsoft .NET Framework 4.5. Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다.

  - Lync Server 2013, 핵심 구성 요소

  - WMI 이전 버전과의 호환성 패키지. 자세한 내용은 마이그레이션 설명서에서 [WMI 이전 버전과의 호환성 패키지 설치](install-wmi-backward-compatibility-package.md) 를 참조 하십시오.

  - Windows PowerShell 3.0. 자세한 내용은 배포 설명서의 [Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) 을 참조 하십시오.

Lync Server 2013, 핵심 구성 요소 또는 WMI 이전 버전과의 호환성 패키지를 실행 하 고 있지 않은 지원 되는 운영 체제를 사용 하는 컴퓨터에 모범 사례 분석기를 설치할 수 있지만 해당 컴퓨터의 모범 사례 분석기를 통해 보고서를 볼 수만 있습니다. 검색을 실행 합니다.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>설치할 컴퓨터 선택

Lync server 2013 관리 전용 컴퓨터에 Lync Server 2013, 모범 사례 분석기를 설치 하는 것이 좋습니다. Lync Server 2013을 실행 하는 서버나 Lync Server 2013 관리 도구를 실행 하는 관리 컴퓨터에 도구를 설치할 수 있습니다. Lync Server를 실행 하는 서버에이 도구를 설치 하는 경우에는이 도구를 사용 하 여 해당 서버만 검사 하는 것이 좋습니다.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>모범 사례 분석기 설치

Lync Server 2013에 대 한 모범 사례 분석기를 다운로드할 수 [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)있습니다.

모범 사례 분석기를 설치하려면 도구를 설치하려는 컴퓨터에서 Microsoft Installer 파일 RtcBPA.msi를 시작하고 화면 지침을 따릅니다. 프로그램 파일을 설치 하는 기본 위치는 \<시스템 드라이브\>\\프로그램 파일\\Lync Server 2013\\BPA입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

