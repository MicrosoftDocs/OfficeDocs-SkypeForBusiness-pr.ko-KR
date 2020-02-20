---
title: 는 전화 회의 디렉터리 만들기
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
ms.openlocfilehash: 77688be2f2b1ba547f79e45ca89dd529e24318c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="23f5b-102">는 전화 회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="23f5b-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f5b-103">_**마지막으로 수정 된 항목:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="23f5b-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="23f5b-104">전화 회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 회의 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="23f5b-105">전화 접속 ID의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="23f5b-106">전화 회의 디렉터리를 여러 개 만들면 상당히 많은 수의 전화 회의가 만들어질 때까지 전화 회의 ID가 짧게 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="23f5b-107">전화 회의 ID를 약 6자리로 유지하려면 사용자당 전화 회의 수가 보편적인 조직의 경우 풀의 사용자 999명당 하나의 전화 회의 디렉터리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="23f5b-108">이 지침을 사용하면 대개 전화 회의 ID가 짧게 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="23f5b-109">그러나 풀에서 전화 회의 디렉터리의 수가 9를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 길이를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="23f5b-110">회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="23f5b-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="23f5b-111">Lync Server 관리 셸에서 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="23f5b-112">예를 들어 다음은 atl-cs-001.litwareinc.com 풀에서 호스트 되는 id가 42 인 전화 회의 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23f5b-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23f5b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23f5b-113">See Also</span></span>


[<span data-ttu-id="23f5b-114">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="23f5b-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="23f5b-115">Get-csconferencedirectory</span><span class="sxs-lookup"><span data-stu-id="23f5b-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

