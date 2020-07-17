---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자 계정을 비즈니스용 Skype 서버 2019 서버로 이동 하면 다음 정보가 해당 사용자 계정으로 이동 됩니다.
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752690"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f575b-103">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f575b-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="f575b-104">사용자 계정을 비즈니스용 Skype 서버 2019 서버로 이동 하면 다음 정보가 해당 사용자 계정으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="f575b-105">**사용자가 이미 예약한 모임**.</span><span class="sxs-lookup"><span data-stu-id="f575b-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="f575b-106">회의 디렉터리 및 회의 데이터 이동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="f575b-107">**사용자의 PIN (개인 id 번호)** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="f575b-108">사용자의 현재 PIN은 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="f575b-109">다음과 같은 사용자 계정 정보는 새 서버로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="f575b-110">**모임 콘텐츠**.</span><span class="sxs-lookup"><span data-stu-id="f575b-110">**Meeting content**.</span></span> <span data-ttu-id="f575b-111">PowerPoint, 화이트 보드, 첨부 파일 또는 설문 데이터와 같이 모임 중에 공유 되는 콘텐츠를 이동 하려면 **MoveConferenceData** 매개 변수를 **csuser** cmdlet의 일부로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f575b-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

