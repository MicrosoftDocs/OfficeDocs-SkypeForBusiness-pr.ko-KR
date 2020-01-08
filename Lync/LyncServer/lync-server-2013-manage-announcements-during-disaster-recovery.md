---
title: 'Lync Server 2013: 재해 복구 시 알림 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="28800-102">Lync Server 2013에서 재해 복구 시 알림 관리</span><span class="sxs-lookup"><span data-stu-id="28800-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28800-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="28800-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="28800-104">Lync Server 2013는 작동 중단 중에 할당 되지 않은 번호로 전화를 걸 때의 알림을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="28800-105">중단 중에 알림 기능을 복원 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="28800-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="28800-106">중단 중에 알림을 복원 하도록 선택한 경우에는 백업 풀에 알림 구성을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="28800-107">이 섹션에서는 재해 복구 중에 알림을 복원 하도록 선택한 경우 수행 해야 할 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="28800-108">이 섹션은 공지 사항 응용 프로그램을 사용 하는 지정 되지 않은 숫자 범위에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28800-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="28800-109">이 섹션은 Exchange UM (통합 메시징) 자동 전화 교환을 사용 하는 지정 되지 않은 숫자 범위에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="28800-110">중단 전</span><span class="sxs-lookup"><span data-stu-id="28800-110">Before an Outage</span></span>

<span data-ttu-id="28800-111">중단 중에 알림을 사용할지 여부에 관계 없이 알림 응용 프로그램에 대해 구성한 모든 사용자 지정 오디오 파일을 별도의 백업으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="28800-112">사용자 지정 된 알림은 Lync Server 재해 복구 프로세스의 일부로 백업 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="28800-113">파일을 별도로 백업 하지 않고 서버 또는 풀에 업로드 한 파일이 손상, 손상 또는 지워진 경우 파일이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28800-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="28800-114">사용자 지정 오디오 파일의 백업 복사본이 없고 원본 오디오 파일을 더 이상 사용할 수 없는 경우, 원래 위치에 있는 서버 또는 풀에 대 한 파일 저장소에서 알림 응용 프로그램에 대해 구성한 오디오 파일을 찾을 수 있습니다. 파일을 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="28800-115">파일 저장소에서 알림 신청에 대해 구성한 모든 오디오 파일을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="28800-116">**파일 저장소에서 오디오 파일을 복사 하려면**</span><span class="sxs-lookup"><span data-stu-id="28800-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="28800-117">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="28800-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="28800-119">여기서 X-ApplicationServer-X는 풀의 응용 프로그램 서버의 서비스 ID를 참조 합니다 (예: 1-ApplicationServer-1 ").</span><span class="sxs-lookup"><span data-stu-id="28800-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="28800-120">중단 하는 동안</span><span class="sxs-lookup"><span data-stu-id="28800-120">During an Outage</span></span>

<span data-ttu-id="28800-121">중단 하는 동안 알림 응용 프로그램을 사용 하려면이 섹션에서 설명 하는 작업을 수행 하 여 백업 풀에 알림 구성을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28800-122">백업 풀에 대 한 작업을 수행 하는 즉시 백업 풀이 할당 되지 않은 번호 범위에 대 한 소유권을 가지 므 때문에이 두 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="28800-123">이 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용 하는 숫자 범위에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="28800-124">**백업 풀에서 알림 구성 다시 만들기**</span><span class="sxs-lookup"><span data-stu-id="28800-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="28800-125">다음을 수행 하 여 백업 풀의 기본 풀에 배포한 알림을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28800-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="28800-126">**CsAnnouncementFile** cmdlet을 사용 하 고 부모 매개 변수에 대 한 백업 풀을 지정 하 여 기본 풀에 사용 되는 오디오 파일을 백업 풀에 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28800-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="28800-127">**새 csannouncement** cmdlet을 사용 하 고 부모 매개 변수에 대 한 백업 풀을 지정 하 여 각 알림을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28800-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28800-128">이러한 매개 변수를 사용 하 여 백업 풀에 알림을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 공지 만들기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28800-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="28800-129">백업 풀에 모든 알림이 다시 만들어진 후에는 기본 풀의 공지 사항을 사용 하는 모든 할당 되지 않은 번호 범위를 백업 풀의 재작성 된 공지 사항으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="28800-130">기본 풀에서 알림을 사용 하는 각 할당 되지 않은 숫자 범위에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="28800-131">중단 후</span><span class="sxs-lookup"><span data-stu-id="28800-131">After the Outage</span></span>

<span data-ttu-id="28800-132">주 풀을 사용할 수 있게 되 면 중단에 대해 변경한 할당 되지 않은 번호 범위를 다시 기본 풀로 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28800-133">이 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용 하는 숫자 범위에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="28800-134">**기본 풀에서 알림을 복원 하려면**</span><span class="sxs-lookup"><span data-stu-id="28800-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="28800-135">복구 하는 동안 기본 풀을 다시 작성 해야 하는 경우 부모에 대 한 기본 풀을 지정 하는 경우를 제외 하 고 백업 풀에서와 마찬가지로 오디오 파일을 가져오고 알림을 만들어 기본 풀에 알림을 다시 만들어야 합니다. 변수도.</span><span class="sxs-lookup"><span data-stu-id="28800-135">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter.</span></span> <span data-ttu-id="28800-136">자세한 내용은이 항목의 앞부분에 있는 "중단 하는 동안"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28800-136">For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="28800-137">중단을 위해 변경한 각 할당 되지 않은 숫자 범위에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="28800-138">필요에 따라 백업 풀에서 다시 만든 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="28800-139">백업 풀 알림 응용 프로그램의 공지 사항 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28800-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="28800-140">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="28800-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="28800-142">결과 목록에서 제거 하 고 Guid를 복사 하려는 공지 사항을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-142">In the resulting list, locate the announcements you want to remove and copy the GUIDs.</span></span> <span data-ttu-id="28800-143">제거 하려는 각 공지 사항에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28800-143">For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="28800-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28800-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

