---
title: 'Lync Server 2013: PSTN 전화 통화 라우팅 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abdb6796139ddc4be2b8ea24aa9bfeb19f745373
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="b64a3-102">Lync Server 2013에서 PSTN 전화 통화 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="b64a3-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b64a3-103">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b64a3-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b64a3-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="b64a3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b64a3-105">매일</span><span class="sxs-lookup"><span data-stu-id="b64a3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b64a3-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="b64a3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b64a3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b64a3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b64a3-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="b64a3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b64a3-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b64a3-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csintertrunkrouting</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="b64a3-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b64a3-112">설명</span><span class="sxs-lookup"><span data-stu-id="b64a3-112">Description</span></span>

<span data-ttu-id="b64a3-113">**Test-csintertrunkrouting** cmdlet은 통화를 다른 SIP로 라우팅할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="b64a3-114">이 작업을 수행 하기 위해 cmdlet에는 전화 번호와 트렁크 구성이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="b64a3-115">그런 다음 **test-csintertrunkrouting** 는 지정 된 번호에 대해 일치 하는 경로 및 일치 하는 PSTN 용도를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="b64a3-116">트렁크에 지정 된 전화 번호와 일치 하는 번호 패턴이 있고 트렁크에서 PSTN 사용을 하나 이상 공유 하는 경우에만 트렁크 간에 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b64a3-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="b64a3-117">Running the test</span></span>

<span data-ttu-id="b64a3-118">아래에 나와 있는 명령은 사용자가 Redmond 사이트의 트렁크 구성 설정을 사용 하 여 전화 번호 1-206-555-1219에 전화를 걸 수 있도록 하는 일치 경로 및 일치 하는 전화 사용을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b64a3-119">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="b64a3-119">Determining success or failure</span></span>

<span data-ttu-id="b64a3-120">통화 간 통신을 다른 SIP로 라우팅할 수 있으면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="b64a3-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="b64a3-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="b64a3-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="b64a3-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="b64a3-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="b64a3-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="b64a3-124">테스트가 실패 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="b64a3-125">Test-csintertrunkrouting: 매개 변수에서 인수 변환을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="b64a3-126">' Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 유형의 '</span><span class="sxs-lookup"><span data-stu-id="b64a3-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="b64a3-127">잘못 된 TrunkConfigurationsetting (매개 변수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="b64a3-128">를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-128">Specify a</span></span>

<span data-ttu-id="b64a3-129">유효한 설정 (매개 변수)을 선택한 다음 다시 시도 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b64a3-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="b64a3-130">줄: 1 char: 79</span><span class="sxs-lookup"><span data-stu-id="b64a3-130">At line:1 char:79</span></span>

<span data-ttu-id="b64a3-131">\+Test-csintertrunkrouting-TargetNumber "tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="b64a3-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="b64a3-132">\-Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 유형의 $t</span><span class="sxs-lookup"><span data-stu-id="b64a3-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="b64a3-133">\+CategoryInfo: InvalidData: (:) \[Test-csintertrunkrouting\](대만)</span><span class="sxs-lookup"><span data-stu-id="b64a3-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="b64a3-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="b64a3-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="b64a3-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError (Microsoft. R)</span><span class="sxs-lookup"><span data-stu-id="b64a3-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="b64a3-136">tc. TestOcsInterTrunkRoutingCmdlet를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b64a3-137">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="b64a3-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="b64a3-138">다음은 **test-csintertrunkrouting에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="b64a3-139">잘못 된 매개 변수를 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-139">You specified invalid parameters.</span></span> <span data-ttu-id="b64a3-140">트렁크가 제대로 구성 되어 있지 않거나 지정 된 대상 번호가 잘못 되었거나 잘못 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a3-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b64a3-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b64a3-141">See Also</span></span>


[<span data-ttu-id="b64a3-142">Get-cstrunk</span><span class="sxs-lookup"><span data-stu-id="b64a3-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="b64a3-143">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="b64a3-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

