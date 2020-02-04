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
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="2e8db-102">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2e8db-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e8db-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2e8db-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2e8db-104">사용자 계정이 Lync Server 2010에서 Lync Server 2013 서버로 이동 되 면 다음 정보가 해당 사용자 계정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="2e8db-105">**사용자가 이미 예약한 모임**</span><span class="sxs-lookup"><span data-stu-id="2e8db-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="2e8db-106">여기에는 회의 디렉터리와 회의 데이터 이동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="2e8db-107">**사용자의 PIN (개인 식별 번호)** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="2e8db-108">사용자의 현재 PIN이 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="2e8db-109">다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="2e8db-110">**모임 콘텐츠**.</span><span class="sxs-lookup"><span data-stu-id="2e8db-110">**Meeting content**.</span></span> <span data-ttu-id="2e8db-111">모임 중에 공유 된 콘텐츠 (예: PowerPoint, 화이트 보드, 첨부 파일 또는 설문 데이터)를 이동 하려면 **CsUser** cmdlet의 일부로 **-MoveConferenceData** 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8db-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

