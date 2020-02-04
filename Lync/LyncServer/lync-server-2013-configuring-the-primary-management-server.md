---
title: 'Lync Server 2013: 주 관리 서버 구성'
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
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Lync Server 2013에서 주 관리 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-19_

Microsoft Lync Server 2013 관리자에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다. 이 컴퓨터에서 System Center Operations Manager 2007 R2 또는 System Center Operations Manager 2012을 설치 해야 합니다. 또한 Operations Manager 백 엔드 데이터베이스로 작동 하려면 지원 되는 버전의 SQL Server를 설치 해야 합니다. System Center Operations Manager 2012를 사용 하는 경우 다음 버전의 SQL Server를 백 엔드 데이터베이스로 사용할 수 있습니다.

  - SQL Server 2008 R2 서비스 팩 1

  - SQL Server 2008 R2 서비스 팩 2

System Center Operations Manager 2007 R2를 사용 하는 경우 SQL Server 2005 서비스 팩 4 또는 SQL Server 2008 서비스 팩 3 중 하나를 설치 하는 것이 좋습니다. System Center Operations Manager 2007 R2 용 백 엔드 데이터베이스로 SQL Server 2008 R2를 사용할 수도 있습니다. 이 설명서의 부록 1을 참조 하 여 SQL Server 2008 R2를 System Center Operations Manager 2007 R2와 함께 사용 하도록 구성 하는 방법에 대해 자세히 알아보세요.

System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 설치 하는 경우 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.

  - 운영 데이터베이스

  - 서버

  - 콘솔

  - Windows PowerShell cmdlet

  - 웹 콘솔

  - 보고

  - 데이터 웨어하우스

이 문서에서는 이러한 구성 요소와 설치에 대해 자세히 설명 하지 않습니다. System Center Operations Manager 2007 R2에 대 한 자세한 내용은 Operations Manager 2007 R2 설명서 <http://go.microsoft.com/fwlink/p/?linkid=257526> 와 System Center operations Manager 2012 설명서를 참조 하세요. <http://go.microsoft.com/fwlink/p/?linkid=257527> 백 엔드 데이터베이스로 SQL Server 2005 또는 SQL Server 2008 서비스 팩 1을 사용 하는 경우에는 이러한 지침을 따라야 합니다.

System Center Operations Manager 2012를 사용 하는 경우 백 엔드 데이터베이스로 SQL Server 2012을 사용할 수 있습니다. SQL Server 2012에 대 한 자세한 내용은 SQL Server 2012의 온라인 설명서를 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)참조 하세요.

Lync Server 배포 당 하나의 주 관리 서버만을 사용할 수 있다는 점에 유의 하세요. 또한 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 사용할 수 있지만 두 응용 프로그램을 동시에 실행할 수는 없습니다 (둘 중 하나를 선택 해야 함). 예를 들어 System Center Operations Manager 2012를 실행 하는 경우 모든 시스템 센터 에이전트는 System Center Operations Manager 2012도 실행 해야 합니다. 일부 에이전트는 System Center Operations Manager 2012 및 System Center Operations Manager 2007 R2를 실행 하는 다른 에이전트를 실행할 수 없습니다.

</div>

<span> </span>

</div>

</div>

</div>

