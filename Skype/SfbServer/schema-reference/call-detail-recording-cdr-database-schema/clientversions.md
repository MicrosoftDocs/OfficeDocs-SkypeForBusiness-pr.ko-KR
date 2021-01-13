---
title: 비즈니스용 Skype 서버의 ClientVersions 테이블
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 테이블은 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813318"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8077b-104">비즈니스용 Skype 서버의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="8077b-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8077b-p102">ClientVersions 테이블은 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8077b-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="8077b-107">**열**</span><span class="sxs-lookup"><span data-stu-id="8077b-107">**Column**</span></span>|<span data-ttu-id="8077b-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="8077b-108">**Data Type**</span></span>|<span data-ttu-id="8077b-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="8077b-109">**Key/Index**</span></span>|<span data-ttu-id="8077b-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="8077b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8077b-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="8077b-111">**VersionId**</span></span> <br/> |<span data-ttu-id="8077b-112">**int**</span><span class="sxs-lookup"><span data-stu-id="8077b-112">**int**</span></span> <br/> |<span data-ttu-id="8077b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8077b-113">Primary</span></span>  <br/> |<span data-ttu-id="8077b-114">이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8077b-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="8077b-115">**버전**</span><span class="sxs-lookup"><span data-stu-id="8077b-115">**Version**</span></span> <br/> |<span data-ttu-id="8077b-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="8077b-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="8077b-117">버전 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8077b-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="8077b-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="8077b-118">**ClientType**</span></span> <br/> |<span data-ttu-id="8077b-119">int</span><span class="sxs-lookup"><span data-stu-id="8077b-119">int</span></span>  <br/> ||<span data-ttu-id="8077b-120">세션에 사용된 클라이언트 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8077b-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="8077b-121">자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8077b-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="8077b-122">이 필드는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="8077b-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

