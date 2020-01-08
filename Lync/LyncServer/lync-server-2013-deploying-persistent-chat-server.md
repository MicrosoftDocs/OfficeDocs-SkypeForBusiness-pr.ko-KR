---
title: 'Lync Server 2013: 영구 채팅 서버 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 서버 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-31_

Lync Server 2013, 영구 채팅 서버는 Lync Server 2013 인프라의 일부입니다.

영구 채팅 서버를 배포 하려면 다음을 수행 해야 합니다.

  - 토폴로지 작성기를 사용 하 여 배포 하려는 토폴로지와 구성 요소를 정의 하거나 가져온 다음 게시 합니다.

  - 영구 채팅 서버 구성 요소를 배포 하기 위한 환경을 준비 합니다.

  - 배포를 위해 영구 채팅 서버 구성 요소를 설치 하 고 구성 합니다.

영구 채팅 서버는 Lync Server 2013 Enterprise Edition을 별도의 풀로 사용할 수 있습니다 (Enterprise Edition 프런트 엔드 서버를 사용 하 여 collocated가 아님). 영구 채팅 서버에는 채팅방 콘텐츠 및 기타 관련 메타 데이터를 저장 하기 위해 Enterprise Edition 풀에 SQL Server 백 엔드 서버가 필요 합니다. 동일한 SQL Server 인스턴스의 collocating Lync Server 2013 백 엔드 서버 및 **PersistentChatStore** 이 지원 되기는 하지만 전용 SQL Server 백 엔드 서버에 **PersistentChatStore** 를 설치 하는 것이 좋습니다.

또한 영구 채팅 서버는 Lync Server 2013 Standard Edition을 사용 하 여 배포할 수 있습니다. 이 경우 **PersistentChatService** 프런트 엔드 서버는 표준 버전 컴퓨터에서 collocated 하 고 **PersistentChatStore** 백 엔드 서버는 로컬 SQL Server Express 인스턴스에 배포 될 수 있습니다.

지원 되는 배치 구성에 대 한 자세한 내용은 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.

<div>


> [!IMPORTANT]  
> 영구 채팅 서버&nbsp;Standard Edition에 대해 고가용성을 지원 하지 않습니다. 성능 및 확장성이 제한 됩니다. 또한, 새로운 영구 채팅 서버&nbsp;Standard Edition 서버만 지원 합니다. Lync Server 2010, 그룹 채팅 서버를 Lync Server 2013&nbsp;영구 채팅 서버&nbsp;표준 버전으로 업그레이드 하는 것은 지원 되지 않습니다.



</div>

조직에 준수 지원이 필요한 경우 영구 채팅 서버 프런트 엔드 서버에 영구 채팅 서버 준수 서비스를 설치할 수 있습니다. 규정을 준수 하려면 별도의 데이터베이스가 필요 합니다.

적어도 각 토폴로지에는 Lync Server 2013이 설치 된 서버와 SQL Server 데이터베이스 소프트웨어가 설치 된 서버가 필요 합니다.

토폴로지 작성기를 사용 하 여 Lync Server 2013 배포에 영구 채팅 서버를 추가 합니다. 토폴로지 작성기를 사용 하 여 하나 이상의 영구 채팅 서버 풀을 추가 하도록 선택할 수 있습니다. 모든 풀에 대해 할 수 있는 것과 동일한 배포 지침에 따라 여러 영구 채팅 서버 풀을 배포 합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하세요.

영구 채팅 서버를 설치 하는 데 사용할 수 있는 토폴로지와 기술 및 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) 에서 지속적인 채팅 서버 작동 방법, 계획 설명서의 [lync Server 2013에서 영구 채팅 서버가 실행 되는 방식](lync-server-2013-how-persistent-chat-server-works.md) , 배포 설명서 또는 운영 설명서의 Lync [server 2013의 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 에 대 한 계획을 참조 하세요.

인증서를 획득 하 고 SQL Server 데이터베이스를 만들고 파일 저장소를 만드는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하세요.

단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다. 총 8만 동시 사용자를 지 원하는 최대 4 개의 활성 프런트 엔드 서버와 영구 채팅 서버 풀을 사용할 수 있습니다.

영구 채팅 서버는 가상 서버 에서도 지원 됩니다. 가상 서버는 실제 서버의 사양과 일치 하는 경우 최대 2만 동시 사용자를 지원할 수 있습니다.

<div>


> [!IMPORTANT]  
> 파일 시스템 보안을 강화 하기 위해 영구 채팅 서버를 NTFS 파일 시스템에 설치 해야 합니다. FAT32는 영구 채팅 서버용으로 지원 되는 파일 시스템이 아닙니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013의 영구 채팅 서버용 배포 검사 목록](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013에서 영구 채팅 서버에 대한 시스템 및 인프라 설정](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Lync Server 2013에서 배포에 영구 채팅 서버 추가](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Lync Server 2013에서 영구 채팅 서버 설치](lync-server-2013-installing-persistent-chat-server.md)

  - [Lync Server 2013에서 영구 채팅 관리자 추가](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Lync Server 2013에서 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server.md)

  - [Windows PowerShell cmdlet으로 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013에서 Windows PowerShell cmdlet으로 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2013의 영구 채팅 서버 장애 조치(failover) 및 장애 복구(failback)](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

