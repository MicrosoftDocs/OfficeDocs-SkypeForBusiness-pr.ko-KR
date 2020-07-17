---
title: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet
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
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755044"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="3c111-102">테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3c111-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="3c111-103">공용 공급자 설정을 수정할 때는 항상 테 넌 트 id를 제공 해야 합니다. 이는 단일 테 넌 트가 있는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="3c111-104">예를 들어 다음 명령은 Windows Live를 사용자가 다음과의 통신을 허용 하는 유일한 공용 공급자로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="3c111-105">다행히 이러한 cmdlet 중 하나를 실행할 때마다 테 넌 트 ID (예: bf19b7db-6960-41e5-a139-2aa373474354)를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="3c111-106">대신, [CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet을 실행 하 고, 변수에 테 넌 트 id를 저장 한 다음, 다른 cmdlet 중 하나를 호출할 때이 변수를 사용 하 여 테 넌 트 id를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="3c111-107">예시:</span><span class="sxs-lookup"><span data-stu-id="3c111-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="3c111-108">또는 테 넌 트 ID를 검색 한 후 해당 값을-Csten앤틸리스 cmdlet으로 파이프 하 여 단일 명령으로이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="3c111-109">**CsTenant** cmdlet을 호출 하는 경우에는 테 넌 트 ID를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="3c111-110">이 명령은 테 넌 트에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="3c111-111">다음 cmdlet은 테 넌 트 id를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="3c111-112">그러나이 경우 매개 변수는 선택 사항이 며 cmdlet을 호출할 때 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="3c111-113">대신 현재 연결 되어 있는 비즈니스용 Skype Online 테 넌 트를 기반으로 하는 테 넌 트 id를 Windows PowerShell에서 효율적으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="3c111-114">[CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3c111-115">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3c111-116">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3c111-117">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3c111-118">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3c111-119">[CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="3c111-120">예를 들어 다음 명령을 사용 하 여 **CsTenantFederationConfiguration** cmdlet을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="3c111-121">필수는 아니지만 CsTenantFederationConfiguration를 호출할 때 테 넌 트 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c111-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="3c111-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c111-122">See Also</span></span>


[<span data-ttu-id="3c111-123">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="3c111-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3c111-124">[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3c111-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

