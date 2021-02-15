---
title: tblSystemRevision
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
ms.assetid: 95b8e307-117c-4fb0-bd52-bc5a5b9ade55
description: tblSystemRevision에는 여러 관리자 클라이언트 간에 일관성을 유지하기 위해서 tblAdminLock 테이블에서 사용되는 수정 버전 번호가 포함됩니다.
ms.openlocfilehash: 5bbcf547d6e6f31cc3e9d71415fed6f351c82910
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831418"
---
# <a name="tblsystemrevision"></a><span data-ttu-id="cb5fd-103">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="cb5fd-103">tblSystemRevision</span></span>
 
<span data-ttu-id="cb5fd-104">tblSystemRevision에는 여러 관리자 클라이언트 간에 일관성을 유지하기 위해서 tblAdminLock 테이블에서 사용되는 수정 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5fd-104">tblSystemRevision contains the revision number that is used with the tblAdminLock table to achieve consistency across multiple administrator clients.</span></span>
  
<span data-ttu-id="cb5fd-105">**열**</span><span class="sxs-lookup"><span data-stu-id="cb5fd-105">**Columns**</span></span>

|<span data-ttu-id="cb5fd-106">**열**</span><span class="sxs-lookup"><span data-stu-id="cb5fd-106">**Column**</span></span>|<span data-ttu-id="cb5fd-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="cb5fd-107">**Type**</span></span>|<span data-ttu-id="cb5fd-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb5fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb5fd-109">sysRevision</span><span class="sxs-lookup"><span data-stu-id="cb5fd-109">sysRevision</span></span>  <br/> |<span data-ttu-id="cb5fd-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="cb5fd-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="cb5fd-111">수정 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5fd-111">Revision number.</span></span>  <br/> |
   

