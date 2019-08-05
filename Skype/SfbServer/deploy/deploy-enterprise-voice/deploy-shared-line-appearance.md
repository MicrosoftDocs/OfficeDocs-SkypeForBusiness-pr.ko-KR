---
title: 비즈니스용 Skype 서버 2015에서 공유 선 모양 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 이 항목에서는 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 선 모양)를 배포 하는 방법에 대해 알아봅니다. SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하기 위한 기능입니다.
ms.openlocfilehash: 04efe0a0b3ae9e89576ca2d52ce45861cde68a9d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191937"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="ff1ee-104">비즈니스용 Skype 서버 2015에서 공유 선 모양 배포</span><span class="sxs-lookup"><span data-stu-id="ff1ee-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="ff1ee-105">이 항목에서는 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 선 모양)를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="ff1ee-106">SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하기 위한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="ff1ee-107">이 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 공유 라인 모양에 대 한 계획](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="ff1ee-108">SLA (공유 선 모양)는 비즈니스용 Skype Server의 새로운 기능으로, 11 월 2015 누적 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="ff1ee-109">이 기능을 사용 하도록 설정 하려면 먼저이 누적 업데이트를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="ff1ee-110">공유 선 모양 설치</span><span class="sxs-lookup"><span data-stu-id="ff1ee-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="ff1ee-111">비즈니스용 Skype 서버, 11 월 2015 누적 업데이트가 배포 된 후에 풀의 `SkypeServerUpdateInstaller.exe` 각 프런트 엔드 서버에서 패치를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="ff1ee-112">설치 관리자가 최신 버전의 SLA 응용 프로그램을 배포 하지만, 응용 프로그램은 기본적으로 활성화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="ff1ee-113">이 기능은 아래에 설명 된 단계에 따라 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="ff1ee-114">에서.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-114">a.</span></span> <span data-ttu-id="ff1ee-115">각 풀에 대해 다음 명령을 실행 하 여 SLA를 서버 응용 프로그램으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="ff1ee-116">여기서% FQDN%는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="ff1ee-117">b.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-117">b.</span></span> <span data-ttu-id="ff1ee-118">다음 명령을 실행 하 여 SLA cmdlet에 대 한 RBAC 역할을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```
   Update-CsAdminRole
   ```

    <span data-ttu-id="ff1ee-119">c.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-119">c.</span></span> <span data-ttu-id="ff1ee-120">SLA를 설치 하 고 활성화 한 모든 풀에서 프런트 엔드 서버 (RTCSRV 서비스)를 모두 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="ff1ee-121">SLA 그룹을 만들고 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="ff1ee-122">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="ff1ee-123">CsSlaConfiguration cmdlet은 Enterprise Voice account SLAGroup1을 SLA 엔터티로 표시 하 고 SLAGroup1의 수는 SLA 그룹의 숫자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="ff1ee-124">SLAGroup1에 대 한 모든 통화가 전체 SLA 그룹에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="ff1ee-125">다음 예에서는 기존 Enterprise Voice user에 대 한 SLA 그룹을 만들고, SLAGroup1에 대해 SLAGroup1에 지정 된 번호를 SLA의 중요 한 번호로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="ff1ee-126">이 명령은 새 SLA 그룹에 대 한 최대 동시 통화 수를 3으로 설정 하 고,이를 초과 하 여 통화 중 신호를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="ff1ee-127">Set-CsSlaConfiguration를 사용 하 여 새 SLA 그룹을 만들거나 기존 항목을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff1ee-128">에 대해 `-Identity` 지정 하는 항목은 유효한 기존 엔터프라이즈 음성 사용 사용자 계정 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="ff1ee-129">[Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에 대리인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="ff1ee-130">다음 예에서는 사용자를 SLA 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="ff1ee-131">그룹에 추가 된 각 사용자는 유효한 Enterprise Voice 사용 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="ff1ee-132">그룹에 추가 하려는 각 사용자에 대해 cmdlet을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="ff1ee-133">사용자는 단일 SLA 그룹에만 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="ff1ee-134">SLA 그룹 약속 있음 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ff1ee-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="ff1ee-135">[Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 사용 중 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="ff1ee-136">다음 예에서는 전화 번호 202-555-1234로 착신 전환 될 최대 동시 통화 수를 초과 하는 호출을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="ff1ee-137">대상은 전화 번호 대신 조직의 사용자 일 수 있습니다. 이 경우 착신 전환 된 전화를 받는 사람에 대 한 구문은 대리인을 지정 하는 경우와 동일 합니다 `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="ff1ee-138">다른 매개 변수 `BusyOption` 를 사용할 수 `Voicemail`있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="ff1ee-139">SLA 그룹 부재 중 전화 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ff1ee-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="ff1ee-140">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹 부재 중 전화 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="ff1ee-141">다음 예에서는 부재 중 통화가 명명 `sla_forward_number`된 사용자에 게 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="ff1ee-142">`-MissedCallOption` 매개 `Forward`변수에 `BusySignal`대 한 유효한 옵션은, 또는 `Disconnect`입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="ff1ee-143">선택 `Forward`하는 경우에는 사용자 또는 전화 `-MissedCallForwardTarget` 번호를 대상으로 하는 매개 변수도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="ff1ee-144">그룹에서 대리인 제거</span><span class="sxs-lookup"><span data-stu-id="ff1ee-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="ff1ee-145">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet을 사용 하 여 그룹에서 대리자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="ff1ee-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-146">For example:</span></span>

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="ff1ee-147">SLA 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="ff1ee-147">Delete an SLA group</span></span>

- <span data-ttu-id="ff1ee-148">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="ff1ee-149">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ee-149">For example:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


