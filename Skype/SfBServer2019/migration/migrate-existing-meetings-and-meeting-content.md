---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 사용자 계정이 비즈니스용 Skype 서버 2019 서버로 이동 되 면 다음 정보가 해당 사용자 계정으로 이동 됩니다.
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191148"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f1723-103">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f1723-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="f1723-104">사용자 계정이 비즈니스용 Skype 서버 2019 서버로 이동 되 면 다음 정보가 해당 사용자 계정으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="f1723-105">**사용자가 이미 예약한 모임**</span><span class="sxs-lookup"><span data-stu-id="f1723-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="f1723-106">여기에는 회의 디렉터리와 회의 데이터 이동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="f1723-107">**사용자의 PIN (개인 식별 번호)** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="f1723-108">사용자의 현재 PIN이 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="f1723-109">다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="f1723-110">**모임 콘텐츠**.</span><span class="sxs-lookup"><span data-stu-id="f1723-110">**Meeting content**.</span></span> <span data-ttu-id="f1723-111">PowerPoint, 화이트 보드, 첨부 파일 또는 설문 데이터와 같이 모임 중에 공유 된 콘텐츠를 이동 하려면 **-MoveConferenceData** 매개 변수를 **이동-csuser** cmdlet의 일부로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1723-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

