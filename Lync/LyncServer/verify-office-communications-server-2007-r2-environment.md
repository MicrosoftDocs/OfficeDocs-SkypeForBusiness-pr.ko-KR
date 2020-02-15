---
title: Office Communications Server 2007 R2 환경 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce71bce6594c0604027df9f055859f023048518
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Office Communications Server 2007 R2 환경 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-16_

Office Communications Server 2007 r 2와 함께 사용 상태로 Lync Server 2013을 배포 하기 전에 Office Communications Server 2007 R2 서비스가 구성 및 시작 되었는지 확인 해야 합니다.

**Office Communications Server 2007 R2 관리 도구를 사용 하 여 풀이 시작 되었는지 확인**

1.  Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  **포리스트** 노드를 확장하고 **Standard Edition 서버** 또는 **엔터프라이즈 풀** 노드를 확장한 후 풀 또는 서버 이름을 확장합니다.

3.  Standard Edition Server 또는 엔터프라이즈 풀에서 서비스가 실행 중인지 확인합니다.
    
    ![Office Communications Server 2007 R2 관리 콘솔](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 관리 콘솔")

**Office Communications Server 2007 R2에 대해 구성된 사용자 검토**

1.  Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  **Forest** 노드를 확장하고 **Standard Edition Server** 또는 **엔터프라이즈 풀** 노드를 확장한 다음 해당 풀 또는 서버 이름을 확장합니다.

3.  **사용자**를 클릭합니다.

4.  Office Communications Server 2007 R2 사용자 목록을 확인 합니다.
    
    ![OCS 관리 도구의 사용자 목록](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 관리 도구의 사용자 목록")

**레거시 XMPP 페더레이션 파트너 구성 확인**

1.  레거시 XMPP 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.

2.  Office Communications Server XMPP 게이트웨이 서비스가 시작되었는지 확인합니다.
    
    ![Office Communications Server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 게이트웨이 서비스")

</div>

<span> </span>

</div>

</div>

</div>

