---
title: MonitoredUserSiteLink 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다. 각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807796"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="965ec-104">MonitoredUserSiteLink 테이블</span><span class="sxs-lookup"><span data-stu-id="965ec-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="965ec-105">MonitoredUserSiteLink 링크 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="965ec-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="965ec-106">각 레코드는 두 사용자 사이트 간의 링크 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="965ec-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="965ec-107">**열**</span><span class="sxs-lookup"><span data-stu-id="965ec-107">**Column**</span></span>|<span data-ttu-id="965ec-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="965ec-108">**Data Type**</span></span>|<span data-ttu-id="965ec-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="965ec-109">**Key/Index**</span></span>|<span data-ttu-id="965ec-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="965ec-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="965ec-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="965ec-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="965ec-112">int</span><span class="sxs-lookup"><span data-stu-id="965ec-112">int</span></span>  <br/> |<span data-ttu-id="965ec-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="965ec-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="965ec-114">[Usersite 테이블](usersite.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="965ec-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="965ec-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="965ec-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="965ec-116">int</span><span class="sxs-lookup"><span data-stu-id="965ec-116">int</span></span>  <br/> |<span data-ttu-id="965ec-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="965ec-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="965ec-118">[Usersite 테이블](usersite.md)의 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="965ec-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

