---
title: 'Lync Server 2013: 재해 복구 시 알림 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fc5aec6371bff867c2e33dbe7b88aa0d2a888c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534551"
---
# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="e08bd-102">Lync Server 2013에서 재해 복구 시 알림 관리</span><span class="sxs-lookup"><span data-stu-id="e08bd-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e08bd-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e08bd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e08bd-104">Lync Server 2013에서는 중단 시 할당 되지 않은 번호로 전화를 걸 수 있는 알림을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="e08bd-105">중단 시 알림 기능을 복원하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="e08bd-106">중단 시 알림을 복원하려는 경우 백업 풀에서 알림 구성을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="e08bd-107">이 섹션에서는 재해 복구 시 알림을 복원하려는 경우 수행해야 할 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="e08bd-108">이 섹션은 알림 응용 프로그램을 사용 하는 할당 되지 않은 번호 범위에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="e08bd-109">이 섹션은 Exchange UM (통합 메시징) 자동 전화 교환을 사용 하는 할당 되지 않은 번호 범위에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="e08bd-110">중단 전 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="e08bd-110">Before an Outage</span></span>

<span data-ttu-id="e08bd-111">중단 시간 중에 알림을 사용할지 여부에 관계 없이 알림 응용 프로그램에 대해 구성한 모든 사용자 지정 오디오 파일을 별도로 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="e08bd-112">사용자 지정 된 알림은 Lync Server 재해 복구 프로세스의 일부로 백업 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="e08bd-113">이러한 파일의 별도 백업을 만들지 않은 상태에서 서버 또는 풀에 업로드한 파일이 손상되거나 삭제될 경우 파일이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="e08bd-114">사용자 지정 된 오디오 파일의 백업 복사본이 없고 원본 오디오 파일을 더 이상 사용할 수 없는 경우 알림 응용 프로그램에 대해 구성한 오디오 파일을 찾으려면 처음에 파일을 가져온 서버나 풀에 대 한 파일 저장소에서 검색 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="e08bd-115">알림 응용 프로그램에 대해 구성한 모든 오디오 파일을 파일 저장소에서 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="e08bd-116">**파일 저장소에서 오디오 파일을 복사 하려면**</span><span class="sxs-lookup"><span data-stu-id="e08bd-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="e08bd-117">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="e08bd-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="e08bd-119">여기서 X-ApplicationServer-X는 풀의 응용 프로그램 서버의 서비스 ID(예: 1-ApplicationServer-1")를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="e08bd-120">중단 도중 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="e08bd-120">During an Outage</span></span>

<span data-ttu-id="e08bd-121">중단 되는 동안 알림 응용 프로그램을 사용 하려면이 섹션에서 설명 하는 작업을 수행 하 여 백업 풀에서 알림 구성을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e08bd-122">이러한 작업은 백업 풀로 장애 조치한(failover) 후에 수행하는 것이 좋습니다. 2단계를 수행하자마자 할당되지 않은 번호 범위를 백업 풀에서 소유하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e08bd-123">이러한 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용하는 번호 범위에는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e08bd-124">**백업 풀에서 알림 구성을 다시 만들려면**</span><span class="sxs-lookup"><span data-stu-id="e08bd-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="e08bd-125">백업 풀에서 다음을 수행하여 주 풀에 배포한 알림을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="e08bd-126">**Import-CsAnnouncementFile** cmdlet을 사용하고 Parent 매개 변수에 백업 풀을 지정하여 주 풀에서 사용된 모든 오디오 파일을 해당 백업 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="e08bd-127">**New-CsAnnouncement** cmdlet을 사용하고 Parent 매개 변수에 백업 풀을 지정하여 각 알림을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e08bd-128">이러한 매개 변수를 사용 하 여 백업 풀에서 알림을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">create a 공고 in The Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e08bd-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="e08bd-129">백업 풀에서 모든 알림을 다시 만든 후에는 주 풀에서 알림을 사용하는, 할당되지 않은 모든 번호 범위를 백업 풀에 다시 만든 알림으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="e08bd-130">주 풀에서 알림을 사용하는, 할당되지 않은 각 번호 범위를 얻으려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="e08bd-131">중단 후 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="e08bd-131">After the Outage</span></span>

<span data-ttu-id="e08bd-132">주 풀을 사용할 수 있게 되면 중단 시 변경한 할당되지 않은 번호 범위를 주 풀로 다시 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e08bd-133">이러한 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용하는 번호 범위에는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e08bd-134">**기본 풀에서 알림을 복원 하려면**</span><span class="sxs-lookup"><span data-stu-id="e08bd-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="e08bd-p105">복구 시 주 풀을 재구성해야 했던 경우, 백업 풀에서 한 것처럼(단, Parent 매개 변수에 주 풀을 지정) 오디오 파일을 가져오고 알림을 만들어 주 풀에서 알림을 다시 만들어야 합니다. 자세한 내용은 이 항목 앞부분에 있는 "중단 도중 수행할 작업"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e08bd-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="e08bd-137">중단 시 변경한 할당되지 않은 각 번호 범위를 얻으려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="e08bd-138">필요한 경우 백업 풀에서 다시 만든 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="e08bd-139">백업 풀 알림 응용 프로그램에 대 한 공지 사항 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="e08bd-140">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="e08bd-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="e08bd-p107">결과로 반환된 목록에서 제거할 알림을 찾아 GUID를 복사합니다. 제거할 각 알림에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="e08bd-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e08bd-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

