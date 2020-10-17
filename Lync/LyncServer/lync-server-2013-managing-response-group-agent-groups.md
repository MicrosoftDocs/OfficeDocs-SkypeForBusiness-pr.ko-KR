---
title: 'Lync Server 2013: 응답 그룹 에이전트 그룹 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e0c0c022b1925831737d70a10c2a193b9732bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497955"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹 에이전트 그룹 관리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

에이전트 그룹은 응답 그룹에 대한 통화에 응답하도록 지정된 사용자 그룹으로 구성됩니다. 에이전트 그룹을 만들 때 그룹에 할당되는 에이전트를 선택하고 라우팅 방법 및 에이전트가 그룹에 로그인하고 그룹에서 로그아웃할 수 있는지 여부와 같은 추가 그룹 설정을 지정합니다.

<div>


> [!NOTE]  
> 사용자가 Enterprise Voice를 사용 하도록 설정 해야 에이전트 그룹에 추가할 수 있습니다. 사용자가 Enterprise Voice를 사용할 수 있도록 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 사용자에 게 Enterprise Voice 사용</A>을 사용 하도록 설정을 참조 하십시오.



</div>

<div>


> [!NOTE]  
> 온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.



</div>

Lync Server에 로그인 하거나 외부에서 제외 해야 하는 에이전트를 *공식 에이전트*라고 합니다. 공식 에이전트는 그룹에 로그인해야 그룹에 라우팅된 통화를 수신할 수 있습니다. 이 기능은 비상근직으로 그룹의 호출에 응답하는 에이전트에 유용할 수 있습니다. 공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하는 방법으로 그룹에 로그인 하 고 사용자를 제외 합니다.

그룹에 로그인하거나 그룹에서 로그아웃하지 않는 에이전트를 *비공식 에이전트*라고 합니다. 사용자가 Lync Server에 로그인 할 때 비공식 에이전트가 그룹에 자동으로 로그인 되며, 그룹에서 로그 아웃할 수 없습니다.

<div>


> [!IMPORTANT]  
> 사용자를 응답 그룹 에이전트로 할당할 때 해당 사용자가 개인 정보 보호 모드를 사용하도록 설정한 경우 "RGS Presence Watcher" 대화 상대를 검색하여 대화 상대 목록에 추가해야 합니다. 개인 정보 보호 모드를 사용하도록 설정한 에이전트의 대화 상대 목록에 "RGS Presence Watcher"가 없으면 응답 그룹으로 걸려 온 전화를 받을 수 없습니다. 개인 정보 보호 모드를 사용하도록 설정하지 않은 에이전트는 영향을 받지 않습니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 에이전트 그룹 만들기 또는 수정](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Lync Server 2013에서 에이전트 그룹 삭제](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

