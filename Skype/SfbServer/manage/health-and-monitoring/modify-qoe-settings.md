---
title: 비즈니스용 Skype 서버에서 환경 품질 설정 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '요약: 비즈니스용 Skype 서버에서 QoE 데이터의 보존을 지정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 18776e9b8eec9dcff6ced9f654d8153d7fa01777
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827798"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="6eb58-103">비즈니스용 Skype 서버에서 환경 품질 설정 수정</span><span class="sxs-lookup"><span data-stu-id="6eb58-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="6eb58-104">**요약:** 비즈니스용 Skype 서버에서 QoE 데이터의 보존을 지정하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="6eb58-p101">QoE(체감 품질) 데이터는 기본적으로 60일 후에 삭제됩니다. **체감 품질 데이터** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. QoE를 사용하지 않도록 설정한 경우 QoE를 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb58-p102">CDR(통화 정보 기록) 및 QoE의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 보고서 홈 페이지에 제공되는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="6eb58-111">다음 절차는 QoE 데이터에 대한 삭제 설정을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6eb58-112">비즈니스용 Skype 서버 제어판을 사용하여 QoE 데이터의 보존을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6eb58-113">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6eb58-114">자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6eb58-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="6eb58-115">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="6eb58-116">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="6eb58-117">**체감 품질 데이터** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="6eb58-118">삭제를 설정하려면 **QoE 삭제 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="6eb58-119">**최대 기간(일) 동안 QoE 유지** 에서 QoE 데이터를 보존할 최대 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="6eb58-120">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6eb58-121">Cmdlet을 사용하여 QoE Windows PowerShell 지정</span><span class="sxs-lookup"><span data-stu-id="6eb58-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6eb58-122">QoE 보존 설정은 Windows PowerShell **Set-CsQoEConfiguration** cmdlet을 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="6eb58-123">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb58-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6eb58-124">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6eb58-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6eb58-125">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="6eb58-126">특정 위치에 대한 QoE 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="6eb58-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="6eb58-127">이 명령은 Redmond 사이트에 대해 QoE 데이터 삭제를 사용하도록 설정하고 20일 동안 QoE 데이터를 유지하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="6eb58-128">여러 위치에 대한 QoE 보존을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="6eb58-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="6eb58-129">이 명령은 조직에서 사용 중인 모든 QoE 구성 설정에 대해 QoE 보존을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb58-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="6eb58-130">자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6eb58-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eb58-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6eb58-131">See also</span></span>

[<span data-ttu-id="6eb58-132">모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="6eb58-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
