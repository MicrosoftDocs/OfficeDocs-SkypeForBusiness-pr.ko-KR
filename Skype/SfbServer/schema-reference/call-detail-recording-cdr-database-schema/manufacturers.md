---
title: 비즈니스용 Skype 서버의 Manufacturers 테이블
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
ms.assetid: 734608b3-5a3a-4b61-87dc-9a8551401d06
description: Manufacturers 테이블은 지원 테이블입니다. 각 레코드에는 한 장치(책상 전화) 제조업체에 대한 정보가 저장됩니다.
ms.openlocfilehash: f3cdd6e33732eb226cc2d99ff403495ac19f5567
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821488"
---
# <a name="manufacturers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="79909-104">비즈니스용 Skype 서버의 Manufacturers 테이블</span><span class="sxs-lookup"><span data-stu-id="79909-104">Manufacturers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="79909-105">Manufacturers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="79909-105">The Manufacturers table is a supporting table.</span></span> <span data-ttu-id="79909-106">각 레코드에는 한 장치(책상 전화) 제조업체에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="79909-106">Each record stores information about one device (desk phone) manufacturer.</span></span>
  
|<span data-ttu-id="79909-107">**열**</span><span class="sxs-lookup"><span data-stu-id="79909-107">**Column**</span></span>|<span data-ttu-id="79909-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="79909-108">**Data Type**</span></span>|<span data-ttu-id="79909-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="79909-109">**Key/Index**</span></span>|<span data-ttu-id="79909-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="79909-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79909-111">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="79909-111">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="79909-112">int</span><span class="sxs-lookup"><span data-stu-id="79909-112">int</span></span>  <br/> |<span data-ttu-id="79909-113">Primary</span><span class="sxs-lookup"><span data-stu-id="79909-113">Primary</span></span>  <br/> |<span data-ttu-id="79909-114">이 제조업체를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="79909-114">Unique number identifying this manufacturer.</span></span>  <br/> |
|<span data-ttu-id="79909-115">**제조업체**</span><span class="sxs-lookup"><span data-stu-id="79909-115">**Manufacturer**</span></span> <br/> |<span data-ttu-id="79909-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="79909-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="79909-117">제조업체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="79909-117">Manufacturer name.</span></span>  <br/> |
   

