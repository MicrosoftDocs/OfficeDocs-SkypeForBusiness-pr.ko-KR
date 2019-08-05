---
title: 비즈니스용 Skype 서버 2015의 ConferenceMessageCount 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 이 테이블의 각 레코드는 한 명의 IM 회의에 있는 한 명의 사용자를 나타내고 해당 사용자가 보낸 메시지 수를 포함 합니다. 각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 하나.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196783"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="21591-104">비즈니스용 Skype 서버 2015의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="21591-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="21591-105">이 테이블의 각 레코드는 한 명의 IM 회의에 있는 한 명의 사용자를 나타내고 해당 사용자가 보낸 메시지 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21591-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="21591-106">각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 하나.</span><span class="sxs-lookup"><span data-stu-id="21591-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="21591-107">**열**</span><span class="sxs-lookup"><span data-stu-id="21591-107">**Column**</span></span>|<span data-ttu-id="21591-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="21591-108">**Data Type**</span></span>|<span data-ttu-id="21591-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="21591-109">**Key/Index**</span></span>|<span data-ttu-id="21591-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="21591-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21591-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="21591-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="21591-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="21591-112">datetime</span></span>  <br/> |<span data-ttu-id="21591-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="21591-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="21591-114">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="21591-114">Time of conference instance.</span></span> <span data-ttu-id="21591-115">회의 인스턴스를 고유 하 게 식별 하기 위해 **Sessionidseq** 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21591-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="21591-116">자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21591-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="21591-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="21591-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="21591-118">int</span><span class="sxs-lookup"><span data-stu-id="21591-118">int</span></span>  <br/> |<span data-ttu-id="21591-119">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="21591-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="21591-120">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="21591-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="21591-121">회의 인스턴스를 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21591-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="21591-122">자세한 내용은 [비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21591-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="21591-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="21591-123">**UserId**</span></span> <br/> |<span data-ttu-id="21591-124">int</span><span class="sxs-lookup"><span data-stu-id="21591-124">int</span></span>  <br/> |<span data-ttu-id="21591-125">외부</span><span class="sxs-lookup"><span data-stu-id="21591-125">Foreign</span></span>  <br/> |<span data-ttu-id="21591-126">이 사용자를 식별 하는 고유 번호로, [Users 테이블](users.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="21591-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="21591-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="21591-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="21591-128">smallint</span><span class="sxs-lookup"><span data-stu-id="21591-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="21591-129">이 회의가 진행 되는 동안이 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="21591-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

