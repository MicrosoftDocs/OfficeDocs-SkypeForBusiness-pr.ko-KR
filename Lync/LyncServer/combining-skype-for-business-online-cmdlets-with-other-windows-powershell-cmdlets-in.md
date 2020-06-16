---
title: 비즈니스용 Skype Online cmdlet을 다른 Windows PowerShell cmdlet과 결합
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4f08370e5aeab6688fdbf2ce13a3e5ccb11a37
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="13424-102">비즈니스용 Skype Online cmdlet을 다른 Windows PowerShell cmdlet과 결합</span><span class="sxs-lookup"><span data-stu-id="13424-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13424-103">_**마지막으로 수정 된 항목:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="13424-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="13424-104">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결할 때 약 40 비즈니스용 Skype 온라인 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="13424-105">그러나 비즈니스용 Skype Online을 관리할 때 이러한 40 cmdlet만 사용 하는 것으로 제한 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="13424-106">비즈니스용 Skype 온라인 cmdlet 외에, 컴퓨터에 설치 된 다른 Windows PowerShell cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="13424-107">Windows PowerShell 3.0을 설치 하면 수백 개의 핵심 Windows PowerShell cmdlet도 설치 됩니다. 이 명령은 비즈니스용 Skype 온라인 cmdlet 및 컴퓨터에서 사용할 수 있는 다른 모든 cmdlet을 혼합 하 고 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="13424-108">Windows PowerShell 3.0의 전체 과정은이 문서의 범위를 벗어나지만 cmdlet을 혼합 하 여 일치 시킬 수 있는 이유를 보여 주는 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="13424-109">첫째, 비즈니스용 Skype Online cmdlet에는 인쇄 명령이 포함 되지 않으며, 이러한 명령을 Windows PowerShell 콘솔에서 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="13424-110">그렇다면 cmdlet에서 검색 된 정보를 출력 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="13424-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="13424-111">한 가지 방법은 정보를 검색 한 다음이 정보를 **출력** 하는 데 사용 되는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="13424-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="13424-112">추가 매개 변수가 포함 되지 않으므로 **출력을 사용** 하는 모든 정보가 기본 프린터로 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13424-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="13424-113">마찬가지로 비즈니스용 Skype Online cmdlet에는 데이터를 파일에 저장할 수 있는 매개 변수가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="13424-114">그러나이 명령은 다음 명령을 사용 **하 여 반환** 되는 정보를 텍스트 파일 C: \\ LogsTenants.txt에 저장 합니다. \\</span><span class="sxs-lookup"><span data-stu-id="13424-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="13424-115">그리고이 명령은 **Select-Object** cmdlet을 사용 하 여 화면에 반환 되 고 표시 되는 데이터를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="13424-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="13424-116">이 예에서 [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet은 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 검색 한 다음, **Select-Object** cmdlet을 사용 하 여 표시 되는 데이터를 사용자의 id 값 및 보관 정책으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="13424-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="13424-117">컴퓨터에서 사용할 수 있는 cmdlet은 수백 개 이므로 비즈니스용 Skype 온라인 cmdlet을 사용 하는 cmdlet을 결정 하는 데 어려움이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="13424-118">비즈니스용 Skype Online cmdlet (및 비즈니스용 Skype Online cmdlet)의 목록을 반환 하려면 먼저 비즈니스용 Skype 온라인 cmdlet이 모두 포함 된 임시 Windows PowerShell 모듈의 이름을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13424-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="13424-119">이렇게 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13424-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="13424-120">화면에 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13424-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="13424-121">ModuleType 스크립트가 있는 모듈은 비즈니스용 Skype Online cmdlet이 포함 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="13424-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="13424-122">이러한 cmdlet의 목록을 반환 하려면 스크립트 모듈 이름을 모듈 이름으로 사용 하 여 **Get-Command** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13424-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="13424-123">스크립트와 같은 ModuleType이 포함 된 모듈이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="13424-124">이 경우 다음 명령을 실행 하 여 **CsTenant** cmdlet이 포함 된 모듈을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13424-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="13424-125">**CsTenant** cmdlet에 대해 반환 되는 모듈은 비즈니스용 Skype Online cmdlet이 모두 포함 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="13424-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="13424-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13424-126">See Also</span></span>


<span data-ttu-id="13424-127">[Windows PowerShell 및 비즈니스용 Skype 온라인 소개](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="13424-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

