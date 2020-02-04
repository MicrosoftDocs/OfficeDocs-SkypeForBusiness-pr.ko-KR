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
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹 에이전트 그룹 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

에이전트 그룹은 응답 그룹에 대 한 통화에 응답 하도록 지정 된 사용자 그룹으로 구성 됩니다. 에이전트 그룹을 만들 때 그룹에 할당 된 에이전트를 선택 하 고 라우팅 메서드, 에이전트에서 그룹에 로그인 할 수 있는지 여부 등의 추가 그룹 설정을 지정 합니다.

<div>


> [!NOTE]  
> 사용자가 Enterprise Voice를 사용 하도록 설정 해야 에이전트 그룹에 추가할 수 있습니다. 엔터프라이즈 음성에 대 한 사용자를 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 엔터프라이즈 음성 사용자 사용</A>을 참조 하세요.



</div>

<div>


> [!NOTE]  
> 온-프레미스 사용자만 에이전트 일 수 있습니다. 에이전트가 온-프레미스에서 온라인으로 이동 하는 경우 응답 그룹 통화는 해당 에이전트로 라우팅되지 않습니다.



</div>

그룹에 로그인 하 여 Lync Server에 로그인 하거나 로그 아웃 하는 것과는 다른 에이전트를 *공식 에이전트*라고 합니다. 정식 에이전트는 그룹으로 라우팅되는 통화를 수신 하기 전에 먼저 그룹에 로그인 해야 합니다. 이는 파트 시간 단위로 그룹에서 전화를 받는 에이전트에 유용할 수 있습니다. 공식 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Windows Internet Explorer 인터넷 브라우저를 열고 웹 페이지 콘솔을 표시 하 여 그룹에 로그인 하 고 로그 아웃 합니다.

그룹에 로그인 하거나 로그 아웃 하지 않은 에이전트를 *비공식적인 에이전트*라고 합니다. 비공식적인 에이전트는 Lync Server에 로그인 할 때 자동으로 그룹에 로그인 되며 그룹에서 로그 아웃할 수 없습니다.

<div>


> [!IMPORTANT]  
> 사용자를 응답 그룹 에이전트로 지정 하는 경우 개인 정보 모드를 사용 하도록 설정한 경우 "RGS 현재 감시자" 연락처를 검색 하 여 해당 연락처 목록에 추가 해야 한다는 것을 알립니다. 개인 정보 모드를 사용 하도록 설정 했지만 대화 상대 목록에 "RGS 현재 상태 감시자"가 없는 에이전트는 응답 그룹에 대 한 통화를 받을 수 없습니다. 개인 정보 모드를 사용할 수 없는 에이전트는 영향을 받지 않습니다.



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

