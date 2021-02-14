---
title: Roles 테이블
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809978"
---
# <a name="roles-table"></a><span data-ttu-id="01c9e-103">Roles 테이블</span><span class="sxs-lookup"><span data-stu-id="01c9e-103">Roles table</span></span>
 
<span data-ttu-id="01c9e-104">Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="01c9e-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="01c9e-105">**열**</span><span class="sxs-lookup"><span data-stu-id="01c9e-105">**Column**</span></span>|<span data-ttu-id="01c9e-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="01c9e-106">**Data Type**</span></span>|<span data-ttu-id="01c9e-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="01c9e-107">**Key/Index**</span></span>|<span data-ttu-id="01c9e-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="01c9e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01c9e-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="01c9e-109">**RoleId**</span></span> <br/> |<span data-ttu-id="01c9e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="01c9e-110">tinyint</span></span>  <br/> |<span data-ttu-id="01c9e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="01c9e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="01c9e-112">**역할**</span><span class="sxs-lookup"><span data-stu-id="01c9e-112">**Role**</span></span> <br/> |<span data-ttu-id="01c9e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="01c9e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="01c9e-114">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="01c9e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="01c9e-115">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="01c9e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="01c9e-116">1 - 발표자</span><span class="sxs-lookup"><span data-stu-id="01c9e-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="01c9e-117">2 - 참석자</span><span class="sxs-lookup"><span data-stu-id="01c9e-117">2 - Attendee</span></span> <br/> |
   

