---
title: Lync Server 2013 클라이언트 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331241dea4f047928913550764c995a7c6f05260
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Lync Server 2013 클라이언트 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

사용자를 Lync Server 2013로 마이그레이션한 후에는 다음을 수행 합니다.

1.  새 Lync Server 2013 서버에서 클라이언트 버전 필터를 사용 하 여 최신 업데이트가 설치 된 클라이언트만 로그인 하도록 허용 합니다.

2.  필요에 따라 클라이언트 부트스트랩에 필요한 그룹 정책 설정을 구성합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 클라이언트 부트스트랩 정책 구성을](lync-server-2013-configuring-client-bootstrapping-policies.md) 참조 하십시오. 이러한 설정에 대한 구성은 기존 클라이언트 부트스트랩 정책을 변경하려는 경우 또는 새로운 클라이언트 부트스트랩 정책을 설정하려는 경우에만 필요합니다. 클라이언트 부트스트랩 정책을 구성하지 않으려는 경우 또는 레거시 클라이언트 부트스트랩 정책을 그대로 유지하려는 경우에는 작업이 필요하지 않습니다.

3.  Lync Server 2013 제어판, Lync Server 2013 관리 셸 또는 둘 다를 사용 하 여 특정 사용자 또는 사용자 그룹에 대 한 기타 사용자 및 클라이언트 정책을 구성 합니다. 자세한 내용은 계획 설명서에서 [New and changed settings For Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) 을 참조 하십시오.

4.  최신 누적 업데이트와 함께 최신 버전의 Lync Server 2013 클라이언트를 배포 합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md) 를 참조 하십시오.

5.  반드시 조직에 Lync Server 2013 향상 된 개인 정보 보호 모드가 필요한 경우 마이그레이션이 완료 된 후 클라이언트 버전 정책 규칙을 정의 하 여 이전 클라이언트 버전이 로그인 되지 않도록 합니다. 그런 다음 향상된 현재 상태 개인 정보 보호 모드를 설정합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 지정 된 서버 풀의 모든 사용자가 최신 클라이언트 버전을 설치할 때까지 Lync 2013 향상 된 현재 상태 개인 정보 보호 모드를 사용 하지 않도록 설정 합니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

