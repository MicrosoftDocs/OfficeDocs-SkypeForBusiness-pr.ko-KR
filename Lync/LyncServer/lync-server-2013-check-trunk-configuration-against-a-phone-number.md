---
title: 'Lync Server 2013: 전화 번호를 기준으로 트렁크 구성 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b67831b6dbcd7dae12f9b19dd71f2512a8807189
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="9a61c-102">Lync Server 2013에서 전화 번호를 기준으로 트렁크 구성 확인</span><span class="sxs-lookup"><span data-stu-id="9a61c-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a61c-103">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9a61c-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a61c-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="9a61c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9a61c-105">월간</span><span class="sxs-lookup"><span data-stu-id="9a61c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a61c-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="9a61c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9a61c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a61c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a61c-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="9a61c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9a61c-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9a61c-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Get-cstrunkconfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="9a61c-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9a61c-112">설명</span><span class="sxs-lookup"><span data-stu-id="9a61c-112">Description</span></span>

<span data-ttu-id="9a61c-113">SIP 트렁크 Lync Server 내부 Enterprise Voice network를 다음 중 하나에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="9a61c-114">공중 전화망 (PSTN)</span><span class="sxs-lookup"><span data-stu-id="9a61c-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="9a61c-115">IP-PBX (공용 분기 교환)</span><span class="sxs-lookup"><span data-stu-id="9a61c-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="9a61c-116">SBC (Session Border Controller)입니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="9a61c-117">Get-cstrunkconfiguration cmdlet은 사용자가 전화를 걸 수 있는 전화번호를 E. 164 네트워크로 변환 하 고 지정 된 SIP 트렁크를 통해 라우팅해야 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9a61c-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="9a61c-118">Running the test</span></span>

<span data-ttu-id="9a61c-119">Get-cstrunkconfiguration cmdlet을 실행 하려면 먼저 Get-cstrunkconfiguration cmdlet을 사용 하 여 SIP 트렁크 구성 설정의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스는 Get-cstrunkconfiguration로 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9a61c-120">Get-cstrunkconfiguration를 먼저 실행 하지 않고 Get-cstrunkconfiguration를 실행 하면 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="9a61c-121">예를 들어 다음 명령은 데이터를 반환 하지 않고 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="9a61c-122">SIP 트렁크 구성 설정의 컬렉션이 여러 개 있는 경우 동일한 전화 번호에 대해 각 모음을 테스트 하는 동시에 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9a61c-123">자세한 내용은 Get-cstrunkconfiguration cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a61c-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9a61c-124">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="9a61c-124">Determining success or failure</span></span>

<span data-ttu-id="9a61c-125">Get-cstrunkconfiguration에서 전화 건 번호로 전화를 걸 수 있으면 변환 된 전화 번호 (E. 164 형식)와 해당 전화 번호를 변환 하는 데 사용 되는 규칙이 모두 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="9a61c-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9a61c-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9a61c-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9a61c-127">\---------------- ------------</span></span>

<span data-ttu-id="9a61c-128">\+12065551219 글로벌/Redmond</span><span class="sxs-lookup"><span data-stu-id="9a61c-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="9a61c-129">테스트가 실패 하면 Get-cstrunkconfiguration에서 빈 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="9a61c-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9a61c-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9a61c-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9a61c-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9a61c-132">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="9a61c-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="9a61c-133">Get-cstrunkconfiguration에서 일치 하는 항목을 반환 하지 않으면 테스트 중인 트렁크 구성 설정에 전화 건 번호를 E. 164 형식으로 변환 하는 데 사용할 수 있는 발신 전화 번호 변환 규칙이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="9a61c-134">트렁크 구성 설정 컬렉션에 할당 된 변환 규칙을 검색 하려면 다음과 같은 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="9a61c-135">이는 각 변환 규칙에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="9a61c-136">설명: 국가 코드나 지역 코드가 없는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="9a61c-137">패턴: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="9a61c-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="9a61c-138">이름: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="9a61c-138">Name : NoAreaCode</span></span>

<span data-ttu-id="9a61c-139">이때 패턴 속성의 값 ( [정규식](http://go.microsoft.com/fwlink/?linkid=400464) 문자열)을 확인 하 여 전화 건 번호를 처리 하도록 변환 규칙이 구성 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="9a61c-140">그렇지 않은 경우에는 기존 규칙 (New-csoutboundtranslationrule) 중 하나를 변경 하거나 New-csoutboundtranslationrule cmdlet을 사용 하 여 컬렉션에 새 규칙을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a61c-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a61c-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a61c-141">See Also</span></span>


[<span data-ttu-id="9a61c-142">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="9a61c-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

