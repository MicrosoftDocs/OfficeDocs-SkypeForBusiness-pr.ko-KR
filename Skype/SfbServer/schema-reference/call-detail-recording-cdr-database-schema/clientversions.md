---
title: 비즈니스용 Skype 서버 2015의 ClientVersions 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 테이블은 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196788"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="634df-104">비즈니스용 Skype 서버 2015의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="634df-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="634df-105">ClientVersions 테이블은 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="634df-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="634df-106">테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="634df-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="634df-107">**열**</span><span class="sxs-lookup"><span data-stu-id="634df-107">**Column**</span></span>|<span data-ttu-id="634df-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="634df-108">**Data Type**</span></span>|<span data-ttu-id="634df-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="634df-109">**Key/Index**</span></span>|<span data-ttu-id="634df-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="634df-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="634df-111">**#**</span><span class="sxs-lookup"><span data-stu-id="634df-111">**VersionId**</span></span> <br/> |<span data-ttu-id="634df-112">**int**</span><span class="sxs-lookup"><span data-stu-id="634df-112">**int**</span></span> <br/> |<span data-ttu-id="634df-113">주요한</span><span class="sxs-lookup"><span data-stu-id="634df-113">Primary</span></span>  <br/> |<span data-ttu-id="634df-114">이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="634df-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="634df-115">**버전**</span><span class="sxs-lookup"><span data-stu-id="634df-115">**Version**</span></span> <br/> |<span data-ttu-id="634df-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="634df-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="634df-117">버전 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="634df-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="634df-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="634df-118">**ClientType**</span></span> <br/> |<span data-ttu-id="634df-119">int</span><span class="sxs-lookup"><span data-stu-id="634df-119">int</span></span>  <br/> ||<span data-ttu-id="634df-120">세션에 사용 되는 클라이언트 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="634df-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="634df-121">자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="634df-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="634df-122">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="634df-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

