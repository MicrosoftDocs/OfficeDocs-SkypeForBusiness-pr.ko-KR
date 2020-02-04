---
title: 다른 Windows PowerShell cmdlet을 사용 하 여 비즈니스용 Skype Online cmdlet 결합
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="826a5-102">다른 Windows PowerShell cmdlet을 사용 하 여 비즈니스용 Skype Online cmdlet 결합</span><span class="sxs-lookup"><span data-stu-id="826a5-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="826a5-103">_**마지막으로 수정한 주제:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="826a5-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="826a5-104">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결 하면 약 40 Skype for Business Online cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="826a5-105">그러나 비즈니스용 Skype Online을 관리 하는 경우에는 이러한 40 cmdlet만 사용 하는 것이 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="826a5-106">비즈니스용 Skype Online cmdlet 외에도 컴퓨터에 설치 된 다른 Windows PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="826a5-107">(Windows PowerShell 3.0을 설치 하는 경우에는 수백 개의 핵심 Windows PowerShell cmdlet도 설치 되어 있습니다.) 이 명령은 비즈니스용 Skype Online cmdlet 및 컴퓨터에서 사용할 수 있는 다른 모든 cmdlet을 혼합 하 여 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="826a5-108">Windows PowerShell 3.0의 전체 과정은이 문서의 범위를 벗어나므로 여기서는 cmdlet을 혼합 하 고 일치 시킬 수 있는 이유를 보여 주는 몇 가지 예를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="826a5-109">무엇 보다도 비즈니스용 Skype Online cmdlet에는 인쇄 명령이 포함 되어 있지 않으며, Windows PowerShell 콘솔에서는 이러한 명령을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="826a5-110">그렇다면 cmdlet에서 검색 된 정보를 출력 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="826a5-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="826a5-111">한 가지 방법은 정보를 검색 한 후 해당 정보를 **Printer** cmdlet으로 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="826a5-112">추가 매개 변수가 포함 되지 않으므로 **Out 프린터** cmdlet에서 반환 된 모든 정보가 기본 프린터로 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="826a5-113">마찬가지로 비즈니스용 Skype Online cmdlet에는 데이터를 파일에 저장할 수 있는 매개 변수가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="826a5-114">그러나이 명령은 **Out 파일** cmdlet을 사용 하 여 반환 된 정보를 텍스트 파일 C:\\로그\\에 테 넌 트에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="826a5-115">이 명령은 **Select-Object** cmdlet을 사용 하 여 화면에 반환 및 표시 되는 데이터를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="826a5-116">이 예제에서 [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet은 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 검색 한 다음 **개체 선택** cmdlet을 사용 하 여 표시 된 데이터를 사용자의 id 값 및 해당 보관 정책으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="826a5-117">컴퓨터에서 수백 개의 cmdlet을 사용할 수 있기 때문에 비즈니스용 Skype Online cmdlet을 사용 하 고 있지 않은 cmdlet을 확인 하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="826a5-118">비즈니스용 skype Online cmdlet (그리고 비즈니스용 Skype Online cmdlet에만 해당) 목록을 반환 하려면 먼저 비즈니스용 Skype Online cmdlet이 모두 포함 된 임시 Windows PowerShell 모듈의 이름을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="826a5-119">이렇게 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="826a5-120">다음과 유사한 정보가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="826a5-121">ModuleType 스크립트를 사용 하는 모듈은 비즈니스용 Skype Online cmdlet을 포함 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="826a5-122">이러한 cmdlet 목록을 반환 하려면 스크립트 모듈의 이름을 모듈 이름으로 사용 하 여 **Get 명령** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="826a5-123">스크립트와 동일한 ModuleType이 포함 된 모듈을 여러 개 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="826a5-124">이 경우 다음 명령을 실행 하 여 **CsTenant** cmdlet을 포함 하는 모듈을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="826a5-125">**CsTenant** cmdlet에 대해 반환 되는 모듈은 비즈니스용 Skype Online cmdlet을 모두 포함 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="826a5-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="826a5-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="826a5-126">See Also</span></span>


<span data-ttu-id="826a5-127">[Windows PowerShell 및 Lync Online 소개](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="826a5-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

