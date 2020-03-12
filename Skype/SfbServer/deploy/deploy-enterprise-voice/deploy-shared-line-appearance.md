---
title: 비즈니스용 Skype 서버 2015에 공유 선 모양 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 비즈니스용 Skype 서버 2015, 2015의 11 월 누적 업데이트에 SLA (공유 선 모양)를 배포 하는 방법을 알아보려면이 항목을 읽어 보십시오. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 기능입니다.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604225"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="d8d1a-104">비즈니스용 Skype 서버 2015에 공유 선 모양 배포</span><span class="sxs-lookup"><span data-stu-id="d8d1a-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="d8d1a-105">비즈니스용 Skype 서버 2015, 2015의 11 월 누적 업데이트에 SLA (공유 선 모양)를 배포 하는 방법을 알아보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d8d1a-106">SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="d8d1a-107">이 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에서 공유 라인 모양 계획](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="d8d1a-108">SLA (공유 선 모양)는 비즈니스용 Skype 서버의 새로운 기능이 며 11 월 2015 누적 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d8d1a-109">이 기능을 사용 하도록 설정 하려면 먼저이 누적 업데이트를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="d8d1a-110">공유 선 모양 설치</span><span class="sxs-lookup"><span data-stu-id="d8d1a-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="d8d1a-111">비즈니스용 Skype 서버, 2015 11 월 누적 업데이트가 배포 되 면 풀의 각 `SkypeServerUpdateInstaller.exe` 프런트 엔드 서버에서 패치를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="d8d1a-112">설치 관리자가 SLA 응용 프로그램의 최신 버전을 배포 하지만 응용 프로그램은 기본적으로 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="d8d1a-113">아래에 설명 된 단계에 따라 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="d8d1a-114">a.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-114">a.</span></span> <span data-ttu-id="d8d1a-115">각 풀에 대해 다음 명령을 실행 하 여 SLA를 서버 응용 프로그램으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="d8d1a-116">여기서% FQDN%는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="d8d1a-117">b.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-117">b.</span></span> <span data-ttu-id="d8d1a-118">다음 명령을 실행 하 여 SLA cmdlet에 대 한 RBAC 역할을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="d8d1a-119">c.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-119">c.</span></span> <span data-ttu-id="d8d1a-120">SLA가 설치 되어 있고 사용 하도록 설정 된 모든 풀에서 모든 프런트 엔드 서버 (RTCSRV 서비스)를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="d8d1a-121">SLA 그룹을 만들고 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="d8d1a-122">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="d8d1a-123">CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1를 SLA 엔터티로 표시 하 고 SLAGroup1의 수는 SLA 그룹의 숫자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="d8d1a-124">SLAGroup1에 대 한 모든 호출이 전체 SLA 그룹에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="d8d1a-125">다음은 기존 Enterprise Voice 사용자에 대 한 SLA 그룹을 만들고 SLAGroup1에 SLAGroup1에 대해 지정 된 번호를 SLA의 중요 번호로 사용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="d8d1a-126">이 명령은 새 SLA 그룹에 대 한 최대 동시 통화 수를 3으로 설정 하 고,이를 초과 하 여 통화 중 신호를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="d8d1a-127">CsSlaConfiguration을 사용 하 여 새 SLA 그룹을 만들거나 기존 항목을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8d1a-128">지정 하는 항목은 유효한 `-Identity` 기존 Enterprise Voice 사용 가능 사용자 계정 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="d8d1a-129">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에 대리인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="d8d1a-130">다음은 SLA 그룹에 사용자를 추가 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="d8d1a-131">그룹에 추가 되는 각 사용자는 유효한 Enterprise Voice 사용이 가능한 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="d8d1a-132">그룹에 추가 하려는 각 사용자에 대해 cmdlet을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="d8d1a-133">사용자는 단일 SLA 그룹에만 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="d8d1a-134">SLA 그룹 약속 있음 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d8d1a-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="d8d1a-135">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 사용 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="d8d1a-136">다음 예에서는 전화 번호 202-555-1234으로 전달 되는 최대 동시 통화 수를 초과 하는 통화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="d8d1a-137">대상은 전화 번호 대신 조직의 사용자 일 수 있습니다. 이 경우 착신 전환 된 전화를 받는 사람에 대 한 구문은 대리인을 지정할 때와 같습니다 `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="d8d1a-138">그 밖의 `BusyOption` 가능한 매개 변수 `Voicemail`는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="d8d1a-139">SLA 그룹 부재 중 전화 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d8d1a-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="d8d1a-140">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 부재 중 전화 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="d8d1a-141">다음 예에서는 부재 중 전화가 라는 `sla_forward_number`사용자에 게 착신 전환 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="d8d1a-142">`-MissedCallOption` 매개 변수에 사용할 수 `Forward`있는 옵션은, `BusySignal`또는 `Disconnect`입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="d8d1a-143">을 선택 `Forward`하는 경우에는 다음과 같이 `-MissedCallForwardTarget` 사용자 또는 전화 번호를 대상으로 매개 변수도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="d8d1a-144">그룹에서 대리인 제거</span><span class="sxs-lookup"><span data-stu-id="d8d1a-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="d8d1a-145">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에서 대리인을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="d8d1a-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="d8d1a-147">SLA 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="d8d1a-147">Delete an SLA group</span></span>

- <span data-ttu-id="d8d1a-148">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="d8d1a-149">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d1a-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


