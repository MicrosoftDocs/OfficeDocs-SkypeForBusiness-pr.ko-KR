---
title: FileTransfers 보기
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821688"
---
# <a name="filetransfers-view"></a><span data-ttu-id="4cda9-104">FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="4cda9-104">FileTransfers view</span></span>
 
<span data-ttu-id="4cda9-105">FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="4cda9-106">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4cda9-107">FileTransfers 보기에는 [SessionDetails](sessiondetails-0.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="4cda9-108">**열**</span><span class="sxs-lookup"><span data-stu-id="4cda9-108">**Column**</span></span>|<span data-ttu-id="4cda9-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="4cda9-109">**Data Type**</span></span>|<span data-ttu-id="4cda9-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="4cda9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4cda9-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="4cda9-111">**FileName**</span></span> <br/> |<span data-ttu-id="4cda9-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4cda9-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4cda9-113">전송된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="4cda9-114">**쿠키**</span><span class="sxs-lookup"><span data-stu-id="4cda9-114">**Cookie**</span></span> <br/> |<span data-ttu-id="4cda9-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="4cda9-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="4cda9-116">이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="4cda9-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="4cda9-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="4cda9-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4cda9-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4cda9-119">동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="4cda9-120">**수락**</span><span class="sxs-lookup"><span data-stu-id="4cda9-120">**Accept**</span></span> <br/> |<span data-ttu-id="4cda9-121">bit</span><span class="sxs-lookup"><span data-stu-id="4cda9-121">bit</span></span>  <br/> |<span data-ttu-id="4cda9-p103">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="4cda9-124">**거부**</span><span class="sxs-lookup"><span data-stu-id="4cda9-124">**Reject**</span></span> <br/> |<span data-ttu-id="4cda9-125">bit</span><span class="sxs-lookup"><span data-stu-id="4cda9-125">bit</span></span>  <br/> |<span data-ttu-id="4cda9-p104">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="4cda9-128">**취소**</span><span class="sxs-lookup"><span data-stu-id="4cda9-128">**Cancel**</span></span> <br/> |<span data-ttu-id="4cda9-129">bit</span><span class="sxs-lookup"><span data-stu-id="4cda9-129">bit</span></span>  <br/> |<span data-ttu-id="4cda9-p105">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cda9-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

