---
title: 장치 로그 구성 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 로그 캐시의 최대 크기, 최대 로그 파일 크기 또는 로그 파일이 삭제되기 전까지 보관되는 기간을 결정하는 로그 설정 편집 페이지에 장치 로그 구성을 추가할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.
ms.openlocfilehash: 694729b74209715bd87bed0c3bd59d80f31fff59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807318"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="dab97-104">장치 로그 구성: 편집</span><span class="sxs-lookup"><span data-stu-id="dab97-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="dab97-105">최대 로그 캐시 크기,  최대 로그 파일 크기 또는 로그 파일이 삭제되기 전까지 보관되는 기간을 결정하는 로그 설정 편집 페이지에 장치 로그 구성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="dab97-106">조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dab97-p103">파일을 삭제하면 파일 시스템에서 영구 제거됩니다. 따라서 파일을 삭제한 후 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="dab97-109">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="dab97-109">Tasks you can perform</span></span>

<span data-ttu-id="dab97-110">로그 설정 편집 페이지에서는 **다음 작업을 수행할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="dab97-111">장치 로그 구성을 전역적으로 또는 특정 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="dab97-112">기존 장치 로그 구성에 대한 옵션 수정</span><span class="sxs-lookup"><span data-stu-id="dab97-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="dab97-113">UI 참조</span><span class="sxs-lookup"><span data-stu-id="dab97-113">UI Reference</span></span>

<span data-ttu-id="dab97-114">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="dab97-115">**범위** 장치 로그 구성의 범위(전역 또는 사이트)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="dab97-116">**이름** 장치 로그 구성의 이름을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="dab97-117">**최대 파일 크기(byte)입니다.** 로그 파일을 제거하기 전에 커질 수 있는 최대 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="dab97-118">기본값은 1,024,000 byte(1MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="dab97-119">**최대 캐시 크기(byte)입니다.** 캐시를 지우고 데이터가 로그 파일에 기록되기 전에 로그 파일 캐시에 저장될 수 있는 최대 정보의 양(bytes)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="dab97-120">기본값은 512,000비트(0.5MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="dab97-121">**캐시 플러시 시간(1~60분)** 로그 파일 캐시에 저장된 정보가 실제 로그 파일에 기록되는 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="dab97-122">데이터가 기록된 후 캐시가 지워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="dab97-123">기본값은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="dab97-124">**로그 파일을 보관할 일 수(1-365)** 로그 파일을 삭제하기 전까지 보관할 일 수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="dab97-125">기본값은 10일입니다.</span><span class="sxs-lookup"><span data-stu-id="dab97-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dab97-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dab97-126">See also</span></span>

[<span data-ttu-id="dab97-127">장치 로그 구성</span><span class="sxs-lookup"><span data-stu-id="dab97-127">Device Log Configuration</span></span>](device-log-configuration.md)
