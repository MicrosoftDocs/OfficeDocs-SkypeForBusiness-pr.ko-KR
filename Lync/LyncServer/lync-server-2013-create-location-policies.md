---
title: 'Lync Server 2013: 위치 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7b815f533661fb553c7b9217f23b70f0027c559
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="53f59-102">Lync Server 2013의 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="53f59-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53f59-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="53f59-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="53f59-104">Lync Server는 클라이언트 등록 중에 E9-1-1에 대해 Lync 클라이언트를 사용 하도록 설정 하기 위해 위치 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="53f59-105">위치 정책에는 E9-1-1이 구현 되는 방식을 정의 하는 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="53f59-106">전역 위치 정책을 편집 하 고 태그가 지정 된 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-106">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="53f59-107">클라이언트가 연결 된 위치 정책을 사용 하는 서브넷 내에 없거나 클라이언트에 위치 정책이 직접 할당 되지 않은 경우에는 글로벌 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-107">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="53f59-108">태그가 지정 된 정책은 서브넷 또는 사용자에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-108">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="53f59-109">위치 정책을 만들려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 이거나이에 해당 하는 관리자 권한 및 사용 권한이 있는 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="53f59-110">위치 정책에 대 한 자세한 내용은 [Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53f59-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="53f59-111">이 절차의 cmdlet은 다음 값을 사용 하 여 정의 된 위치 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53f59-112">요소</span><span class="sxs-lookup"><span data-stu-id="53f59-112">Element</span></span></th>
<th><span data-ttu-id="53f59-113">값</span><span class="sxs-lookup"><span data-stu-id="53f59-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53f59-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="53f59-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="53f59-115"><strong>적용</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f59-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="53f59-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="53f59-117"><strong>고지 사항</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f59-118">Microsoft.rtc.management.writableconfig.policy.location.enhancedemergencyservicedisclaimer 유형의</span><span class="sxs-lookup"><span data-stu-id="53f59-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="53f59-119">회사 정책에 따라 위치를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-119">Your company policy requires you to set a location.</span></span> <span data-ttu-id="53f59-120">위치를 설정 하지 않으면 응급 서비스에서 해당 사용자를 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-120">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="53f59-121">위치를 설정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53f59-121">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f59-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="53f59-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="53f59-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f59-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="53f59-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="53f59-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f59-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="53f59-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="53f59-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f59-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="53f59-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="53f59-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f59-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="53f59-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="53f59-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f59-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="53f59-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="53f59-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f59-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="53f59-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="53f59-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f59-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="53f59-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="53f59-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="53f59-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53f59-138">위치 정책을 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53f59-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="53f59-139">새-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="53f59-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="53f59-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="53f59-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="53f59-141">설정-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="53f59-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="53f59-142">제거-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="53f59-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="53f59-143">부여-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="53f59-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="53f59-144">위치 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="53f59-144">To create location policies</span></span>

1.  <span data-ttu-id="53f59-145">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53f59-146"><STRONG>PstnUsage</STRONG> 에 대 한 설정이 PstnUsages의 전역 목록에 없으면 CsLocationPolicy가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="53f59-147">필요한 경우 다음 cmdlet을 실행 하 여 전역 위치 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="53f59-148">다음을 실행 하 여 태그가 지정 된 위치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="53f59-149">다음 cmdlet를 실행 하 여 3 단계에서 만든 태그가 지정 된 위치 정책을 사용자 정책에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f59-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

