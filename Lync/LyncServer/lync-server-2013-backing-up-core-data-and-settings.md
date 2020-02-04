---
title: 'Lync Server 2013: 핵심 데이터 및 설정 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="41031-102">Lync Server 2013에서 핵심 데이터 및 설정 백업</span><span class="sxs-lookup"><span data-stu-id="41031-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41031-103">_**마지막으로 수정한 주제:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="41031-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="41031-104">다음 절차에서는 Lync Server Management Shell cmdlet을 사용 하 여 설정 및 핵심 서비스의 데이터에 대 한 백업 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41031-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="41031-105">위치를 포함 하 여이 섹션에 사용 된 도구에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41031-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="41031-106">보관 및 모니터링 데이터 백업에 대 한 자세한 내용은 [Lync Server 2013에서 보관 및 모니터링 데이터베이스 백업을](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41031-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41031-107">중앙 관리 저장소를 백업 하는이 섹션의 단계에서는 보관 및 모니터링에 대 한 설정 및 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="41031-108">이 섹션에 설명 된 cmdlet을 로컬 또는 원격으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="41031-109">핵심 데이터 및 설정을 백업 하려면</span><span class="sxs-lookup"><span data-stu-id="41031-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="41031-110">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41031-111">다음 단계에서 만든 백업을 저장 하려면 새 공유 폴더를 만들고 **$Backup** 에서 참조 하는 경로를 새 공유 폴더로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="41031-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="41031-113">중앙 관리 저장소 구성 파일을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="41031-114">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="41031-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41031-116">이 단계에서는 Lync Server 토폴로지, 정책 및 구성 설정을 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="41031-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="41031-117">다른 단계는 토폴로지 데이터를 백업 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="41031-118">백업 된 중앙 관리 저장소 구성 파일을 $Backup\\에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="41031-119">위치 정보 서비스 데이터를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-119">Back up Location Information service data.</span></span> <span data-ttu-id="41031-120">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="41031-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="41031-122">$Backup\\에 백업 된 위치 정보 서비스 구성 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="41031-123">프런트 엔드 풀과 모든 Standard Edition 서버의 모든 백 엔드 데이터베이스에 있는 사용자 데이터를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="41031-124">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="41031-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="41031-126">$Backup\\에 백업 된 사용자 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="41031-127">응답 그룹 응용 프로그램을 실행 하는 모든 풀에서 응답 그룹 구성을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="41031-128">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="41031-129">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="41031-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41031-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="41031-131">$Backup\\에 백업 된 응답 그룹 구성 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="41031-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

