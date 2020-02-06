---
title: 비즈니스용 Skype 서버 2015의 위치 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 각 레코드는 E9-1-1 통화와 같이 비상 전화의 한 위치 참조를 나타냅니다.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815116"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8ceb6-103">비즈니스용 Skype 서버 2015의 위치 테이블</span><span class="sxs-lookup"><span data-stu-id="8ceb6-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ceb6-104">각 레코드는 E9-1-1 통화와 같이 비상 전화의 한 위치 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="8ceb6-105">**열**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-105">**Column**</span></span>|<span data-ttu-id="8ceb6-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-106">**Data Type**</span></span>|<span data-ttu-id="8ceb6-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-107">**Key/Index**</span></span>|<span data-ttu-id="8ceb6-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ceb6-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="8ceb6-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="8ceb6-110">datetime</span></span>  <br/> |<span data-ttu-id="8ceb6-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8ceb6-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8ceb6-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-112">Time of session request.</span></span> <span data-ttu-id="8ceb6-113">세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="8ceb6-114">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8ceb6-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="8ceb6-116">int</span><span class="sxs-lookup"><span data-stu-id="8ceb6-116">int</span></span>  <br/> |<span data-ttu-id="8ceb6-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8ceb6-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8ceb6-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-118">ID number to identify the session.</span></span> <span data-ttu-id="8ceb6-119">세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="8ceb6-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8ceb6-121">**위치**</span><span class="sxs-lookup"><span data-stu-id="8ceb6-121">**Location**</span></span> <br/> |<span data-ttu-id="8ceb6-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8ceb6-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="8ceb6-123">비상 전화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8ceb6-123">Location of emergency call.</span></span>  <br/> |
   

