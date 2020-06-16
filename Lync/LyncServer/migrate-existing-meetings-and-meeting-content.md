---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>기존 모임 및 모임 콘텐츠 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

사용자 계정을 Lync Server 2010에서 Lync Server 2013 서버로 이동 하면 해당 사용자 계정을 사용 하 여 다음 정보가 이동 됩니다.

  - **Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.

  - **User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.

다음과 같은 사용자 계정 정보는 새 서버로 이동하지 않습니다.

  - **Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.

</div>

<span> </span>

</div>

</div>

</div>

