---
title: 'Lync Server 2013: 공유 선 모양 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531415"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="69f4a-102">Lync Server 2013에 공유 선 모양 배포</span><span class="sxs-lookup"><span data-stu-id="69f4a-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f4a-103">_**마지막으로 수정 된 항목:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="69f4a-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="69f4a-104">Lync Server 2013, 누적 업데이트 4 월 2016에는 SLA (Shared Line 모양새)를 배포 하는 방법을 알아보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="69f4a-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="69f4a-105">SLA는 공유 번호 라는 특정 번호에서 여러 통화를 처리 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="69f4a-106">이 기능에 대 한 자세한 내용은 [Plan For Shared Line 모양새 In Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="69f4a-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="69f4a-107">SLA (공유 선 모양)는 Lync Server 2013, 누적 업데이트 4 월 2016의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="69f4a-108">이 기능을 사용 하도록 설정 하려면 먼저이 누적 업데이트를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="69f4a-109">공유 선 모양 설치</span><span class="sxs-lookup"><span data-stu-id="69f4a-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="69f4a-110">Lync Server 2013, 4 2016 월 누적 업데이트를 배포 하 고 나면 SLA 응용 프로그램은 기본적으로 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="69f4a-111">응용 프로그램을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="69f4a-112">각 풀에 대해 다음 명령을 실행 하 여 SLA를 서버 응용 프로그램으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="69f4a-113">여기서% FQDN%는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="69f4a-114">다음 명령을 실행 하 여 SLA cmdlet에 대 한 RBAC 역할을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="69f4a-115">SLA가 설치 되어 있고 사용 하도록 설정 된 모든 풀에서 모든 프런트 엔드 서버 (RTCSRV 서비스)를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="69f4a-116">SLA 그룹을 만들고 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="69f4a-117">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용 하 여 SLA 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="69f4a-118">Set-CsSlaConfiguration cmdlet은 Enterprise Voice 계정 SLAGroup1를 SLA 엔터티로 표시 하 고 SLAGroup1의 수가 SLA 그룹의 숫자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="69f4a-119">SLAGroup1에 대 한 모든 호출이 전체 SLA 그룹에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="69f4a-120">다음은 기존 Enterprise Voice 사용자에 대 한 SLA 그룹을 만들고 SLAGroup1에 SLAGroup1에 대해 지정 된 번호를 SLA의 중요 번호로 사용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="69f4a-121">이 명령은 새 SLA 그룹에 대 한 최대 동시 통화 수를 3으로 설정 하 고,이를 초과 하 여 통화 중 신호를 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="69f4a-122">Set-CsSlaConfiguration을 사용 하 여 새 SLA 그룹을 만들거나 기존 항목을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69f4a-123">지정 하는 항목은 <CODE>-Identity</CODE> 유효한 기존 Enterprise Voice 사용 가능 사용자 계정 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="69f4a-124">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet을 사용 하 여 그룹에 대리인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="69f4a-125">다음은 SLA 그룹에 사용자를 추가 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="69f4a-126">그룹에 추가 되는 각 사용자는 유효한 Enterprise Voice 사용이 가능한 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="69f4a-127">그룹에 추가 하려는 각 사용자에 대해 cmdlet을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="69f4a-128">사용자는 단일 SLA 그룹에만 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="69f4a-129">SLA 그룹 약속 있음 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="69f4a-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="69f4a-130">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용 하 여 SLA 그룹 사용 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="69f4a-131">다음 예에서는 전화 번호 202-555-1234으로 전달 되는 최대 동시 통화 수를 초과 하는 통화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="69f4a-132">대상은 전화 번호 대신 조직의 사용자 일 수 있습니다. 이 경우 착신 전환 된 전화를 받는 사람에 대 한 구문은 대리인을 지정할 때와 같습니다 `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="69f4a-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="69f4a-133">그 밖의 가능한 매개 변수는 `BusyOption` `Voicemail` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="69f4a-134">SLA 그룹 부재 중 전화 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="69f4a-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="69f4a-135">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet을 사용 하 여 SLA 그룹 부재 중 전화 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="69f4a-136">다음 예에서는 부재 중 전화가 라는 사용자에 게 착신 전환 되도록 지정 합니다 `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="69f4a-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="69f4a-137">`-MissedCallOption`매개 변수에 사용할 수 있는 옵션은 `Forward` , `BusySignal` 또는 `Disconnect` 입니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="69f4a-138">을 선택 하는 경우에는 `Forward` `-MissedCallForwardTarget` 다음과 같이 사용자 또는 전화 번호를 대상으로 매개 변수도 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="69f4a-139">그룹에서 대리인 제거</span><span class="sxs-lookup"><span data-stu-id="69f4a-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="69f4a-140">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet을 사용 하 여 그룹에서 대리인을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="69f4a-141">예제:</span><span class="sxs-lookup"><span data-stu-id="69f4a-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="69f4a-142">SLA 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="69f4a-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="69f4a-143">[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet을 사용 하 여 SLA 그룹을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="69f4a-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69f4a-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

