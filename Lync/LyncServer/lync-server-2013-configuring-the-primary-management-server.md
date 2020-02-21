---
title: 'Lync Server 2013: 기본 관리 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18ec967418effe53399070bc8e6f414cd2d927cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Lync Server 2013에서 기본 관리 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-19_

Microsoft Lync Server 2013에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 관리자가 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다. 이 컴퓨터에서 System Center Operations Manager 2007 R2 또는 System Center Operations Manager 2012을 설치 해야 합니다. 또한 Operations Manager 백 엔드 데이터베이스로 작동 하려면 지원 되는 버전의 SQL Server를 설치 해야 합니다. System Center Operations Manager 2012를 사용 하는 경우 다음 SQL Server 버전을 백 엔드 데이터베이스로 사용할 수 있습니다.

  - SQL Server 2008 R2 서비스 팩 1

  - SQL Server 2008 R2 서비스 팩 2

System Center Operations Manager 2007 R2를 사용 하는 경우 SQL Server 2005 서비스 팩 4 또는 SQL Server 2008 서비스 팩 3을 설치 하는 것이 좋습니다. System Center Operations Manager 2007 r 2의 백 엔드 데이터베이스로 SQL Server 2008 R2를 사용할 수도 있습니다. System Center Operations Manager 2007 r 2에서 작동 하도록 SQL Server 2008 R2를 구성 하는 방법에 대 한 자세한 내용은이 설명서의 부록 1을 참조 하십시오.

System Center Operations Manager 2012 또는 System Center Operations Manager 2007 r 2를 설치 하는 경우에는 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.

  - 운영 데이터베이스

  - Server

  - 콘솔용

  - Windows PowerShell cmdlet

  - 웹 콘솔

  - Reporting

  - 데이터 웨어하우스

이러한 구성 요소 및 구성 요소의 설치에 대해서는 이 문서에서 자세히 설명하지 않습니다. System Center Operations Manager 2007 r 2에 대 한 자세한 내용은 Operations Manager 2007 R2 설명서 <https://go.microsoft.com/fwlink/p/?linkid=257526> 및 System Center operations Manager 2012 설명서를 참조 하십시오 <https://go.microsoft.com/fwlink/p/?linkid=257527>. SQL Server 2005 또는 SQL Server 2008 서비스 팩 1을 백 엔드 데이터베이스로 사용 하려는 경우에는 이러한 지침을 따라야 합니다.

System Center Operations Manager 2012를 사용 하는 경우 백 엔드 데이터베이스로 SQL Server 2012을 사용할 수 있습니다. SQL Server 2012에 대 한 자세한 내용은 온라인 설명서 for SQL Server 2012를 [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)참조 하십시오.

기본 관리 서버는 Lync Server 배포 당 하나만 있을 수 있습니다. 또한 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 r 2를 사용할 수 있지만 두 응용 프로그램을 동시에 실행할 수는 없습니다 (둘 중 하나를 선택 해야 함). 예를 들어 System Center Operations Manager 2012을 실행 하는 경우 모든 System Center 에이전트에서 System Center Operations Manager 2012도 실행 해야 합니다. System Center Operations Manager 2012 및 System Center Operations Manager 2007 r 2를 실행 하는 에이전트를 실행 하는 에이전트도 있을 수 없습니다.

</div>

<span> </span>

</div>

</div>

</div>

