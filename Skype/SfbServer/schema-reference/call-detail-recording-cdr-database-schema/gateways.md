---
title: 비즈니스용 Skype 서버 2015의 게이트웨이 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 게이트웨이 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN (공개 교환 통신망) 통화와 관련 된 게이트웨이 하나에 대 한 정보를 저장 합니다.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196742"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="93045-104">비즈니스용 Skype 서버 2015의 게이트웨이 테이블</span><span class="sxs-lookup"><span data-stu-id="93045-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="93045-105">게이트웨이 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="93045-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="93045-106">각 레코드는 데이터베이스에 레코드가 있는 PSTN (공개 교환 통신망) 통화와 관련 된 게이트웨이 하나에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="93045-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="93045-107">**열**</span><span class="sxs-lookup"><span data-stu-id="93045-107">**Column**</span></span>|<span data-ttu-id="93045-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="93045-108">**Data Type**</span></span>|<span data-ttu-id="93045-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="93045-109">**Key/Index**</span></span>|<span data-ttu-id="93045-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="93045-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93045-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="93045-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="93045-112">int</span><span class="sxs-lookup"><span data-stu-id="93045-112">int</span></span>  <br/> |<span data-ttu-id="93045-113">주요한</span><span class="sxs-lookup"><span data-stu-id="93045-113">Primary</span></span>  <br/> |<span data-ttu-id="93045-114">이 게이트웨이를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="93045-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="93045-115">**게이트웨이와**</span><span class="sxs-lookup"><span data-stu-id="93045-115">**Gateway**</span></span> <br/> |<span data-ttu-id="93045-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93045-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="93045-117">게이트웨이 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93045-117">Gateway name.</span></span>  <br/> |
   

