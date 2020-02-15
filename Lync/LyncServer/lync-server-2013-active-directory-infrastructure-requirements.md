---
title: 'Lync Server 2013: Active Directory 인프라 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 Active Directory 인프라 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비 프로세스를 시작 하기 전에 Active Directory 인프라가 다음 필수 구성 요소를 충족 하는지 확인 합니다.

  - Lync Server를 배포 하는 포리스트에서 모든 글로벌 카탈로그 서버를 포함 하는 모든 도메인 컨트롤러는 다음 운영 체제 중 하나를 실행 합니다.
    
      - Windows Server 2012 R2 운영 체제
    
      - Windows Server 2012 운영 체제
    
      - Windows Server 2008 R2 운영 체제
    
      - Windows Server 2008 운영 체제
    
      - Windows Server 2008 Enterprise 32 비트
    
      - 32비트 또는 64비트 버전의 Windows Server 2003 R2 운영 체제
    
      - 32 비트 또는 64 비트 버전의 Windows Server 2003 운영 체제

  - Lync Server를 배포 하는 모든 도메인은 Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 또는 Windows Server 2003 이상의 도메인 기능 수준으로 발생 합니다.

  - Lync Server를 배포 하는 포리스트는 Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 또는 Windows Server 2003 이상에 해당 하는 포리스트 기능 수준으로 발생 합니다.
    
    <div>
    

    > [!NOTE]  
    > 도메인 또는 포리스트 기능 수준을 변경 하려면 TechNet 라이브러리에서 "도메인 및 포리스트 기능 수준 올리기"를 참조 하세요 <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.

    
    </div>

  - 글로벌 카탈로그는 Lync Server 컴퓨터나 사용자를 배포 하는 모든 도메인에 배포 됩니다.

Lync Server 2013는 windows Server 2012 R2, Windows Server 2012, Windows server 2008 R2, Windows Server 2008 및 Windows Server 2003 운영 체제의 유니버설 그룹을 지원 합니다. 유니버설 그룹의 구성원은 도메인 트리 또는 포리스트에 있는 도메인의 다른 그룹 및 계정을 포함할 수 있고 도메인 트리 또는 포리스트에 있는 도메인의 사용 권한이 할당될 수 있습니다. 관리자 위임과 함께 유니버설 그룹을 지원 하면 Lync Server 배포를 간편 하 게 관리할 수 있습니다. 예를 들어 한 도메인을 다른 도메인에 추가하지 않아도 관리자가 둘 다 관리할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

