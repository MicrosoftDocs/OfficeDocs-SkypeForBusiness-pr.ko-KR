---
title: 비즈니스용 Skype 서버의 Gateways 테이블
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 테이블은 지원 테이블입니다. 각 레코드는 데이터베이스에 레코드가 있는 PSTN(Public Switched Telephone Network) 통화에 관련된 하나의 게이트웨이에 대한 정보를 저장합니다.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821588"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0c0eb-104">비즈니스용 Skype 서버의 Gateways 테이블</span><span class="sxs-lookup"><span data-stu-id="0c0eb-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0c0eb-105">Gateways 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="0c0eb-106">각 레코드는 데이터베이스에 레코드가 있는 PSTN(Public Switched Telephone Network) 통화에 관련된 하나의 게이트웨이에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="0c0eb-107">**열**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-107">**Column**</span></span>|<span data-ttu-id="0c0eb-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-108">**Data Type**</span></span>|<span data-ttu-id="0c0eb-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-109">**Key/Index**</span></span>|<span data-ttu-id="0c0eb-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c0eb-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="0c0eb-112">int</span><span class="sxs-lookup"><span data-stu-id="0c0eb-112">int</span></span>  <br/> |<span data-ttu-id="0c0eb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0c0eb-113">Primary</span></span>  <br/> |<span data-ttu-id="0c0eb-114">이 게이트웨이를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="0c0eb-115">**게이트웨이**</span><span class="sxs-lookup"><span data-stu-id="0c0eb-115">**Gateway**</span></span> <br/> |<span data-ttu-id="0c0eb-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c0eb-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="0c0eb-117">게이트웨이 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0eb-117">Gateway name.</span></span>  <br/> |
   

