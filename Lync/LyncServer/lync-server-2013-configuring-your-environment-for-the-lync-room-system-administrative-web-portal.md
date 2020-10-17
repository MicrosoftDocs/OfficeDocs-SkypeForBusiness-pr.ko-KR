---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털에 대 한 환경 구성'
description: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털에 대 한 환경 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542204"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Lync 대화방 시스템 관리 웹 포털에 대 한 Lync Server 2013 환경 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-22_

LRS (Lync 대화방 시스템) 관리 웹 포털을 사용 하려면 다음 필수 구성 요소를 설치 하거나 구성 해야 합니다.

<div>


> [!IMPORTANT]  
> 서버가 Kerberos 인증과 NTLM 인증을 모두 사용 하 여 구성 되었지만 도메인에 가입 되지 않은 컴퓨터에서 LRS가 실행 되 고 있으면 Kerberos 인증이 실패 하 고 사용자에 게 관리 포털의 LRS 상태가 표시 되지 않습니다. 이 문제를 해결 하려면 NTLM 인증 또는 NTLM 및 DSK 인증 (Kerberos 제외)을 사용 하 여 서버를 구성 하거나 LRS 컴퓨터를 도메인에 참가 시킵니다.



</div>

1.  Lync server 토폴로지에서 Lync Server 2013 누적 업데이트: 7 월 2013을 설치 합니다.
    
    업데이트를 가져오거나 여기에 포함 된 항목을 확인 하려면 [Lync Server 2013 용 업데이트](https://go.microsoft.com/fwlink/p/?linkid=323959)를 참조 하세요.

2.  SIP 사용이 가능한 Active Directory 사용자를 만듭니다.
    
    LRS 관리 웹 포털은 이러한 자격 증명을 사용 하 여 Lync Server에서 정보를 쿼리 합니다. 권장 사용자 이름은 LRSApp입니다.

3.  이름이 LRSSupportAdminGroup 인 Active Directory 보안 그룹을 만듭니다.
    
    그룹 범위가 글로벌이 고 그룹 유형이 Security 인 그룹을 만듭니다. SIP 사용이 그룹에 추가 된 사용자는 대화방 목록을 확인 하 고 로그 수집과 같은 특정 명령을 실행할 수 있습니다.

4.  이름이 LRSFullAccessAdminGroup 인 Active Directory 보안 그룹을 만듭니다.
    
    그룹 범위가 글로벌이 고 그룹 유형이 Security 인 그룹을 만듭니다 .이 그룹에 추가 된 SIP 사용 사용자에 게는 모든 관리자 포털 기능을 사용할 수 있는 권한이 부여 됩니다.
    
     
    
    ![보안 그룹 역할이 포함 된 관리자 그룹 목록](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "보안 그룹 역할이 포함 된 관리자 그룹 목록")  
    
     

5.  LRSFullAccessAdminGroup을 LRSSupportAdminGroup의 구성원으로 추가 합니다.
    
    ![LRSSupportAdminGroup Properties Members 페이지](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members 페이지")  
    
     

6.  이름이 LRSSupport 인 SIP 사용 Active Directory 사용자를 만듭니다. 이 사용자를 LRSSupportAdminGroup에 추가 합니다.
    
    ![LRSSupportAdminGroup Properties Members 페이지](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members 페이지")  
    
     

7.  Microsoft 다운로드 센터에서 사용할 수 있는 Visual Studio 2010 SP1 및 Visual Web Developer 2010 s p 1 용 ASP.NET MVC 4를 설치 [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) 합니다.

</div>

<span> </span>

</div>

</div>

</div>

