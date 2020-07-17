---
title: 통화 대기 응용 프로그램 설정 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 통화 대기 응용 프로그램의 마이그레이션에는 레거시 설치에서 업로드 된 모든 사용자 지정 음악을 포함 하는 비즈니스용 Skype 서버 2019 풀을 프로 비전 하 고, 서비스 수준 설정을 복원 하 고, 모든 통화 대기 궤도를 비즈니스용 Skype 서버 2019 풀에 연결 하는 기능이 포함 되어 있습니다. 사용자 지정 된 음악 보존 파일을 풀에서 구성한 경우 이러한 파일을 새로운 비즈니스용 Skype 서버 2019 풀로 복사 해야 합니다. 또한 통화 대기를 위해 업로드 된 사용자 지정 된 모든 음악 준비 파일의 별도 백업 복사본을 유지 하기 위해 전화 걸기 사용자 지정 된 모든 음악 파일을 다른 대상으로 백업 하는 것이 좋습니다. 통화 대기 응용 프로그램에 대 한 사용자 지정 된 음악 보존 파일은 해당 풀의 파일 저장소에 저장 됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 Xcopy 명령을 사용 합니다.
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752820"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="8b35c-107">통화 대기 응용 프로그램 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8b35c-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="8b35c-108">통화 대기 응용 프로그램의 마이그레이션에는 레거시 설치에서 업로드 된 사용자 지정 음악 보존 파일을 사용 하 여 비즈니스용 Skype 서버 2019 풀을 구축 하 고, 서비스 수준 설정을 복원 하 고, 모든 통화 대기 궤도를 비즈니스용 Skype 서버 2019 풀로 다시 지정 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8b35c-109">사용자 지정 된 음악 보존 파일을 풀에서 구성한 경우 이러한 파일을 새로운 비즈니스용 Skype 서버 2019 풀로 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8b35c-110">또한 통화 대기를 위해 업로드 된 사용자 지정 된 모든 음악 준비 파일의 개별 백업 복사본을 유지 하려면 모든 통화 보류 사용자 지정 된 보존 파일을 다른 대상에 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="8b35c-111">통화 대기 응용 프로그램에 대 한 사용자 지정 된 음악 보존 파일은 해당 풀의 파일 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="8b35c-112">풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="8b35c-113">사용자 지정 된 모든 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소로 복사한 경우 비즈니스용 Skype 서버 2019 풀의 통화 대기 응용 프로그램 설정을 구성 해야 하며 레거시 풀과 연결 된 통화 대기 번호 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="8b35c-114">통화 대기 응용 프로그램 설정에는 픽업 시간 제한 임계값, 보류에 대 한 음악 사용/사용 안 함, 최대 통화 픽업 시도 횟수 및 시간 제한 요청이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="8b35c-115">비즈니스용 Skype 서버 관리 셸을 사용 하 여 **new-cscpsconfiguration** cmdlet을 실행 하 여 통화 대기 응용 프로그램 설정을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="8b35c-116">비즈니스용 Skype 서버 제어판을 사용 하 여 통화 대기 응용 프로그램 설정을 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="8b35c-117">통화 대기 서비스 설정 다시 구성</span><span class="sxs-lookup"><span data-stu-id="8b35c-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="8b35c-118">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8b35c-119">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b35c-120">비즈니스용 Skype 서버 2019 통화 대기 응용 프로그램 설정이 레거시 설정과 동일한 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="8b35c-121">비즈니스용 Skype 서버 2019 및 레거시 환경에 대해 통화 대기 응용 프로그램 설정이 다르면 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="8b35c-122">레거시 풀의 모든 통화 대기 번호 범위를 비즈니스용 Skype 서버 2019 풀로 다시 할당 하려면 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8b35c-123">비즈니스용 Skype 서버 제어판을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당</span><span class="sxs-lookup"><span data-stu-id="8b35c-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8b35c-124">비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8b35c-125">왼쪽 창에서 **음성 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="8b35c-126">**통화** 대기 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="8b35c-127">레거시 풀에 할당 된 각 통화 대기 번호 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 대기 요청을 처리할 비즈니스용 Skype 서버 2019 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="8b35c-128">**커밋을** 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8b35c-129">비즈니스용 Skype 서버 관리 셸을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당</span><span class="sxs-lookup"><span data-stu-id="8b35c-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8b35c-130">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8b35c-131">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="8b35c-132">이 cmdlet은 배포의 모든 통화 대기 번호 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="8b35c-133">**CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 레거시 풀로 설정 하는 모든 통화 대기 궤도를 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="8b35c-134">Skype for Business Server 2019 풀에 레거시 통화 대기 번호 범위를 다시 할당 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="8b35c-135">모든 통화 대기 번호 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 한 후에는 통화 대기 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 비즈니스용 Skype 서버 2019 풀에서 이후의 모든 통화 대기 요청이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b35c-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


