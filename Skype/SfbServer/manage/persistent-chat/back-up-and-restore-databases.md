---
title: 비즈니스용 Skype 서버에서 영구 채팅 데이터베이스 백업 및 복원
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 및 복원하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826378"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="10ed1-103">비즈니스용 Skype 서버에서 영구 채팅 데이터베이스 백업 및 복원</span><span class="sxs-lookup"><span data-stu-id="10ed1-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="10ed1-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 및 복원하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="10ed1-105">영구 채팅 서버에는 기록 및 SQL Server, 구성, 사용자 프로비전 및 기타 관련 메타데이터와 같은 채팅방 데이터를 저장하기 위해 데이터베이스 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="10ed1-106">또한 조직에 영구 채팅 활동을 보관해야 하는 규정이 있는 경우 선택적 준수 서비스를 사용하도록 설정하면 SQL Server 데이터베이스 소프트웨어를 사용하여 채팅 콘텐츠 및 채팅방 참가 및 나가기 등의 규정 준수 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="10ed1-107">채팅방 콘텐츠는 영구 채팅 데이터베이스(mgc)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="10ed1-108">준수 데이터는 준수 데이터베이스(mgccomp)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="10ed1-109">정기적으로 백업해야 하는 업무상 중요한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="10ed1-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="10ed1-111">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="10ed1-112">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="10ed1-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="10ed1-113">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="10ed1-114">데이터베이스 백업</span><span class="sxs-lookup"><span data-stu-id="10ed1-114">Back up the databases</span></span>

<span data-ttu-id="10ed1-115">영구 채팅 데이터를 백업하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="10ed1-116">SQL Server 백업</span><span class="sxs-lookup"><span data-stu-id="10ed1-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="10ed1-117">영구 채팅 데이터를 파일로 내보내는 **Export-CsPersistentChatData** cmdlet</span><span class="sxs-lookup"><span data-stu-id="10ed1-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="10ed1-118">SQL Server 백업을 사용하여 만든 데이터에는 **Export-CsPersistentChatData** cmdlet에서 만든 것보다 훨씬 더 많은 디스크 공간이 필요하지만 SQL Server 백업은 익숙한 절차일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="10ed1-119">백업 절차를 SQL Server 자세한 내용은 SQL 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10ed1-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="10ed1-120">**Export-CsPersistentChatData** cmdlet을 사용하려는 경우 명령을 다음과 같이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="10ed1-121">또는</span><span class="sxs-lookup"><span data-stu-id="10ed1-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="10ed1-122">예를 들어 다음 명령은 서버에 있는 영구 채팅 데이터베이스에서 영구 채팅 데이터를 atl-sql-001.contoso.com. 내보낼 데이터는 파일 형식에 C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="10ed1-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="10ed1-123">Level 매개 변수를 지정하지 않은 경우 명령은 영구 채팅 정보를 전체 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="10ed1-124">데이터베이스 복원</span><span class="sxs-lookup"><span data-stu-id="10ed1-124">Restore the databases</span></span>

<span data-ttu-id="10ed1-125">영구 채팅 데이터를 복원하는 방법은 백업하는 데 사용한 방법에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="10ed1-126">백업 절차를 SQL Server 복원 절차를 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="10ed1-127">**Export-CsPersistentChatData** cmdlet을 사용하여 영구 채팅 데이터를 백업한 경우 **Import-CsPersistentChatData** cmdlet을 사용하여 데이터를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed1-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="10ed1-128">또는</span><span class="sxs-lookup"><span data-stu-id="10ed1-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
