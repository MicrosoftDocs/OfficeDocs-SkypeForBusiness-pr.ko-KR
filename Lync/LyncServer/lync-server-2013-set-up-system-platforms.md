---
title: 'Lync Server 2013: 시스템 플랫폼 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Lync Server 2013에서 시스템 플랫폼 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

영구 채팅 서버의 배포를 시작 하기 전에 서버의 시스템 요구 사항을 충족 하는 하드웨어에 필요한 운영 체제를 설치 해야 합니다.

Lync Server 2013, 데이터베이스 서버, 파일 서버를 실행 하는 서버의 지원 되는 하드웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요. 지원 되는 운영 체제 및 데이터베이스 소프트웨어에 대 한 자세한 내용은 제공 가능성 설명서의 [Lync server 2013에서 서버 소프트웨어 및 인프라 지원을](lync-server-2013-server-software-and-infrastructure-support.md) 참조 하세요. Windows 업데이트 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md) 참조 하세요.

영구 채팅 서버 프런트 엔드 서버 **PersistentChatService**는 Lync Server 2013 Enterprise Edition 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 배포할 수 있습니다. Lync Server Enterprise Edition 프런트 엔드 서버에서는 collocated 될 수 없습니다. 영구 채팅 서버는 다른 Lync Server 역할과 마찬가지로 부트스트래퍼에 의해 배포 될 수 있습니다. **파일 업로드/다운로드에 대 한 영구 채팅 웹 서비스**와 채팅방 관리를 위한 **영구 채팅 웹 서비스** 는 Lync Server 2013 프런트 엔드 서버에 배포 된 웹 구성 요소입니다.

단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다. 총 8만 동시 사용자를 지 원하는 최대 4 개의 활성 프론트 엔드와 영구 채팅 서버 풀을 사용할 수 있습니다. 영구 채팅 백 엔드 서버 **PersistentChatStore**에는 채팅방과 범주가 저장 됩니다. 엔터프라이즈 버전 풀의 전용 SQL Server 백 엔드 서버에 **PersistentChatStore** 를 설치 하는 것이 좋습니다. collocating Lync Server 2013 백 엔드 서버와 **PersistentChatStore** 를 모두 동일한 SQL Server 인스턴스에서 지원 하지만

조직에 준수 지원이 필요한 경우 토폴로지 작성기를 사용 하 여 설치할 수 있습니다. 영구 채팅 서버 준수 서비스는 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 되어 있습니다. 규정을 준수 하려면 별도의 데이터베이스가 필요 합니다. 영구 채팅 서버의 준수 요구 사항에 대 한 자세한 내용은 계획 문서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하세요.

적어도 각 토폴로지에는 Lync Server 2013이 설치 된 서버와 SQL Server 데이터베이스 소프트웨어가 설치 된 서버가 필요 합니다. 토폴로지 작성기는 여러 영구 채팅 서버 풀을 지원 합니다. 모든 풀에 대해 수행 하는 것과 동일한 배포 지침에 따라 배포 설명서에 [Lync Server 2013을 배포](lync-server-2013-deploying-lync-server.md) 합니다.

Lync Server 2013 Standard Edition을 사용 하 여 영구 채팅 서버를 배포할 수도 있습니다. 이 경우 **PersistentChatService** 프런트 엔드 서버는 스탠더드 버전 서버에서 collocated 되며, 로컬 SQL Server Express 인스턴스에서 **PersistentChatStore** 백 엔드 서버를 배포할 수 있습니다.

<div>


> [!IMPORTANT]  
> 고가용성을 위해 영구 채팅 서버&nbsp;Standard Edition을 지원 하지 않습니다. 성능 및 확장성이 제한 됩니다. 또한 새로운 영구 채팅 서버&nbsp;Standard Edition 서버 배포만 지원 합니다. Lync Server 2010, 그룹 채팅 서버를 Lync Server 2013&nbsp;영구 채팅 서버&nbsp;표준 버전으로 업그레이드 하는 것은 지원 되지 않습니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 추가 서버 지원 및 요구 사항](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013에서 지원되는 하드웨어](lync-server-2013-supported-hardware.md)  
[Lync Server 2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md)  
[Lync Server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)  
[Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

