---
title: 범주를 사용 하 여 영구 채팅 서버 관리
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eecae8ff3c84861df7c624e8ca5b958c4fb53696
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>범주를 사용 하 여 영구 채팅 서버 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-01_

영구 채팅 서버 배포에서는 많은 동시 영구 대화방을 호스팅할 수 있습니다. 채팅방은 서버에서 범주 집합으로 구성할 수 있습니다. 각 채팅방은 범주 하나에 속하며 해당 범주의 일부 설정을 상속합니다. 이러한 구성에서는 대화를 해당 업무상 용도에 따라 식별할 수 있는 유용한 구조가 작성되며, 위임된 관리 및 간편한 관리를 용이하게 수행할 수 있도록 합니다.

<div>


> [!NOTE]  
> 대화방의 여러 관리 기능을 사용자에 게 제공 되는 Lync 클라이언트 (영구 채팅)를 실행 하는 컴퓨터에서 사용할 수 있지만 <STRONG>cspersistentchatadministrator</STRONG> 역할의 영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들거나 관리 해야 합니다.



</div>

영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 하 고 조직의 사용자에 대 한 대화방에 대 한 액세스를 디자인 합니다.

하나 이상의 대화방을 관리 하는 기능을 가진 영구 대화방 관리자는 Lync 클라이언트를 사용 하 여 대화방 관리 웹 응용 프로그램을 실행 하 여 대화방을 만들고 관리할 수 있습니다 (또는 고객이 사용자 지정 솔루션 및 워크플로를 만들 수 있음). 영구 채팅 관리자는 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 대화방을 만들고 관리할 수도 있습니다.

<div>


> [!NOTE]  
> 영구 채팅방은 영구 채팅 범주와 같은 이름을 사용할 수 없습니다.



</div>

채팅방 관리자는 방 범주 변경을 제외한 모든 채팅방 속성을 변경할 수 있습니다. 채팅방 관리자가 다음과 같은 작업을 수행하지 못하도록 제한할 수는 없습니다.

  - 채팅방 비활성화

  - 채팅방 이름 변경

  - 채팅방 설명 변경

  - 채팅방 유형 변경(강당/일반)

  - 방 개인 정보 변경(공개/비공개/비밀)

  - 구성원 추가 또는 제거

  - 채팅방 관리자 추가 또는 제거

  - 추가 기능 추가 또는 제거

  - 초대 등의 설정 변경(범주에서 허용되는 경우)

<div>

## <a name="delegated-administration"></a>위임된 관리

범주를 올바르게 사용 하면 영구 대화방을 만들고 관리 하기가 훨씬 쉬워졌습니다. 영구 채팅 관리자는 각 범주에 대해 **Allowedmembers** 및 **작성자** 를 정의할 수 있으며, 범주에 만들어지는 모든 채팅방에 적용할 기본 대화방 설정 및 동작도 정의할 수 있습니다. 영구 채팅 관리자 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.

범주의 작성자로 식별되는 사용자, OU(조직 구성 단위) 및 사용자 그룹은 해당 범주에서 대화방을 만들 수 있는 개인과 그룹입니다. 이들은 범주를 만든 후 범주의 **AllowedMembers** 목록에서 사용자, OU 및 사용자 그룹을 대화방을 관리하고 대화방에 참가할 관리자 및 구성원으로 선택할 수 있습니다.

범주 안에 만들어지는 대화방은 범주에 의해 적용되는 정책 및 설정(대화방 구성원, 대화방 관리자, 파일 업로드 허용 여부, 초대 전송 여부 등)을 따릅니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

