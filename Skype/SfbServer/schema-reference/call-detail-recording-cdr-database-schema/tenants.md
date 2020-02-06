---
title: Tenants 테이블
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814856"
---
# <a name="tenants-table"></a><span data-ttu-id="f4bae-104">Tenants 테이블</span><span class="sxs-lookup"><span data-stu-id="f4bae-104">Tenants table</span></span>
 
<span data-ttu-id="f4bae-105">테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f4bae-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="f4bae-106">테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4bae-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4bae-107">온-프레미스 배포에서 CDR는 빌드에 테 넌 트 ID를 사용 하 여 공용 IM 연결, 페더레이션 및 익명 등의 다른 인증 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4bae-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="f4bae-108">**열**</span><span class="sxs-lookup"><span data-stu-id="f4bae-108">**Column**</span></span>|<span data-ttu-id="f4bae-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="f4bae-109">**Data Type**</span></span>|<span data-ttu-id="f4bae-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="f4bae-110">**Key/Index**</span></span>|<span data-ttu-id="f4bae-111">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="f4bae-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4bae-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="f4bae-112">**TenantId**</span></span> <br/> |<span data-ttu-id="f4bae-113">int</span><span class="sxs-lookup"><span data-stu-id="f4bae-113">int</span></span>  <br/> |<span data-ttu-id="f4bae-114">주요한</span><span class="sxs-lookup"><span data-stu-id="f4bae-114">Primary</span></span>  <br/> |<span data-ttu-id="f4bae-115">이 테 넌 트 ID를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f4bae-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="f4bae-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="f4bae-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="f4bae-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4bae-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f4bae-118">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="f4bae-118">Allowed values:</span></span> <br/>  <span data-ttu-id="f4bae-119">00000000-0000-0000-0000-000000000000-엔터프라이즈</span><span class="sxs-lookup"><span data-stu-id="f4bae-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="f4bae-120">00000000-0000-0000-0000-000000000001-페더레이션</span><span class="sxs-lookup"><span data-stu-id="f4bae-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="f4bae-121">00000000-0000-0000-0000-000000000002-익명</span><span class="sxs-lookup"><span data-stu-id="f4bae-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="f4bae-122">00000000-0000-0000-0000-000000000003-공용 메신저 연결</span><span class="sxs-lookup"><span data-stu-id="f4bae-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

