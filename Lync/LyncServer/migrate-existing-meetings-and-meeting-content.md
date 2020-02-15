---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a6036421dd84f466df0f2353b6d5264e0680c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="123db-102">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="123db-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="123db-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="123db-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="123db-104">사용자 계정을 Lync Server 2010에서 Lync Server 2013 서버로 이동 하면 해당 사용자 계정을 사용 하 여 다음 정보가 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="123db-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="123db-p101">**사용자가 이미 예약한 모임**. 회의 디렉터리 및 회의 데이터 이동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="123db-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="123db-p102">**사용자의 개인 ID 번호(PIN)**. 사용자의 현재 PIN은 만료되거나 사용자가 새 PIN을 요청할 때까지 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="123db-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="123db-109">다음과 같은 사용자 계정 정보는 새 서버로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="123db-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="123db-p103">**모임 콘텐츠**. PowerPoint, 화이트보드, 첨부 파일, 설문 데이터 등 모임 중에 공유되는 콘텐츠를 이동하려면 **Move-CsUser** cmdlet의 일부분으로 **-MoveConferenceData** 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="123db-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

