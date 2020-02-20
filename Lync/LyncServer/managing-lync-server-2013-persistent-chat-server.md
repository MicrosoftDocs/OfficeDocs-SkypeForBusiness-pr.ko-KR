---
title: Lync Server 2013, 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe49370fe42d1ca721f9f767bdb87ab9b7b3c1d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a>Lync Server 2013, 영구 채팅 서버 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-11_

Lync Server 2013, 영구 채팅 서버를 사용 하 여 여러 사용자가 텍스트, 링크 및 파일을 비롯 한 특정 항목에 대 한 콘텐츠를 게시 하 고 액세스 하는 대화에 참가할 수 있습니다. 사용자가 세션 중에 실시간으로 통신할 수 있지만 각 세션의 콘텐츠는 영구적 이며 세션이 종료 된 후에도 계속 사용할 수 있습니다.

영구 대화방의 내용은 긴 메시지, 즉 *스토리*, 이모티콘을 비롯 하 여 하이퍼링크, 이모티콘 및 업로드 된 문서를 포함할 수 있지만 주로 짧은 텍스트 메시지로 구성 됩니다.

<div>


> [!NOTE]  
> 파일 업로드 및 다운로드는 Lync 2013 클라이언트에서 지원 되지 않습니다. 그러나 Lync Server 2013, 영구 채팅 서버에서는 여전히 지원 됩니다. 레거시 그룹 채팅 클라이언트가 파일을 게시 하 고 볼 수는 있지만 Lync 2013 클라이언트를 통해 동일한 대화방에 액세스 하는 경우에는 파일에 액세스할 수 없습니다.



</div>

채팅방에 대한 액세스는 구성원 자격 목록에 의해 제어됩니다. 전체 채팅방 내용은 모든 구성원이 시간별 검토 또는 전체 텍스트 검색에 이용할 수 있습니다. 영구 채팅 클라이언트 사용에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 클라이언트 계획](lync-server-2013-planning-for-clients.md) 및 배포 설명서의 [lync server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md) 를 참조 하세요.

조직에 대해 영구 채팅 서버를 설정 하는 경우 배포 중에 초기 구성을 지정 합니다. 그러나 영구 채팅 서버 지원을 구현 하는 방법을 변경 하려는 경우가 있을 수 있습니다. 예를 들어 조직 내 특정 팀 또는 그룹에 대해 영구 채팅 서버 지원 및 컨트롤을 다르게 설정 해야 할 수 있습니다. 이 섹션에서는 영구 채팅 서버 배포를 사용자 지정 하는 데 도움이 되는 정보와 절차를 제공 합니다. 영구 채팅 서버에 대해 구성할 수 있는 기능에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버에 대 한 조직의 요구 사항 정의](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) 및 계획 설명서, 배포 설명서 또는 작업 설명서의 [lync Server 2013에서 영구 채팅 서버의 작동 방식을](lync-server-2013-how-persistent-chat-server-works.md) 참조 하십시오. Lync Server 2013에 대해 영구 채팅 서버를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 " [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md) "를 참조 하십시오.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식](lync-server-2013-how-persistent-chat-server-works.md)

  - [범주를 사용 하 여 영구 채팅 서버 관리](using-categories-to-administer-persistent-chat-server.md)

  - [영구 채팅 구성원 자격 이해](understanding-persistent-chat-membership.md)

  - [영구 채팅 서버 모범 사례](persistent-chat-server-best-practices.md)

  - [Lync Server 2013에서 범주, 대화방 및 추가 기능 관리](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [Lync Server 2013에서 영구 채팅 사용자 액세스 관리](lync-server-2013-managing-persistent-chat-user-access.md)

  - [Lync Server 2013의 영구 채팅 시스템 운영 및 유지 관리](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

