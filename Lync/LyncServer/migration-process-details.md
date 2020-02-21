---
title: 마이그레이션 프로세스-세부 정보
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
ms.openlocfilehash: 6df1eb2e0f69f79bd299f2da4f6f12aaba1bb5d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="0308e-102">마이그레이션 프로세스-세부 정보</span><span class="sxs-lookup"><span data-stu-id="0308e-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0308e-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0308e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0308e-104">Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하려면 다음 필수 구성 요소 및 세부 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="0308e-105">마이그레이션을 위한 사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0308e-105">Prerequisites for Migration</span></span>

<span data-ttu-id="0308e-106">Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하기 전에 다음 필수 구성 요소를 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="0308e-107">하나 이상의 Lync Server 2013 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="0308e-108">Lync Server 2013 풀이 여러 개 있는 경우 새 Lync Server 2013 영구 채팅 서버 풀에 대 한 홈 풀이 될 Lync Server 2013 풀을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="0308e-109">Lync Server 2013, 영구 채팅 서버 풀을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="0308e-110">범주, 채팅방, 추가 기능 등이 전혀 없이 빈 상태일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="0308e-111">레거시 범주, 회의실 또는 추가 기능을 마이그레이션하기 전에 Lync Server 2013, 영구 채팅 서버 배포에 회의실, 범주 또는 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0308e-p103">새로 만든 항목이 마이그레이션하는 기존 항목과 충돌할 수 있습니다. 이름이 충돌하지 않도록 방지하십시오. 그렇지 않으면 기존 데이터를 마이그레이션할 때 덮어써집니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-p103">Be aware that these newly created items may conflict with legacy items that you migrate. Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="0308e-114">마이그레이션을 위해 원본 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="0308e-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="0308e-115">다음 단계를 수행하여 마이그레이션을 위해 원본 데이터를 올바로 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="0308e-116">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 원본 데이터베이스를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="0308e-117">SQL Server를 백업 하는 방법에 대 한 자세한 내용은의 "백업 개요 (SQL <https://go.microsoft.com/fwlink/p/?linkid=254851>Server)"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0308e-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0308e-118">Active Directory 도메인 서비스는 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="0308e-119">마이그레이션을 위한 조건으로, 특히, 다른 Active Directory 포리스트에서 다른 배포의 풀로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="0308e-120">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 대화방 및 범주 구성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="0308e-121">기존 레거시 배포의 범주, 대화방 또는 추가 기능에 대 한 변경 내용은 그룹 채팅 관리 도구를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="0308e-122">Lync Server 2013, 영구 채팅 서버 배포의 범주, 대화방 또는 추가 기능에 대 한 변경 내용은 Lync Server 제어판 또는 Windows PowerShell cmdlet을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="0308e-123">다음 단계를 수행하여 기존 시스템을 마이그레이션할 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="0308e-124">영구 채팅 서버는 범주에 대 한 심도 깊은 계층 집합과 달리 단일 수준의 범주를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="0308e-125">마이그레이션이 완료되면 하위 범주 앞에 전체 상위 범주 이름이 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="0308e-126">기존 범주 구조를 단일 계층으로 단순화하여 요구 사항에 맞는 결과 구조를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="0308e-p108">루트 범주에 **관리자**가 있는지 확인합니다. 이 루트 수준에 관리자가 존재하면 마이그레이션 이후 해당 사용자는 **모든 채팅방의 관리자**로 추가됩니다. 관리자가 조직 요구 사항이 아니면 루트 범주에서 이들 관리자를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-p108">Verify the **Managers** at the root Category. If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration. If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="0308e-p109">채팅방 이름의 길이를 확인합니다. 마이그레이션 이후 단순화된 범주 구조로 인해 하위 범주를 보유한 채팅방은 이름 앞에 상위 범주의 전체 이름이 붙습니다. 이름은 상위 범주 이름을 포함하여 256자로 제한됩니다. 채팅방 이름의 길이를 확인한 후, 이름이 너무 긴 경우 가능하면 길이를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-p109">Verify the length of room names. After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names. The naming limit is 256 characters, including parent category names. You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="0308e-134">Lync Server 2013에서 범주 **초대** 설정이 true로 설정 된 경우 해당 범주의 대화방에 대 한 초대에 대해 true 또는 false를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="0308e-135">하지만 범주 초대 설정이 거짓으로 설정된 경우 해당 범주 아래의 채팅방은 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="0308e-136">특정 범주에 해당 하는 대화방을 만들려는 경우 마이그레이션 전에 레거시 Lync Server 그룹 채팅 서버 버전에서 초대 설정을 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="0308e-137">그렇지 않으면 마이그레이션 중에 Lync Server 2013에서 경고를 표시 하 고 대화방을 기본값인 false로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="0308e-138">채팅방에서 파일을 사용한 경우에는 마이그레이션 후에 새 영구 채팅 파일 저장소로 파일을 수동으로 XCOPY 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="0308e-139">이는 자동으로 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="0308e-140">페더레이션 사용자와 대화방을 연결 해야 하는 경우 영구 채팅 서버가 페더레이션을 지원 하지 않는다는 것을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="0308e-141">페더레이션 사용자가 있는 채팅방은 마이그레이션되지만 페더레이션 액세스가 지원되지 않으므로 사용자 자신은 콘텐츠에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="0308e-142">마이그레이션하지 않으려는 채팅방을 식별하여 사용 안 함으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="0308e-p113">채팅방 콘텐츠를 마이그레이션하기 시작할 날짜를 식별합니다. 예를 들어 2010년 1월 1일 이전의 메시지는 오래되었거나 마이그레이션과 관련이 없다는 이유로 마이그레이션하지 않으려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-p113">Identify the date beyond which you want to migrate the chat room content. For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="0308e-145">마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="0308e-145">Performing the Migration</span></span>

<span data-ttu-id="0308e-146">다음 단계를 수행 하 여 레거시 그룹 채팅 서버를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="0308e-147">Lync Server 2010, 그룹 채팅, Office Communications Server 2007 R2 그룹 채팅 또는 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="0308e-148">모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 시간에이 작업을 수행 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="0308e-149">앞에서 설명한 것 처럼 현재 그룹 채팅 데이터베이스를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="0308e-150">Windows PowerShell **export-cspersistentchatdata** Cmdlet을 영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="0308e-151">내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0308e-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="0308e-152">내보낸 콘텐츠를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="0308e-153">가져오기 전에 Lync Server 2013, 영구 채팅 서버 서비스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="0308e-154">모든 서비스를 중지 해야 하므로 가동 중지 시간이 충분 한 시간에이 작업을 수행 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="0308e-155">마이그레이션 전에 Lync Server 2013 배포에서 범주, 대화방 또는 추가 기능을 만든 경우 영구 채팅 데이터베이스의 백업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="0308e-156">내보내기/가져오기 프로세스를 통해 레거시 데이터를 Lync Server 2013 배포에 병합할 수는 있지만, 그래도 이름 충돌이 여전히 존재 하는 경우에는 콘텐츠를 실수로 덮어쓰는 경우에 대비 하 여 데이터베이스를 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="0308e-157">**WhatIf** 명령을 사용 하 여 Windows PowerShell **export-cspersistentchatdata** cmdlet (가져오기 도구)을 실행 하 여 영구 채팅 서버 풀의 백 엔드 서버를 마이그레이션된 데이터로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="0308e-158">단순화된 관리 모델을 적용하는 과정에서 일부 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="0308e-159">나타나는 오류 또는 경고를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="0308e-160">영구 채팅 관리자 RBAC 역할 (CsPersistentChatAdministrator)의 구성원으로 영구 채팅 서버 Windows PowerShell **export-cspersistentchatdata** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="0308e-161">내보내기/가져오기 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0308e-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="0308e-162">업로드 된 모든 파일 (전체 폴더)을 새 Lync Server 2013, 영구 채팅 파일 저장소로 XCOPY 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0308e-163">Lync 2013 (클라이언트)은 대화방에서 파일을 업로드 하거나 보는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="0308e-164">채팅방의 파일을 보고 게시하기 위해 기존 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="0308e-165">Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅 조회 서버 URI를 Lync Server 2013, 영구 채팅 서버 연락처 개체에 이식 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="0308e-166">다음 단계는 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅 클라이언트가 클라이언트 쪽 구성 변경 없이 마이그레이션 후 최신 Lync 2013, 영구 채팅 (클라이언트)에 연결 해야 하는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="0308e-167">Ocschat@\<DomainName\>조회 서버 사용자 계정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="0308e-168">이는 Lync Server 2010, 그룹 채팅의 조회 서비스를 가리키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="0308e-169">풀을 제거하고 신뢰할 수 있는 항목을 나중에 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="0308e-170">레거시 클라이언트가 서비스를 다시 시작할 때 효과적으로 작동 하도록 하려면 Windows PowerShell cmdlet **get-cspersistentchatendpoint**를 실행 하 여 동일한 SIP URI를 사용 하 여 레거시 끝점 (영구 채팅 서버 대화 상대 개체)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="0308e-171">이제 필수 마이그레이션 프로세스를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="0308e-172">Lync 2010 그룹 채팅 (클라이언트) 또는 Office Communicator 2007 R2 그룹 채팅 (클라이언트)은 이제 새 영구 채팅 서버 풀에 투명 하 게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="0308e-173">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에 대 한 다음 추가 폐기 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="0308e-174">새 영구 채팅 서버 풀의 모든 컴퓨터를 설정 하 여 영구 채팅 서버 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="0308e-175">Lync Server 제어판 및 Windows PowerShell cmdlet을 사용 하 여 데이터가 제대로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="0308e-176">그룹 채팅 서버 풀의 컴퓨터에서 Lync 2010 그룹 채팅 또는 Office Communicator 2007 R2 그룹 채팅을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="0308e-177">Windows PowerShell cmdlet을 사용 하 여 신뢰할 수 있는 응용 프로그램 및 트러스트 된 응용 프로그램 풀을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0308e-178">이렇게 하면 중앙 관리 저장소에서 이러한 항목과 Active Directory에서 연결 된 TSEs (신뢰할 수 있는 서비스 항목)가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="0308e-179">또한 토폴로지 작성기를 사용 하 여이 단계를 수행할 수도 있습니다 (신뢰할 수 있는 응용 프로그램/풀에도 전용 노드가 있습니다.).</span><span class="sxs-lookup"><span data-stu-id="0308e-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="0308e-180">이제 새 클라이언트를 통해 영구 채팅 서버 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="0308e-181">영구 채팅 서버를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 배포](lync-server-2013-deploying-persistent-chat-server.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0308e-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0308e-182">Lync Server 2013에서는 여러 영구 채팅 서버 풀을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="0308e-183">그러나 microsoft는 Lync 2010 그룹 채팅 또는 Office Communications Server 2007 R2&nbsp;그룹 채팅 풀을 단일 Lync Server 2013, 영구 채팅 서버 풀로 마이그레이션하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="0308e-184">배포에 새 영구 채팅 서버 풀을 추가 하 여 규정 요구 사항 (예: 지정 된 지리 내의 데이터 유지)을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0308e-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

