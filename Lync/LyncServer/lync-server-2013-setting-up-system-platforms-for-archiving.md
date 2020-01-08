---
title: 'Lync Server 2013: 보관을 위한 시스템 플랫폼 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 시스템 플랫폼을 보관 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

보관 배포를 시작 하기 전에 시스템 요구 사항을 충족 하는 하드웨어에 필요한 운영 체제 및 기타 필수 구성 요소 소프트웨어를 설치 해야 합니다.

  - **Lync server 2013 플랫폼**   lync server 2013 배포에는 보관 서버가 없습니다. 대신 통합 데이터 수집 에이전트는 프런트 엔드 서버와 Standard Edition 서버에서 보관을 위해 데이터를 캡처하기 위해 실행 되므로 보관을 호스트 하는 데 별도의 시스템 플랫폼이 필요 하지 않습니다.

  - **데이터 저장소 플랫폼**   Lync Server 2013에서는 다음 중 하나를 사용 하 여 데이터를 저장할 수 있습니다.
    
      - **Microsoft exchange 통합**   exchange 2013 배포를 사용 하 여 Lync Server 2013 보관 데이터를 저장 하려는 경우, 보관 데이터를 저장 하기 위해 별도의 데이터베이스를 설정 하는 대신 또는 추가 하는 것이 아니라 exchange 배포에서 exchange 2013을 실행 중 이어야 합니다. Exchange 2013에 대 한 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하세요.
    
      - **Sql server**   Microsoft Exchange 통합을 사용 하는 대신 또는 데이터 보관을 위해 별도의 sql server 데이터베이스를 사용 하려는 경우 보관을 배포 하기 전에 데이터베이스에 대 한 시스템 플랫폼을 설정 해야 합니다. 특정 시스템 플랫폼 요구 사항은 보관 데이터베이스용으로 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012 사용 여부에 따라 달라 집니다. 이러한 데이터베이스용 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Microsoft SQL Server 2008 R2 및 Microsoft SQL Server 2012 제품 설명서를 참조 하세요.

  - **파일 서버 플랫폼**   lync server 2013에서는 프런트 엔드 서버 또는 Standard Edition 서버를 설정할 때 파일 저장소에 대해 지정 하는 위치에 lync server 보관 파일을 저장 합니다. 파일 저장소 보관을 위한 별도의 위치를 지정할 수 없으므로 파일 저장소 보관에 별도의 시스템 플랫폼이 필요 하지 않습니다. Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013에서 보관 된 Lync 통신 용 파일은 해당 Exchange 서버에 속한 사용자의 Exchange 2013 서버에 저장 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

