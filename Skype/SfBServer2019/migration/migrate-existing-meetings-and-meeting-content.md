---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자 계정이 비즈니스용 Skype 서버 2019 서버로 이동 되 면 다음 정보가 해당 사용자 계정으로 이동 됩니다.
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813476"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="4b0a7-103">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4b0a7-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="4b0a7-104">사용자 계정이 비즈니스용 Skype 서버 2019 서버로 이동 되 면 다음 정보가 해당 사용자 계정으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="4b0a7-105">**사용자가 이미 예약한 모임**</span><span class="sxs-lookup"><span data-stu-id="4b0a7-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="4b0a7-106">여기에는 회의 디렉터리와 회의 데이터 이동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="4b0a7-107">**사용자의 PIN (개인 식별 번호)** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="4b0a7-108">사용자의 현재 PIN이 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="4b0a7-109">다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="4b0a7-110">**모임 콘텐츠**.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-110">**Meeting content**.</span></span> <span data-ttu-id="4b0a7-111">PowerPoint, 화이트 보드, 첨부 파일 또는 설문 데이터와 같이 모임 중에 공유 된 콘텐츠를 이동 하려면 **-MoveConferenceData** 매개 변수를 **이동-csuser** cmdlet의 일부로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a7-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

