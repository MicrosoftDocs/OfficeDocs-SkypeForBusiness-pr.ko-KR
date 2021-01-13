---
title: 비즈니스용 Skype 서버 2015에서 공유 라인 모양 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 이 항목을 읽고 비즈니스용 Skype 서버 2015, 2015년 11월 누적 업데이트에서 SLA(공유 라인 모양)를 배포하는 방법을 배워 읽습니다. SLA는 공유 번호라는 특정 번호에서 여러 통화를 처리하는 기능입니다.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812408"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="ebde5-104">비즈니스용 Skype 서버 2015에서 공유 라인 모양 배포</span><span class="sxs-lookup"><span data-stu-id="ebde5-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="ebde5-105">이 항목을 읽고 비즈니스용 Skype 서버 2015, 2015년 11월 누적 업데이트에서 SLA(공유 라인 모양)를 배포하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="ebde5-106">SLA는 공유 번호라는 특정 번호에서 여러 통화를 처리하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="ebde5-107">이 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)공유 라인 모양 계획을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebde5-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="ebde5-108">SLA(공유 라인 모양)는 2015년 11월 누적 업데이트인 비즈니스용 Skype 서버의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="ebde5-109">이 기능을 사용하도록 설정하려면 이 누적 업데이트를 먼저 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="ebde5-110">공유 선 모양 설치</span><span class="sxs-lookup"><span data-stu-id="ebde5-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="ebde5-111">비즈니스용 Skype 서버가 2015년 11월 누적 업데이트가 배포된 후 풀의 각 프런트 엔드 서버에서  `SkypeServerUpdateInstaller.exe` 패치를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="ebde5-112">설치 관리자에서 최신 버전의 SLA 응용 프로그램을 배포합니다. 그러나 응용 프로그램은 기본적으로 사용하도록 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="ebde5-113">아래에 설명된 단계에 따라 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="ebde5-114">a.</span><span class="sxs-lookup"><span data-stu-id="ebde5-114">a.</span></span> <span data-ttu-id="ebde5-115">각 풀에 대해 다음 명령을 실행하여 SLA를 서버 응용 프로그램으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="ebde5-116">여기서 %FQDN%은 풀의 정식 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="ebde5-117">b.</span><span class="sxs-lookup"><span data-stu-id="ebde5-117">b.</span></span> <span data-ttu-id="ebde5-118">다음 명령을 실행하여 SLA cmdlet에 대한 RBAC 역할을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="ebde5-119">c.</span><span class="sxs-lookup"><span data-stu-id="ebde5-119">c.</span></span> <span data-ttu-id="ebde5-120">SLA가 설치 및 사용하도록 설정된 모든 풀에서 모든 프런트 엔드 서버(RTCSRV 서비스)를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="ebde5-121">SLA 그룹 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="ebde5-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="ebde5-122">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="ebde5-123">이 Set-CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1을 SLA 엔터티로 표시하고 SLAGroup1 수는 SLA 그룹의 번호가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="ebde5-124">SLAGroup1에 대한 모든 호출은 전체 SLA 그룹을 울리게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="ebde5-125">다음 예제에서는 기존 Enterprise Voice 사용자 SLAGroup1에 대한 SLA 그룹을 만들고 SLAGroup1에 할당된 번호를 SLA 주선 번호로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="ebde5-126">이 명령은 새 SLA 그룹에 대한 최대 동시 호출 수를 3으로 설정하고 통화 중 신호를 듣지 못하게 하는 통화에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="ebde5-127">새 SLA Set-CsSlaConfiguration 만들거나 기존 SLA 그룹을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebde5-128">지정하는 대상은 유효한 기존 사용자 계정 또는 Enterprise Voice  `-Identity` 계정이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="ebde5-129">[Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용하여 그룹에 대리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="ebde5-130">다음 예제에서는 SLA 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="ebde5-131">그룹에 추가된 각 사용자는 유효한 사용자 Enterprise Voice 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="ebde5-132">그룹에 추가할 각 사용자에 대해 cmdlet을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="ebde5-133">사용자는 단일 SLA 그룹에만 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="ebde5-134">SLA 그룹 사용 중 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ebde5-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="ebde5-135">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹 사용 중 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="ebde5-136">다음 예에서는 전화 번호 202-555-1234로 전달할 최대 동시 통화 수를 초과하는 통화를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="ebde5-137">대상은 전화 번호 대신 조직의 사용자일 수 있습니다. 이 경우 전달된 통화를 받을 사람의 구문은 대리인을 지정할 때와  `sip:<NameofDelegate@domain>` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="ebde5-138">그 외 가능한 매개 변수는  `BusyOption` `Voicemail` 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="ebde5-139">SLA 그룹 부재 중 통화 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ebde5-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="ebde5-140">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹 부재 중 통화 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="ebde5-141">다음은 부재 중 전화가 1이라는 사용자에게 전달하도록 지정하는  `sla_forward_number` 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="ebde5-142">매개 변수에 사용할 수 있는 옵션은  `-MissedCallOption` `Forward` 다음과  `BusySignal`  `Disconnect` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="ebde5-143">이 매개 변수를 선택하는 경우 사용자 또는 전화 번호도 대상으로  `Forward`  `-MissedCallForwardTarget` 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="ebde5-144">그룹에서 대리인 제거</span><span class="sxs-lookup"><span data-stu-id="ebde5-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="ebde5-145">[Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용하여 그룹에서 대리인을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="ebde5-146">예제:</span><span class="sxs-lookup"><span data-stu-id="ebde5-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="ebde5-147">SLA 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="ebde5-147">Delete an SLA group</span></span>

- <span data-ttu-id="ebde5-148">[Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용하여 SLA 그룹을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="ebde5-149">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebde5-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


