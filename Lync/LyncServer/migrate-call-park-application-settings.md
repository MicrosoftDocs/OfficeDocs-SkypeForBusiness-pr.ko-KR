---
title: 통화 대기 응용 프로그램 설정 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789a8a83c8f3ee831fb91c85999d936ea54dd8b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="446c6-102">통화 대기 응용 프로그램 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="446c6-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="446c6-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="446c6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="446c6-104">Lync server 2010에서 Lync Server 2013로의 통화 대기 응용 프로그램 마이그레이션에는 lync server 2010에 업로드 된 사용자 지정 음악을 포함 하 여 Lync Server 2013 풀을 프로 비전 하 고, 서비스 수준 설정을 복원 하 고 모든 통화 대기 궤도을 Lync Server 2013 풀로 다시 설정 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="446c6-105">Lync Server 2010 풀에 사용자 지정 된 음악 대기 파일을 구성한 경우 이러한 파일을 새 Lync Server 2013 풀로 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="446c6-106">또한 통화 대기에 업로드 된 사용자 지정 된 모든 음악 준비 파일의 별도 백업 복사본을 유지 하기 위해 Lync Server 2010에서 모든 통화 보류 음악 파일을 다른 대상으로 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="446c6-107">통화 대기 응용 프로그램에 대 한 사용자 지정 된 음악 보존 파일은 해당 풀의 파일 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="446c6-108">Lync Server 2010 풀 파일 저장소의 오디오 파일을 Lync Server 2013 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="446c6-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="446c6-109">사용자 지정 된 모든 오디오 파일을 Lync Server 2013 파일 저장소로 복사한 후에는 Lync server 2013 풀의 통화 대기 응용 프로그램 설정을 구성 해야 하며 Lync server 2010 풀과 연결 된 통화 대기 번호 범위를 Lync Server 2013 풀에 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="446c6-110">통화 대기 응용 프로그램 설정에는 픽업 시간 제한 임계값이 포함 되며 보류 중인 음악을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="446c6-111">Lync Server 관리 셸을 사용 하 여 **new-cscpsconfiguration** cmdlet을 실행 하 여 통화 대기 응용 프로그램 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="446c6-112">Lync Server 제어판을 사용 하 여 통화 대기 응용 프로그램 설정을 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="446c6-113">**통화 대기 서비스 설정 다시 구성**</span><span class="sxs-lookup"><span data-stu-id="446c6-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="446c6-114">Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="446c6-115">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="446c6-116">Lync Server 2013 통화 대기 응용 프로그램 설정이 레거시 Lync Server 2010 설정과 동일한 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="446c6-117">Lync Server 2013 및 Lync Server 2010 환경에 대해 통화 대기 응용 프로그램 설정이 다르면 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 하십시오.</span><span class="sxs-lookup"><span data-stu-id="446c6-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="446c6-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-enablemusiconhold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-ontimeouturi" <LS2010 CPS timeout URI> "```</span><span class="sxs-lookup"><span data-stu-id="446c6-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="446c6-119">Lync server 2010 풀의 모든 통화 대기 번호 범위를 Lync Server 2013 풀로 다시 할당 하려면 Lync Server 제어판 또는 Lync Server 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="446c6-120">**Lync Server 제어판을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당**</span><span class="sxs-lookup"><span data-stu-id="446c6-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="446c6-121">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="446c6-122">왼쪽 창에서 **음성 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="446c6-123">**통화** 대기 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="446c6-124">Lync Server 2010 풀에 할당 된 각 통화 대기 번호 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 대기 요청을 처리할 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="446c6-125">**커밋을** 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="446c6-126">**Lync Server 관리 셸을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당**</span><span class="sxs-lookup"><span data-stu-id="446c6-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="446c6-127">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="446c6-128">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="446c6-129">이 cmdlet은 배포의 모든 통화 대기 번호 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="446c6-130">**CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 Lync Server 2010 Pool로 설정한 모든 통화 대기 궤도를 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="446c6-131">Lync server 2010 통화 대기 번호 범위를 Lync Server 2013 풀에 다시 할당 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="446c6-132">모든 통화 대기 궤도 범위를 Lync Server 2013 풀에 다시 할당 하면 통화 대기 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 Lync Server 2013 풀에서 이후의 모든 통화 대기 요청이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="446c6-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

