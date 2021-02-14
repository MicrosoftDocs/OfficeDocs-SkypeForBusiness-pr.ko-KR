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
description: 통화 파킹 응용 프로그램 마이그레이션에는 레거시 설치에 업로드된 사용자 지정 보류 음악 파일을 사용하여 비즈니스용 Skype 서버 2019 풀을 프로비전하고, 서비스 수준 설정을 복원하고, 모든 통화 파킹된 통화 파킹된 통화를 비즈니스용 Skype 서버 2019 풀로 다시 지정하는 것이 포함됩니다. 사용자 지정된 보류 음악 파일이 풀에 구성된 경우 이러한 파일을 새 비즈니스용 Skype 서버 2019 풀에 복사해야 합니다. 또한 통화 파크에 대해 업로드된 사용자 지정된 통화 보류 음악 파일의 별도의 백업 복사본을 보관하기 위해 통화 파크 사용자 지정 통화 보류 음악 파일을 다른 대상으로 백업하는 것이 좋습니다. 통화 파크 응용 프로그램에 대한 사용자 지정된 보류 음악 파일은 풀의 파일 저장소에 저장됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소로 복사하려면 다음 매개 변수와 함께 Xcopy 명령을 사용합니다.
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752820"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="ca614-107">통화 대기 응용 프로그램 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ca614-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="ca614-108">통화 파킹 응용 프로그램 마이그레이션에는 레거시 설치에 업로드된 사용자 지정 보류 음악 파일을 사용하여 비즈니스용 Skype 서버 2019 풀을 프로비전하고, 서비스 수준 설정을 복원하고, 모든 통화 파킹된 통화를 비즈니스용 Skype 서버 2019 풀로 다시 대상으로 지정하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ca614-109">사용자 지정된 보류 음악 파일이 풀에 구성된 경우 이러한 파일을 새 비즈니스용 Skype 서버 2019 풀에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ca614-110">또한 통화 파크에 대해 업로드된 사용자 지정된 통화 보류 음악 파일의 별도의 백업 복사본을 보관하기 위해 통화 파크 사용자 지정 통화 보류 음악 파일을 다른 대상에 백업하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="ca614-111">통화 파크 응용 프로그램에 대한 사용자 지정된 보류 음악 파일은 풀의 파일 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="ca614-112">풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소로 복사하려면 다음 매개 변수와 **함께 Xcopy** 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="ca614-113">사용자 지정된 모든 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사한 경우 비즈니스용 Skype 서버 2019 풀의 통화 파크 응용 프로그램 설정을 구성해야 합니다. 레거시 풀과 연결된 통화 파크 파선 범위를 비즈니스용 Skype 서버 2019 풀에 다시 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="ca614-114">통화 파킹 응용 프로그램 설정에는 Pickup timeout threshold, enabling or disabling music on hold, maximum call pickup attempts, and the timeout request.</span><span class="sxs-lookup"><span data-stu-id="ca614-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="ca614-115">**Set-CsCpsConfiguration** cmdlet을 실행하려면 비즈니스용 Skype 서버 관리 셸을 사용하여 통화 파킹 응용 프로그램 설정을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="ca614-116">비즈니스용 Skype 서버 제어판을 사용하여 통화 파크 응용 프로그램 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="ca614-117">통화 파크 서비스 설정 다시 구성</span><span class="sxs-lookup"><span data-stu-id="ca614-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="ca614-118">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ca614-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ca614-119">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca614-120">비즈니스용 Skype 서버 2019 통화 파기 응용 프로그램 설정이 레거시 설정과 동일한 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="ca614-121">비즈니스용 Skype 서버 2019 및 레거시 환경에 대해 통화 파킹 응용 프로그램 설정이 다른 경우 아래 cmdlet을 템플릿으로 사용하여 해당 변경 내용을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="ca614-122">레거시 풀에서 비즈니스용 Skype 서버 2019 풀로 모든 통화 파크 파운데이트 파크 궤도 범위를 다시 재할당하기 위해 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ca614-123">비즈니스용 Skype 서버 제어판을 사용하여 모든 통화 파크 궤도 범위 재할당</span><span class="sxs-lookup"><span data-stu-id="ca614-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ca614-124">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ca614-125">왼쪽 창에서 음성 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca614-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="ca614-126">통화 **파크 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="ca614-127">레거시 풀에 할당된 각 통화 파크 파선 범위에 대해 대상 서버 **설정의 FQDN을** 편집하고 통화 파크 요청을 처리하기 위한 비즈니스용 Skype 서버 2019 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="ca614-128">변경 **내용을** 저장하려면 커밋을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ca614-129">비즈니스용 Skype 서버 관리 셸을 사용하여 모든 통화 파크 파운데이트 범위 다시 전송</span><span class="sxs-lookup"><span data-stu-id="ca614-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ca614-130">비즈니스용 Skype 서버 관리 셸을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ca614-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ca614-131">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="ca614-132">이 cmdlet은 배포의 모든 통화 파킹된 통화 궤도 범위를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="ca614-133">**CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 레거시 풀로 설정한 모든 통화 파킹된 통화 궤도는 다시 배정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="ca614-134">레거시 통화 파크 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 재할당하기 위해 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="ca614-135">모든 통화 파킹된 통화선 범위를 비즈니스용 Skype 서버 2019 풀에 다시 다시 위임하고 나면 통화 파킹 응용 프로그램에 대한 마이그레이션 프로세스가 완료됩니다. 비즈니스용 Skype 서버 2019 풀은 이후의 모든 통화 파킹 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca614-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


