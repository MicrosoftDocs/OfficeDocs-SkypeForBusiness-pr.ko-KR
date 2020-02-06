---
title: 영구 채팅 데이터베이스 백업 및 복원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 하 고 복원 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817344"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="cdb75-103">영구 채팅 데이터베이스 백업 및 복원</span><span class="sxs-lookup"><span data-stu-id="cdb75-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cdb75-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 하 고 복원 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cdb75-105">영구 채팅 서버에는 기록 및 콘텐츠, 구성, 사용자 프로비저닝, 기타 관련 메타 데이터 등의 채팅방 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="cdb75-106">또한 조직에 영구 채팅 작업을 보관 해야 하는 규정이 있고 선택적 준수 서비스를 사용 하는 경우 SQL Server 데이터베이스 소프트웨어를 사용 하 여 다음과 같은 채팅 콘텐츠 및 이벤트를 비롯 한 규정 준수 데이터를 저장 합니다. 회의실에 가입/탈퇴</span><span class="sxs-lookup"><span data-stu-id="cdb75-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="cdb75-107">채팅방 콘텐츠는 mgc (영구 채팅 데이터베이스)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="cdb75-108">준수 데이터는 준수 데이터베이스 (mgccomp)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="cdb75-109">정기적으로 백업 해야 하는 비즈니스에 중요 한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cdb75-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cdb75-111">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="cdb75-112">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb75-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="cdb75-113">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="cdb75-114">데이터베이스 백업</span><span class="sxs-lookup"><span data-stu-id="cdb75-114">Back up the databases</span></span>

<span data-ttu-id="cdb75-115">영구 채팅 데이터를 백업 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="cdb75-116">SQL Server 백업</span><span class="sxs-lookup"><span data-stu-id="cdb75-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="cdb75-117">영구 채팅 데이터를 파일로 내보내는 **Export-CsPersistentChatData** cmdlet</span><span class="sxs-lookup"><span data-stu-id="cdb75-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="cdb75-118">SQL Server 백업을 사용 하 여 만든 데이터에는 **내보내기-CsPersistentChatData** cmdlet에서 만든 것 보다 훨씬 더 많은 디스크 공간이 필요 하지만, sql server 백업은 사용자가 익숙한 프로시저인 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="cdb75-119">SQL Server 백업 절차를 사용 하려는 경우 자세한 내용은 SQL 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb75-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="cdb75-120">**Export-CsPersistentChatData** cmdlet을 사용 하려는 경우 다음과 같이 명령을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="cdb75-121">또는</span><span class="sxs-lookup"><span data-stu-id="cdb75-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="cdb75-122">예를 들어 다음 명령은 서버 atl-sql-001.contoso.com에 있는 영구 채팅 데이터베이스에서 영구 채팅 데이터를 내보냅니다. 내보낸 데이터는 파일 C:\Logs\PersistentChatData.zip.에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="cdb75-123">Level 매개 변수가 지정 되지 않았으므로이 명령은 영구 채팅 정보를 전체적으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="cdb75-124">데이터베이스 복원</span><span class="sxs-lookup"><span data-stu-id="cdb75-124">Restore the databases</span></span>

<span data-ttu-id="cdb75-125">영구 채팅 데이터를 복원 하는 방법은 백업 하는 데 사용한 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="cdb75-126">SQL Server 백업 절차를 사용 하는 경우 SQL Server restore 프로시저를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="cdb75-127">**CsPersistentChatData** cmdlet을 사용 하 여 영구 채팅 데이터를 백업한 경우 **CsPersistentChatData** cmdlet을 사용 하 여 데이터를 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb75-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="cdb75-128">또는</span><span class="sxs-lookup"><span data-stu-id="cdb75-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
