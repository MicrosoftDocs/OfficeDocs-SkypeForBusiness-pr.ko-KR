---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock은 일부 관리자 명령을 실행하는 데 필요한 관리자 잠금을 포함합니다.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809888"
---
# <a name="tbladminlock"></a><span data-ttu-id="207f0-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="207f0-103">tblAdminLock</span></span>
 
<span data-ttu-id="207f0-104">tblAdminLock은 일부 관리자 명령을 실행하는 데 필요한 관리자 잠금을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="207f0-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="207f0-105">**열**</span><span class="sxs-lookup"><span data-stu-id="207f0-105">**Columns**</span></span>

|<span data-ttu-id="207f0-106">**열**</span><span class="sxs-lookup"><span data-stu-id="207f0-106">**Column**</span></span>|<span data-ttu-id="207f0-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="207f0-107">**Type**</span></span>|<span data-ttu-id="207f0-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="207f0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="207f0-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="207f0-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="207f0-110">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="207f0-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="207f0-p101">잠금 만료 날짜 및 시간입니다. 소유자는 이 값을 주기적으로 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="207f0-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="207f0-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="207f0-113">lockServerID</span></span>  <br/> |<span data-ttu-id="207f0-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="207f0-114">int, not null</span></span>  <br/> |<span data-ttu-id="207f0-115">잠금을 소유하는 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="207f0-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="207f0-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="207f0-116">lockActorID</span></span>  <br/> |<span data-ttu-id="207f0-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="207f0-117">int, not null</span></span>  <br/> |<span data-ttu-id="207f0-118">잠금을 소유하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="207f0-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

