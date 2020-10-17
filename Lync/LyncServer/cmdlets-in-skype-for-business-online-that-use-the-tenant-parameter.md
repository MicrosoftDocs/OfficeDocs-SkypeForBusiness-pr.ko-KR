---
title: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet
description: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet입니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546804"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="1b7b5-103">테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="1b7b5-103">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="1b7b5-104">공용 공급자 설정을 수정할 때는 항상 테 넌 트 id를 제공 해야 합니다. 이는 단일 테 넌 트가 있는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-104">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="1b7b5-105">예를 들어 다음 명령은 Windows Live를 사용자가 다음과의 통신을 허용 하는 유일한 공용 공급자로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-105">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="1b7b5-106">다행히 이러한 cmdlet 중 하나를 실행할 때마다 테 넌 트 ID (예: bf19b7db-6960-41e5-a139-2aa373474354)를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-106">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="1b7b5-107">대신, [CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet을 실행 하 고, 변수에 테 넌 트 id를 저장 한 다음, 다른 cmdlet 중 하나를 호출할 때이 변수를 사용 하 여 테 넌 트 id를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-107">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="1b7b5-108">예제:</span><span class="sxs-lookup"><span data-stu-id="1b7b5-108">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="1b7b5-109">또는 테 넌 트 ID를 검색 한 다음 해당 값을 Set-CsTenantPublicProvider cmdlet으로 파이프 하 여 단일 명령으로이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-109">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="1b7b5-110">**CsTenant** cmdlet을 호출 하는 경우에는 테 넌 트 ID를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-110">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="1b7b5-111">이 명령은 테 넌 트에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-111">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="1b7b5-112">다음 cmdlet은 테 넌 트 id를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-112">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="1b7b5-113">그러나이 경우 매개 변수는 선택 사항이 며 cmdlet을 호출할 때 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-113">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="1b7b5-114">대신 현재 연결 되어 있는 비즈니스용 Skype Online 테 넌 트를 기반으로 하는 테 넌 트 id를 Windows PowerShell에서 효율적으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-114">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="1b7b5-115">[CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-115">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1b7b5-116">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-116">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1b7b5-117">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-117">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1b7b5-118">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-118">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1b7b5-119">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-119">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1b7b5-120">[CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-120">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="1b7b5-121">예를 들어 다음 명령을 사용 하 여 **CsTenantFederationConfiguration** cmdlet을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-121">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="1b7b5-122">필수는 아니지만 Get-CsTenantFederationConfiguration를 호출할 때 테 넌 트 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7b5-122">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="1b7b5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b7b5-123">See Also</span></span>


[<span data-ttu-id="1b7b5-124">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="1b7b5-124">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1b7b5-125">[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1b7b5-125">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

