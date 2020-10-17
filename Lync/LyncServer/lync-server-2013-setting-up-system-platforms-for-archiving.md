---
title: 'Lync Server 2013: 보관용 시스템 플랫폼 설정'
description: 'Lync Server 2013: 보관용 시스템 플랫폼을 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554184"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 보관용 시스템 플랫폼 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

보관 배포를 시작하기 전에 시스템 요구 사항을 충족하는 하드웨어에 필요한 운영 체제 및 기타 필수 구성 요소 소프트웨어를 설치해야 합니다.

  - **Lync Server 2013 플랫폼**     Lync Server 2013 배포에는 보관 서버가 없습니다. 대신 통합 데이터 수집 에이전트가 프런트 엔드 서버 및 Standard Edition 서버에서 실행되어 보관할 데이터를 캡처하므로 보관을 호스팅하기 위해 별도로 필요한 시스템 플랫폼은 없습니다.

  - **데이터 저장소 플랫폼**     Lync Server 2013에서는 다음 중 하나를 사용 하 여 데이터를 저장할 수 있습니다.
    
      - **Microsoft Exchange 통합**     보관 데이터를 저장 하기 위해 별도의 데이터베이스를 설정 하는 대신 또는 Exchange 2013 배포를 사용 하 여 Lync Server 2013 보관 데이터를 저장 하려면 Exchange 배포에서 Exchange 2013을 실행 중 이어야 합니다. Exchange 2013에 대 한 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하십시오.
    
      - **SQL Server**     Microsoft Exchange 통합을 사용 하는 대신 또는 보관 데이터를 저장 하는 별도의 SQL Server 데이터베이스를 사용 하려는 경우 보관을 배포 하기 전에 데이터베이스에 대 한 시스템 플랫폼을 설정 해야 합니다. 특정 시스템 플랫폼 요구 사항은 보관 데이터베이스용으로 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012을 사용 하는지에 따라 달라 집니다. 이러한 데이터베이스에 대 한 시스템 플랫폼을 설정 하는 방법에 대 한 자세한 내용은 Microsoft SQL Server 2008 R2 및 Microsoft SQL Server 2012 제품 설명서를 참조 하십시오.

  - **파일 서버 플랫폼**     Lync Server 2013에서는 프런트 엔드 서버 또는 Standard Edition 서버를 설정할 때 파일 저장소로 지정한 것과 동일한 위치에 Lync Server 보관 파일을 저장 합니다. 보관 파일 저장용으로 별도의 위치를 지정할 수는 없으므로, 보관 파일 저장을 위해 별도의 시스템 플랫폼이 필요하지는 않습니다. Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 보관 된 Lync communications 파일은 해당 Exchange 서버에 있는 사용자에 대해 Exchange 2013 서버에 저장 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

