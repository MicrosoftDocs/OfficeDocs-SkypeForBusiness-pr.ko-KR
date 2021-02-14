---
title: 회의 디렉터리 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 풀을 해제하기 전에 레거시 풀의 각 회의 디렉터리에 대해 다음 절차를 수행해야 합니다.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752500"
---
# <a name="move-conference-directories"></a><span data-ttu-id="eb702-103">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="eb702-103">Move Conference Directories</span></span>

<span data-ttu-id="eb702-104">풀을 해제하기 전에 레거시 풀의 각 회의 디렉터리에 대해 다음 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="eb702-105">전화 회의 디렉터리를 비즈니스용 Skype 서버 2019로 이동</span><span class="sxs-lookup"><span data-stu-id="eb702-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="eb702-106">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="eb702-107">조직에서 회의의 ID를 얻습니다. 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="eb702-108">위의 명령은 조직의 모든 회의를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="eb702-109">따라서 해제되는 풀로 결과를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="eb702-110">예를 들어 FQDN(FQDN)을 사용하여 풀을 해제하는 pool01.contoso.net 다음 명령을 사용하여 반환되는 데이터를 해당 풀의 회의 디렉터로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="eb702-111">이 명령은 ServiceID 속성에 FQDN이 포함된 전화 회의 pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="eb702-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="eb702-112">회의 디렉터리를 이동하기 위해 풀의 각 회의 디렉터리에 대해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="eb702-113">예를 들어 전화 회의 디렉터리 3을 이동하기 위해 다음 명령을 사용하여 비즈니스용 Skype 서버 2019 풀을 TargetPool로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="eb702-114">풀의 모든 회의 센터를 이동하려는 경우 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="eb702-115">[레거시](https://go.microsoft.com/fwlink/p/?linkId=246227) 풀 해제에 대한 포괄적인 단계별 지침을 위해 Microsoft 레거시 제거 및 서버 역할 제거를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="eb702-116">회의를 이동하는 경우 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="eb702-117">이 오류는 일반적으로 비즈니스용 Skype 서버 관리 셸에서 작업을 완료하기 위해 업데이트된 Active Directory 권한 집합이 필요한 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eb702-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="eb702-118">문제를 해결하려면 관리 셸의 현재 인스턴스를 닫은 다음 새 셸 인스턴스를 열고 명령을 다시 실행하여 회의 디렉터리를 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb702-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

