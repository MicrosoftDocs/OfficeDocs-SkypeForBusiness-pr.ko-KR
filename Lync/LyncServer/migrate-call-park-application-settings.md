---
title: 통화 대기 응용 프로그램 설정 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba55ec7ff54858d3324df2ab8794176a5dc7a10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="f92ae-102">통화 대기 응용 프로그램 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f92ae-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f92ae-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f92ae-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f92ae-104">Lync server 2010에서 Lync server 2013로 전화 연결을 마이그레이션하는 경우 lync server 2010에서 업로드 된 보류 파일의 사용자 지정 음악을 사용 하 여 Lync Server 2013 풀을 제공 하 고 서비스 수준 설정 및 대상 설정을 복원 하는 기능이 포함 됩니다. 모든 통화 공원는 Lync Server 2013 풀로 orbits.</span><span class="sxs-lookup"><span data-stu-id="f92ae-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f92ae-105">사용자 지정 된 음악 저장 파일을 Lync Server 2010 풀에서 구성한 경우 이러한 파일을 새 Lync Server 2013 풀에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="f92ae-106">또한, 통화 공원에 업로드 된 사용자 지정 음악 보관 파일에 대 한 별도의 백업 복사본을 유지 하기 위해 Lync Server 2010의 모든 통화 대기 파일을 다른 목적지로 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="f92ae-107">통화 공원 응용 프로그램에 대해 사용자 지정 된 음악 보관 파일은 풀의 파일 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="f92ae-108">Lync Server 2010 풀 파일 저장소의 오디오 파일을 Lync Server 2013 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="f92ae-109">모든 사용자 지정 오디오 파일이 Lync Server 2013 파일 저장소에 복사 된 경우 Lync Server 2013 풀의 통화 대기 응용 프로그램 설정을 구성 하 고 Lync Server 2010 풀과 연결 된 통화 대기 궤도 범위를 다시 할당 해야 합니다. Lync Server 2013 풀.</span><span class="sxs-lookup"><span data-stu-id="f92ae-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="f92ae-110">통화 공원 응용 프로그램 설정에는 픽업 시간 제한 임계값이 포함 되어 있으며 보류 중인 음악을 허용 하거나 사용 하지 않도록 설정할 수 있습니다 (최대 통화 픽업 시도 횟수와 시간 초과 요청).</span><span class="sxs-lookup"><span data-stu-id="f92ae-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="f92ae-111">**CsCpsConfiguration** cmdlet을 실행 하려면 Lync Server Management Shell을 사용 하 여 통화 공원 응용 프로그램 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="f92ae-112">Lync Server 제어판을 사용 하 여 통화 공원 응용 프로그램 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="f92ae-113">**통화 공원 서비스 설정 다시 구성**</span><span class="sxs-lookup"><span data-stu-id="f92ae-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="f92ae-114">Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f92ae-115">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f92ae-116">Lync Server 2013 통화 공원 응용 프로그램 설정이 레거시 Lync Server 2010 설정과 동일한 경우이 단계 실행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="f92ae-117">통화 공원 응용 프로그램 설정이 Lync Server 2013 및 Lync Server 2010 환경과 다른 경우 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="f92ae-118">Lync Server 2010 풀에서 lync server 2013 풀로 모든 통화 공원 궤도 범위를 다시 할당 하려면 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="f92ae-119">**Lync Server 제어판을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당**</span><span class="sxs-lookup"><span data-stu-id="f92ae-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="f92ae-120">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="f92ae-121">왼쪽 창에서 **음성 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="f92ae-122">**통화 공원** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="f92ae-123">Lync Server 2010 풀에 할당 된 각 통화 대기 궤도 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 대기 요청을 처리 하는 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="f92ae-124">**커밋을** 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="f92ae-125">**Lync Server Management Shell을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당**</span><span class="sxs-lookup"><span data-stu-id="f92ae-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="f92ae-126">Lync Server Management Shell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f92ae-127">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="f92ae-128">이 cmdlet은 배포의 모든 통화 공원 궤도 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="f92ae-129">Lync Server 2010 풀로 설정 된 **CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 사용 하는 모든 통화 대기 orbits을 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="f92ae-130">Lync server 2010 통화 공원 회전 범위를 Lync Server 2013 풀에 다시 할당 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="f92ae-131">모든 통화 공원 궤도 범위를 Lync Server 2013 풀에 다시 할당 한 후에는 통화 공원 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 Lync Server 2013 풀에서 이후의 모든 이후 통화 대기 요청이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f92ae-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

