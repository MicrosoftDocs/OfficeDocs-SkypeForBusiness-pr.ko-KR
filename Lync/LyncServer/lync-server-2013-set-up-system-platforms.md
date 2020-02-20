---
title: 'Lync Server 2013: 시스템 플랫폼 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec8b2e923b4c0815449ce7fd7beb2624fe728623
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Lync Server 2013에서 시스템 플랫폼 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

영구 채팅 서버 배포를 시작 하기 전에 서버에 대 한 시스템 요구 사항을 충족 하는 하드웨어에 필요한 운영 체제를 설치 해야 합니다.

Lync Server 2013, 데이터베이스 서버 및 파일 서버를 실행 하는 서버에 대해 지원 되는 하드웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013에](lync-server-2013-supported-hardware.md) 사용할 수 있는 하드웨어를 참조 하십시오. 지원 되는 운영 체제 및 데이터베이스 소프트웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 서버 소프트웨어 및 인프라 지원을](lync-server-2013-server-software-and-infrastructure-support.md) 참조 하십시오. Windows 업데이트 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md) 참조 하세요.

영구 채팅 서버 프런트 엔드 서버 **PersistentChatService**는 Lync Server 2013 Enterprise Edition 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 배포할 수 있습니다. Lync Server Enterprise Edition 프런트 엔드 서버에서는 배치 된를 사용할 수 없습니다. 영구 채팅 서버는 다른 Lync Server 역할과 마찬가지로 부트스트래퍼에서 배포할 수 있습니다. **파일 업로드/다운로드를 위한 영구 채팅 웹 서비스**와 대화방 **용 영구 채팅 웹 서비스** 는 Lync Server 2013 프런트 엔드 서버에 배포 된 웹 구성 요소입니다.

단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다. 총 8만 동시 사용자를 지 원하는 최대 4 개의 활성 프런트 엔드와 함께 영구 채팅 서버 풀을 사용할 수 있습니다. 영구 채팅 백 엔드 서버인 **PersistentChatStore**에는 대화방 및 범주가 저장 됩니다. **PersistentChatStore** 는 Enterprise Edition 풀의 전용 SQL Server 백 엔드 서버에 설치 하는 것이 좋습니다. 배치 Lync Server 2013 백 엔드 서버와 **PersistentChatStore** 는 동일한 SQL Server 인스턴스에서 지원 되지만

조직에서 준수 지원이 필요한 경우 토폴로지 작성기를 사용 하 여 설치할 수 있습니다. 영구 채팅 서버 준수 서비스가 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다. 준수용으로 별도의 데이터베이스가 필요합니다. 영구 채팅 서버에 대 한 준수 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.

적어도 각 토폴로지에는 Lync Server 2013이 설치 된 서버와 SQL Server 데이터베이스 소프트웨어가 설치 된 서버가 필요 합니다. 토폴로지 작성기는 여러 영구 채팅 서버 풀을 지원 합니다. 배포 설명서의 모든 풀에서 [Lync server 2013을 배포](lync-server-2013-deploying-lync-server.md) 하는 것과 동일한 배포 지침을 수행 하 여 여러 영구 채팅 서버 풀을 배포 합니다.

Lync Server 2013 Standard Edition과 함께 영구 채팅 서버를 배포할 수도 있습니다. 이 경우 **PersistentChatService** 프런트 엔드 서버가 Standard Edition 서버에서 배치 된 되며, 로컬 SQL Server Express 인스턴스에 **PersistentChatStore** 백 엔드 서버를 배포할 수 있습니다.

<div>


> [!IMPORTANT]  
> 고가용성을 위한 영구 채팅 서버&nbsp;Standard Edition은 지원 되지 않습니다. 성능 및 확장 기능은 제한됩니다. 또한 새 영구 채팅 서버&nbsp;Standard Edition 서버 배포만 지원 합니다. Lync Server 2010, 그룹 채팅 서버를 Lync Server 2013&nbsp;영구 채팅 서버&nbsp;Standard Edition으로 업그레이드 하는 것은 지원 되지 않습니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 추가 서버 지원 및 요구 사항](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md)  
[Lync Server 2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md)  
[Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)  
[Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

