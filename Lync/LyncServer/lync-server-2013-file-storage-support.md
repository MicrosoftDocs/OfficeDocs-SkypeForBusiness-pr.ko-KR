---
title: Lync Server 2013 파일 저장소 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013의 파일 저장소 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-16_

Lync Server 2013는 모든 파일 저장소에 동일한 파일 저장소를 사용 합니다. 파일 저장소 지원에는 다음이 포함 됩니다.

  - 파일 저장소 (분산 파일 시스템) 또는 DFS (저장 영역 네트워크)를 포함 하 여 파일을 공유 하는 파일과 저장소에 대 한 독립 디스크 (RAID)의 중복 배열입니다. 저장소 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 프런트 엔드 서버, 메신저 대화, 현재 상태](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , 그리고 계획 설명서의 [lync Server 2013에서 디렉터에 대 한 하드웨어 및 소프트웨어 요구](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 사항에 대해 알아보세요. Windows Server 용 DFS 2008 운영 체제에 대 한 자세한 내용은 Windows Server 2008의 DFS for 단계별 가이드를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).

  - 파일 공유에 대 한 공유 클러스터 공유 클러스터를 사용 하는 경우 Windows Server 2008 또는 Windows Server 2008 R2를 실행 하는 클러스터 서버를 사용 해야 합니다. 이전 버전의 Windows를 실행 하는 클러스터 서버를 사용 하면 사용 권한 문제가 발생 하 여 일부 기능을 사용할 수 없게 될 수 있습니다. 클러스터 관리자를 사용 하 여 파일 공유를 만듭니다. 클러스터 관리자 사용에 대 한 자세한 내용은 Microsoft 기술 자료 문서 284838, "cluster.exe를 사용 하 여 서버 클러스터 파일 공유를 만드는 방법"을 참조 [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)하세요.

</div>

<span> </span>

</div>

</div>

</div>

