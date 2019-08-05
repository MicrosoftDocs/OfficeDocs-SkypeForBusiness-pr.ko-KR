---
title: 통화 공원 앱 설정 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 통화 대기 응용 프로그램의 마이그레이션에는 비즈니스용 Skype 서버 2019 풀을 레거시 설치에 업로드 된 보류 파일에 있는 사용자 지정 음악으로 프로 비전 하 고, 서비스 수준 설정을 복원 하 고, 모든 통화 공원 orbits 비즈니스용 Skype 서버 2019 풀. 사용자 지정 된 음악 보관 파일을 풀에서 구성한 경우 이러한 파일을 새 비즈니스용 Skype Server 2019 풀에 복사 해야 합니다. 또한 통화 대기를 위해 업로드 된 사용자 지정 음악 보관 파일에 대 한 별도의 백업 복사본을 유지 하기 위해 모든 통화 공원 사용자 지정 된 음악 파일을 다른 대상에 백업 하는 것이 좋습니다. 통화 공원 응용 프로그램에 대해 사용자 지정 된 음악 보관 파일은 풀의 파일 저장소에 저장 됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 Xcopy 명령을 사용 합니다.
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189084"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="b4828-107">통화 공원 앱 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b4828-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="b4828-108">통화 공원 응용 프로그램 마이그레이션에는 레거시 설치에 업로드 된 사용자 지정 음악 보관 파일과 함께 비즈니스용 Skype 서버 2019 풀 프로비저닝이 포함 되며, 서비스 수준 설정을 복원 하 고, 모든 통화 대기 orbits을 다시 지정 합니다. 비즈니스용 Skype 서버 2019 풀로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b4828-109">사용자 지정 된 음악 보관 파일을 풀에서 구성한 경우 이러한 파일을 새 비즈니스용 Skype Server 2019 풀에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b4828-110">또한, 통화 대기를 위해 업로드 된 사용자 지정 음악 보관 파일의 별도 백업 복사본을 유지 하기 위해 모든 통화 공원 사용자 지정 된 음악 파일을 다른 대상에 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="b4828-111">통화 공원 응용 프로그램에 대해 사용자 지정 된 음악 보관 파일은 풀의 파일 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="b4828-112">풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="b4828-113">사용자 지정 된 모든 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사한 경우 비즈니스용 Skype Server 2019 풀의 통화 공원 응용 프로그램 설정을 구성 하 고 레거시 풀과 연결 된 통화 공원 궤도 범위를 사용 해야 합니다. 비즈니스용 Skype 서버 2019 풀에 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="b4828-114">통화 공원 응용 프로그램 설정에는 픽업 시간 제한 임계값, 보류 중인 음악을 활성화 또는 비활성화, 최대 통화 픽업 시도 횟수, 제한 시간 요청이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="b4828-115">**CsCpsConfiguration** cmdlet을 실행 하려면 비즈니스용 Skype Server Management Shell을 사용 하 여 통화 공원 응용 프로그램 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="b4828-116">비즈니스용 Skype 서버 제어판을 사용 하 여 통화 공원 응용 프로그램 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="b4828-117">통화 공원 서비스 설정 다시 구성</span><span class="sxs-lookup"><span data-stu-id="b4828-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="b4828-118">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b4828-119">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4828-120">비즈니스용 Skype 서버 2019 통화 공원 응용 프로그램 설정이 레거시 설정과 동일한 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="b4828-121">통화 공원 응용 프로그램 설정이 비즈니스용 Skype 서버 2019 및 레거시 환경과 다르면 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="b4828-122">레거시 풀의 모든 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 하려면 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b4828-123">비즈니스용 Skype Server 제어판을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당</span><span class="sxs-lookup"><span data-stu-id="b4828-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b4828-124">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="b4828-125">왼쪽 창에서 **음성 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="b4828-126">**통화 공원** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="b4828-127">레거시 풀에 할당 된 각 통화 대기 궤도 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 공원 요청을 처리 하는 비즈니스용 Skype server 2019 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="b4828-128">**커밋을** 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b4828-129">비즈니스용 Skype Server Management Shell을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당</span><span class="sxs-lookup"><span data-stu-id="b4828-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b4828-130">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b4828-131">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="b4828-132">이 cmdlet은 배포의 모든 통화 공원 궤도 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="b4828-133">**CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 레거시 풀로 설정 하는 모든 통화 대기 orbits을 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="b4828-134">레거시 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="b4828-135">모든 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 한 후에는 통화 대기 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 비즈니스용 Skype 서버 2019 풀에서 이후의 모든 통화 대기 요청이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4828-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


