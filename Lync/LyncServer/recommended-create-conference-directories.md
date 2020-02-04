---
title: (권장) 전화 회의 디렉터리 만들기
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d525951dcb77ee365c9c83461f678c26ae53af6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="70496-102">(권장) 전화 회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="70496-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70496-103">_**마지막으로 수정한 주제:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="70496-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="70496-104">회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 모임 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="70496-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="70496-105">전화 회의 ID의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70496-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="70496-106">여러 회의 디렉터리를 만들면 회의 Id가 매우 많은 회의를 만들 때까지 짧은 시간 동안 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70496-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="70496-107">사용자 당 일반적인 회의 수가 있는 조직에서 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70496-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="70496-108">이 지침을 사용 하 여 회의 Id를 일반적으로 작게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70496-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="70496-109">그러나, 풀 전체의 회의 디렉터리 수가 9 개를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 길이가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="70496-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="70496-110">회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="70496-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="70496-111">Lync Server 관리 셸에서 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="70496-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="70496-112">예를 들어 다음은 풀 atl-cs-001.litwareinc.com에서 호스트 되는 id 42를 사용 하 여 컨퍼런스 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70496-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70496-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70496-113">See Also</span></span>


[<span data-ttu-id="70496-114">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="70496-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="70496-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="70496-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

