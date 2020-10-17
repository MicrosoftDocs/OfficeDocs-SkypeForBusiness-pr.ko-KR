---
title: Lync Server 2013 파일 저장소 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c424693b71f516b1fcb27523fbcb27b3a514176
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507284"
---
# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013의 파일 저장소 지원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-16_

Lync Server 2013에서는 모든 파일 저장소에 대해 동일한 파일 저장소를 사용 합니다. 파일 저장소 지원에는 다음이 포함 됩니다.

  - DFS (분산 파일 시스템)를 포함 하는 DAS (직접 연결 된 저장소) 또는 SAN (저장 영역 네트워크), 파일 저장용 RAID (독립 디스크)에 있는 파일 공유 저장소 요구 사항에 대 한 자세한 내용은 계획 설명서에서 lync server [2013의 디렉터](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 에 대 한 [프런트 엔드 서버, 인스턴트 메시징 및 현재 2013 상태에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) 참조 하세요. Windows Server 용 DFS 2008 운영 체제에 대 한 자세한 내용은 Windows Server 2008에 대 한 DFS 단계별 가이드를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) .

  - 파일 공유에 대 한 공유 클러스터 공유 클러스터를 사용 하는 경우 Windows Server 2008 또는 Windows Server 2008 R2를 실행 하는 클러스터 서버를 사용 해야 합니다. 이전 버전의 Windows를 실행 하는 클러스터 서버를 사용 하면 사용 권한 문제가 발생 하 여 일부 기능을 사용 하지 못할 수 있습니다. 클러스터 관리자를 사용 하 여 파일 공유를 만듭니다. 클러스터 관리자 사용에 대 한 자세한 내용은 Microsoft 기술 자료 문서 284838, "Cluster.exe를 사용 하 여 서버 클러스터 파일 공유를 만드는 방법"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) .

</div>

<span> </span>

</div>

</div>

</div>

