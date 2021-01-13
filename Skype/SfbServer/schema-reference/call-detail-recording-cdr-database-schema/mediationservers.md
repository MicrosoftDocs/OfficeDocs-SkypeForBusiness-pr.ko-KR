---
title: MediationServers 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 테이블은 지원 테이블입니다. 각 레코드에는 데이터베이스에 레코드가 있는 통화와 관련된 중재 서버 하나에 대한 정보가 저장됩니다.
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814768"
---
# <a name="mediationservers-table"></a><span data-ttu-id="7ba7f-104">MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="7ba7f-104">MediationServers table</span></span>
 
<span data-ttu-id="7ba7f-105">MediationServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="7ba7f-106">각 레코드에는 데이터베이스에 레코드가 있는 통화와 관련된 중재 서버 하나에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="7ba7f-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-107">**Column**</span></span>|<span data-ttu-id="7ba7f-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-108">**Data Type**</span></span>|<span data-ttu-id="7ba7f-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-109">**Key/Index**</span></span>|<span data-ttu-id="7ba7f-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ba7f-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="7ba7f-112">int</span><span class="sxs-lookup"><span data-stu-id="7ba7f-112">int</span></span>  <br/> |<span data-ttu-id="7ba7f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7ba7f-113">Primary</span></span>  <br/> |<span data-ttu-id="7ba7f-114">이 중재 서버를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="7ba7f-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="7ba7f-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="7ba7f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7ba7f-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="7ba7f-117">중재 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba7f-117">Mediation Server name.</span></span>  <br/> |
   

