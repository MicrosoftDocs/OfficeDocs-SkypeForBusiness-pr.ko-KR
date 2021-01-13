---
title: Tenants 테이블
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 테이블은 다양한 테넌트 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 테넌트를 나타냅니다.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831718"
---
# <a name="tenants-table"></a><span data-ttu-id="86046-104">Tenants 테이블</span><span class="sxs-lookup"><span data-stu-id="86046-104">Tenants table</span></span>
 
<span data-ttu-id="86046-p102">Tenants 테이블은 다양한 테넌트 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 테넌트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86046-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86046-107">온-프레미스 배포의 경우 CDR은 기본 제공되는 테넌트 ID를 사용하여 공용 IM 연결, 페더레이션 및 익명과 같은 서로 다른 인증 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86046-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="86046-108">**열**</span><span class="sxs-lookup"><span data-stu-id="86046-108">**Column**</span></span>|<span data-ttu-id="86046-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="86046-109">**Data Type**</span></span>|<span data-ttu-id="86046-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="86046-110">**Key/Index**</span></span>|<span data-ttu-id="86046-111">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="86046-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="86046-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="86046-112">**TenantId**</span></span> <br/> |<span data-ttu-id="86046-113">int</span><span class="sxs-lookup"><span data-stu-id="86046-113">int</span></span>  <br/> |<span data-ttu-id="86046-114">Primary</span><span class="sxs-lookup"><span data-stu-id="86046-114">Primary</span></span>  <br/> |<span data-ttu-id="86046-115">이 테넌트 ID를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="86046-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="86046-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="86046-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="86046-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="86046-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="86046-118">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86046-118">Allowed values:</span></span> <br/>  <span data-ttu-id="86046-119">000000000-0000-0000-0000-00000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="86046-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="86046-120">000000000-0000-0000-0000-000000000001 - 페더화</span><span class="sxs-lookup"><span data-stu-id="86046-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="86046-121">000000000-0000-0000-0000-000000000002 - 익명</span><span class="sxs-lookup"><span data-stu-id="86046-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="86046-122">000000000-0000-0000-0000-000000000003 - 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="86046-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

