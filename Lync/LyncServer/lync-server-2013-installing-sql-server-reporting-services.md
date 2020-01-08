---
title: 'Lync Server 2013: SQL Server Reporting Services 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Lync Server 2013에서 SQL Server Reporting Services 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-20_

Microsoft Lync Server 2013 모니터링 보고서를 사용 하려는 경우 (자세한 내용은이 문서의 다음 섹션 참조) 먼저 SQL Server Reporting Services를 설치 해야 합니다. Reporting Services는 Microsoft SQL Server를 설치 하는 동시에 설치 하거나 SQL Server가 설치 된 후 언제 든 지 설치할 수 있습니다. SQL Server를 설치 하지 않은 경우에는이 설명서의 앞에 나와 있는 지침을 따르세요. SQL Server를 설치할 때 기능 선택 페이지에서 Reporting Services를 선택 합니다. 그러면 SQL Server Reporting Services가 설치 됩니다.

이미 SQL Server를 설치 했지만 SQL Server Reporting Services를 설치 하지 않은 경우 적절 하 게 SQL Server 2008 R2 또는 SQL Server 2012에 대 한 적절 한 지침을 따라 해당 기능을 추가할 수 있습니다.

Reporting Services가 성공적으로 설치 되었는지 확인 하려면 다음 단계를 완료 합니다.

1.  Microsoft SQL Server 2008 R2를 실행 하는 경우 **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭 한 다음 **Reporting Services 구성 관리자**를 클릭 합니다.
    
    Microsoft SQL Server 2012을 실행 중인 경우 **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft SQL Server 2012**, **구성 도구**, **Reporting Services 구성 관리자**를 차례로 클릭 합니다.

2.  **Reporting Services 구성 연결** 대화 상자 **에서 서버 이름 상자에** 서버 이름이 나타나고 모니터링 데이터를 저장 하는 SQL Server 인스턴스의 이름이 **보고서 서버 인스턴스** 상자에 표시 되는지 확인 합니다. **연결**을 클릭 합니다.

보고 서비스 구성 관리자에서 보고서 서버 상태 창에 SQL Server Reporting Services가 설치 되었고 Reporting Services가 현재 실행 되 고 있음을 표시 해야 합니다. 보고서 서버 상태가 **시작** 됨으로 표시 되 고 **시작** 단추를 사용할 수 없습니다. Reporting Services가 실행 되 고 있지 않으면 **시작** 을 클릭 하 여 서비스를 시작 합니다.

보고서 서버 데이터베이스 이름 레이블 옆에 데이터베이스가 나열 되지 않으면 다음을 수행 합니다.

1.  Reporting Services 구성 관리자에서 **데이터베이스**를 클릭 합니다.

2.  보고서 서버 데이터베이스 창에서 **데이터베이스 변경을**클릭 합니다.

3.  보고서 서버 데이터베이스 구성 마법사의 작업 창에서 **새 보고서 서버 데이터베이스 만들기** 를 선택 하 고 **다음**을 클릭 합니다.

4.  보고서 서버 데이터베이스 구성 마법사의 데이터베이스 서버 창에서 **서버 이름**, **인증 유형**및 **사용자 이름** 상자에 나열 된 정보가 올바른지 확인 합니다. **연결 테스트** 를 클릭 하 여 데이터베이스 서버에 연결할 수 있는지 확인 하 고 **다음**을 클릭 합니다.

5.  보고서 서버 데이터베이스 구성 마법사의 데이터베이스 창에서 **데이터베이스 이름**, **언어**및 **보고서 서버 모드** 에 대 한 기본값을 적용 하 고 **다음**을 클릭 합니다.

6.  보고서 서버 데이터베이스 구성 마법사의 자격 증명 창에서 **인증 형식** 드롭다운 목록과 **사용자 이름** 및 **암호** 상자에 올바른 정보가 나열 되어 있는지 확인 하 고 **다음**을 클릭 합니다.

7.  보고서 서버 데이터베이스 구성 마법사의 요약 창에서 **다음**을 클릭 합니다.

8.  보고서 서버 데이터베이스 구성 마법사의 진행률 및 완료 창에서 **마침을**클릭 합니다.

Reporting Service Url이 구성 되었는지 확인 하려면 **웹 서비스 url**을 클릭 합니다. 머리글 **보고서 서버 웹 서비스 url**아래에 하나 이상의 url이 표시 됩니다. 이러한 Url을 각각 클릭 하 여 SQL Server Reporting Services 로컬 설치의 홈 페이지에 도달할 수 있는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

