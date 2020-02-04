---
title: 마이그레이션 프로세스 - 세부 정보
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="38762-102">마이그레이션 프로세스 - 세부 정보</span><span class="sxs-lookup"><span data-stu-id="38762-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38762-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="38762-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="38762-104">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하려면 다음 필수 구성 요소와 세부 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="38762-105">마이그레이션 필수 조건</span><span class="sxs-lookup"><span data-stu-id="38762-105">Prerequisites for Migration</span></span>

<span data-ttu-id="38762-106">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하기 전에 다음 전제 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="38762-107">하나 이상의 Lync Server 2013 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="38762-108">Lync Server 2013 풀이 여러 개 있는 경우 새 Lync Server 2013 영구 채팅 서버 풀에 대 한 홈 풀이 될 Lync Server 2013 풀을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="38762-109">Lync Server 2013, 영구 채팅 서버 풀을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="38762-110">비어 있는 항목 (범주, 방 또는 추가 기능은 없음)이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="38762-111">레거시 범주, 회의실 또는 추가 기능을 마이그레이션하기 전에 Lync Server 2013, 영구 채팅 서버 배포에서 회의실, 범주 또는 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38762-112">새로 만든 이러한 항목은 마이그레이션하는 레거시 항목과 충돌할 수 있으므로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="38762-113">명명 충돌을 방지 합니다. 그렇지 않으면 레거시 데이터를 마이그레이션할 때 덮어쓰게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="38762-114">마이그레이션에 대 한 원본 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="38762-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="38762-115">마이그레이션에 사용할 원본 데이터를 적절 하 게 준비 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="38762-116">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 원본 데이터베이스를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="38762-117">SQL Server를 백업 하는 방법에 대 한 자세한 내용은에서 <http://go.microsoft.com/fwlink/p/?linkid=254851>"백업 개요 (SQL Server)"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38762-118">Active Directory 도메인 서비스는 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="38762-119">마이그레이션에 대 한 조건으로 다른 배포의 풀로 마이그레이션할 수 없습니다 (특히, 다른 Active Directory 포리스트에서).</span><span class="sxs-lookup"><span data-stu-id="38762-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="38762-120">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 채팅방과 범주 구성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="38762-121">기존 레거시 배포의 범주, 회의실 또는 추가 기능에 대 한 변경 내용은 그룹 채팅 관리 도구를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="38762-122">Lync Server 2013의 범주, 회의실 또는 추가 기능에 대 한 변경 내용은 Lync Server 제어판 또는 Windows PowerShell cmdlet에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="38762-123">다음 단계에 따라 마이그레이션에 대 한 레거시 시스템을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="38762-124">영구 채팅 서버는 범주에 대 한 깊은 계층 구조 집합과 달리 단일 수준의 범주를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="38762-125">마이그레이션 후 하위 범주에는 전체 상위 범주 이름이 접두사로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="38762-126">결과 구조가 요구 사항을 충족 하도록 기존 범주 구조를 단순화 하 고 결합 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="38762-127">루트 범주에서 **관리자** 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="38762-128">이 수준에 관리자가 있는 경우 이러한 사용자는 마이그레이션 후 **모든 채팅방에 관리자로** 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="38762-129">조직에 대 한 요구 사항이 아닌 경우 루트 범주에서 이러한 관리자를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="38762-130">방 이름의 길이를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-130">Verify the length of room names.</span></span> <span data-ttu-id="38762-131">마이그레이션 후에는 간소화 된 범주 구조로 인해 해당 채팅방이 하위 범주 아래에 있는 경우 전체 상위 범주 이름을 접두사로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="38762-132">이름 제한은 상위 범주 이름을 포함 하 여 256 자입니다.</span><span class="sxs-lookup"><span data-stu-id="38762-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="38762-133">방 이름의 길이를 확인 하 여 길이가 너무 긴 경우 길이를 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="38762-134">Lync Server 2013에서 범주 **초대** 설정이 true로 설정 된 경우 해당 범주 아래에 있는 채팅방에 대 한 초대에 대해 true 또는 false를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="38762-135">그러나 범주 초대 설정이 false로 설정 된 경우 해당 범주의 채팅방에는 초대가 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="38762-136">특정 범주 아래에 방 (들)이 존재 하도록 하려면 마이그레이션하기 전에 레거시 Lync Server 그룹 채팅 서버 버전에서 초대 설정을 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="38762-137">그렇지 않으면 마이그레이션 중에 Lync Server 2013에서 경고가 표시 되 고 채팅방이 기본값 false로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="38762-138">채팅방에서 파일을 사용한 경우에는 마이그레이션한 후 새 영구 채팅 파일 저장소에 파일을 수동으로 XCOPY 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="38762-139">도구가이 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="38762-140">페더레이션 사용자와 페더레이션 사용자 및 채팅방을 사용 하는 경우 영구 채팅 서버가 페더레이션을 지원 하지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="38762-141">페더레이션 사용자가 있는 채팅방은 마이그레이션됩니다. 그러나 페더레이션 액세스는 지원 되지 않으므로 사용자 자체는 콘텐츠에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="38762-142">마이그레이션하지 않으려는 채팅방을 확인 하 고 사용 안 함으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="38762-143">채팅방 콘텐츠를 마이그레이션할 이후 날짜를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="38762-144">예를 들어, 2010 년 1 월 1 일 이전에는 이러한 메시지가 오래 되거나 마이그레이션과 관련이 없기 때문에이 메시지를 마이그레이션하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="38762-145">마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="38762-145">Performing the Migration</span></span>

<span data-ttu-id="38762-146">다음 단계를 수행 하 여 이전 그룹 채팅 서버를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="38762-147">Lync Server 2010, 그룹 채팅, Office Communications Server 2007 R2 그룹 채팅 또는 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="38762-148">모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분할 때이 작업을 수행할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="38762-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="38762-149">앞에서 설명한 대로 현재 그룹 채팅 데이터베이스를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="38762-150">Windows PowerShell **내보내기-CsPersistentChatData** Cmdlet을 영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="38762-151">내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="38762-152">내보낸 콘텐츠를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="38762-153">가져오기 전에 Lync Server 2013, 영구 채팅 서버 서비스를 종료 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="38762-154">모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 경우에이 작업을 수행 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="38762-155">마이그레이션 전에 Lync Server 2013 배포에서 범주, 방 또는 추가 기능을 만든 경우 영구 채팅 데이터베이스의 백업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="38762-156">내보내기/가져오기 프로세스는 레거시 데이터를 Lync Server 2013 배포에 병합할 수 있지만, 해당 콘텐츠를 실수로 덮어쓴 경우 (예: 이름 충돌이 여전히 존재 하는 경우)에는 데이터베이스를 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="38762-157">Windows PowerShell **가져오기-CsPersistentChatData** cmdlet (가져오기 도구)을 실행 하 여 **WhatIf** 명령을 사용 하 여 영구 채팅 서버 풀의 백 엔드 서버를 마이그레이션된 데이터로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="38762-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="38762-158">간단한 관리 모델을 수용 하기 위해 일부 변환이 진행 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="38762-159">표시 되는 오류 또는 경고를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="38762-160">영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 지속적인 채팅 서버 Windows PowerShell **CsPersistentChatData** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="38762-161">내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="38762-162">모든 업로드 된 파일 (전체 폴더)을 새 Lync Server 2013, 영구 채팅 파일 저장소에 XCOPY 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38762-163">Lync 2013 (클라이언트)는 채팅방에서 파일을 업로드 하거나 보는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="38762-164">여전히 레거시 클라이언트를 사용 하 여 룸에서 파일을 게시 하 고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="38762-165">Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 조회 서버 URI를 Lync Server 2013, 영구 채팅 서버 contact 개체에 이식 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="38762-166">Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅 클라이언트가 클라이언트쪽 구성 변경 없이 마이그레이션 후 최신 Lync 2013, 영구 채팅 (클라이언트)에 연결 해야 하는 경우 다음 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="38762-167">Ocschat@\<DomainName\>조회 서버 사용자 계정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="38762-168">이는 Lync Server 2010, 그룹 채팅에서 조회 서비스를 가리키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="38762-169">풀을 제거 하 고 나중에 신뢰 된 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="38762-170">서비스를 다시 시작할 때 레거시 클라이언트가 효과적으로 작동할 수 있도록 동일한 SIP URI를 사용 하 여 Windows PowerShell cmdlet 인 **CsPersistentChatEndpoint**를 실행 하 여 레거시 끝점 (영구 채팅 서버 contact 개체)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38762-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="38762-171">필수 마이그레이션 프로세스는이 시점에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="38762-172">Lync 2010 그룹 채팅 (클라이언트) 또는 Office Communicator 2007 R2 그룹 채팅 (클라이언트)이 새 영구 채팅 서버 풀에 투명 하 게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="38762-173">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 다음 추가 폐기 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="38762-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="38762-174">새로운 영구 채팅 서버 풀에서 모든 컴퓨터를 설정 하 여 영구 채팅 서버 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="38762-175">Lync Server 제어판 및 Windows PowerShell cmdlet을 사용 하 여 데이터가 성공적으로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="38762-176">그룹 채팅 서버 풀의 컴퓨터에서 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="38762-177">Windows PowerShell cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램 및 신뢰 된 응용 프로그램 풀을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="38762-178">이렇게 하면 중앙 관리 저장소에서 이러한 항목이 삭제 되 고 Active Directory에서 TSEs (신뢰할 수 있는 서비스 항목)가 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38762-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="38762-179">또는이 단계는 토폴로지 작성기를 사용 하 여 작동 합니다 (신뢰할 수 있는 응용 프로그램/풀에도 전용 노드가 있습니다.).</span><span class="sxs-lookup"><span data-stu-id="38762-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="38762-180">이제 새 클라이언트를 통해 영구 채팅 서버 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="38762-181">영구 채팅 서버를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38762-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38762-182">Lync Server 2013는 여러 영구 채팅 서버 풀을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="38762-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="38762-183">그러나 Lync 2010 그룹 채팅 또는 Office Communications Server 2007 R2&nbsp;그룹 채팅 풀을 단일 Lync 서버 2013, 영구 채팅 서버 풀로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38762-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="38762-184">배포에 새 영구 채팅 서버 풀을 추가 하 여 규정 요구를 충족 시킬 수 있습니다 (예: 지정 된 지리 내에 데이터 유지).</span><span class="sxs-lookup"><span data-stu-id="38762-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

