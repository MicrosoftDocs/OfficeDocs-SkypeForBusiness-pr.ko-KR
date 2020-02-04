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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="c58fe-102">Lync Server 2013에서 PSTN 전화 통화 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="c58fe-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c58fe-103">_**마지막으로 수정한 주제:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c58fe-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c58fe-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="c58fe-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c58fe-105">Daily</span><span class="sxs-lookup"><span data-stu-id="c58fe-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c58fe-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="c58fe-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c58fe-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c58fe-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c58fe-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="c58fe-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c58fe-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c58fe-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsInterTrunkRouting</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="c58fe-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c58fe-112">설명</span><span class="sxs-lookup"><span data-stu-id="c58fe-112">Description</span></span>

<span data-ttu-id="c58fe-113">**CsInterTrunkRouting** cmdlet은 한 SIP에서 다른 통화로 통화를 라우팅할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="c58fe-114">이를 위해 cmdlet에는 전화 번호와 트렁크 구성이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="c58fe-115">그런 다음 **CsInterTrunkRouting** 는 지정 된 번호에 대해 일치 하는 경로 및 일치 하는 PSTN 용도를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="c58fe-116">Trunks에 지정 된 전화 번호와 일치 하는 숫자 패턴이 있고 trunks에서 하나 이상의 PSTN 사용을 공유 하는 경우에만 trunks 간에 호출을 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c58fe-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c58fe-117">Running the test</span></span>

<span data-ttu-id="c58fe-118">아래 표시 된 명령은 사용자가 Redmond 사이트의 트렁크 구성 설정을 사용 하 여 전화 번호 1-206-555-1219에 통화할 수 있도록 일치 하는 경로 및 일치 하는 전화를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c58fe-119">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="c58fe-119">Determining success or failure</span></span>

<span data-ttu-id="c58fe-120">한 SIP에서 다른 통화로 통화를 라우팅할 수 있는 경우 다음과 유사한 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="c58fe-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="c58fe-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="c58fe-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="c58fe-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="c58fe-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="c58fe-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="c58fe-124">테스트에 실패 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="c58fe-125">테스트-CsInterTrunkRouting: 매개 변수에서 인수 변환을 처리할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c58fe-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="c58fe-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="c58fe-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="c58fe-127">잘못 된 TrunkConfigurationsetting (매개 변수).</span><span class="sxs-lookup"><span data-stu-id="c58fe-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="c58fe-128">를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-128">Specify a</span></span>

<span data-ttu-id="c58fe-129">올바른 설정 (매개 변수)을 선택한 다음 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="c58fe-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="c58fe-130">줄: 1 char: 79</span><span class="sxs-lookup"><span data-stu-id="c58fe-130">At line:1 char:79</span></span>

<span data-ttu-id="c58fe-131">\+테스트-CsInterTrunkRouting-TargetNumber "tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="c58fe-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="c58fe-132">\-TrunkConfiguration $t</span><span class="sxs-lookup"><span data-stu-id="c58fe-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="c58fe-133">\+CategoryInfo: InvalidData: (:) \[CsInterTrunkRouting\](대만)</span><span class="sxs-lookup"><span data-stu-id="c58fe-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="c58fe-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="c58fe-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="c58fe-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="c58fe-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="c58fe-136">tc. 관리. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="c58fe-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c58fe-137">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="c58fe-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="c58fe-138">**테스트 CsInterTrunkRouting** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="c58fe-139">잘못 된 매개 변수를 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-139">You specified invalid parameters.</span></span> <span data-ttu-id="c58fe-140">트렁크가 아직 올바르게 구성 되지 않았거나 지정 된 대상 번호가 올바르지 않거나 올바르지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58fe-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c58fe-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c58fe-141">See Also</span></span>


[<span data-ttu-id="c58fe-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="c58fe-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="c58fe-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="c58fe-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

