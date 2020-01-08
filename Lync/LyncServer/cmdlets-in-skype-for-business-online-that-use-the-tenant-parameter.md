---
title: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40984504"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="cc15a-102">테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cc15a-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="cc15a-103">공용 공급자 설정을 수정할 때는 항상 테 넌 트 id를 제공 해야 합니다. 단일 테 넌 트가 있는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="cc15a-104">예를 들어이 명령은 사용자가 통신 하도록 허용 된 유일한 공용 공급자로 Windows Live를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="cc15a-105">다행히 이러한 cmdlet 중 하나를 실행할 때마다 테 넌 트 ID (예: bf19b7db-6960-41e5-a139-2aa373474354)를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="cc15a-106">대신 [CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet을 실행 하 고, 변수에 테 넌 트 id를 저장 한 다음 다른 cmdlet 중 하나를 호출할 때 해당 변수를 사용 하 여 테 넌 트 id를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="cc15a-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="cc15a-108">또는 테 넌 트 ID를 검색 하 여 단일 명령으로 수행한 다음 해당 값을 Set-Csten앤틸리스 Publicprovider cmdlet에 파이핑 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="cc15a-109">**CsTenant** cmdlet을 호출할 때 테 넌 트 ID를 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="cc15a-110">이 명령은 테 넌 트에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="cc15a-111">다음 cmdlet은 테 넌 트 id를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="cc15a-112">그러나 이러한 경우 매개 변수는 선택 사항이 며 cmdlet을 호출할 때 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="cc15a-113">대신 Windows PowerShell에서는 현재 연결 된 비즈니스용 Skype Online 테 넌 트에 따라 테 넌 트 id를 효율적으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="cc15a-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cc15a-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cc15a-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cc15a-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cc15a-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cc15a-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="cc15a-120">예를 들어 다음 명령을 사용 하 여 **CsTenantFederationConfiguration** cmdlet을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="cc15a-121">필수는 아니지만 CsTenantFederationConfiguration를 호출할 때 테 넌 트 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc15a-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="cc15a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc15a-122">See Also</span></span>


[<span data-ttu-id="cc15a-123">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="cc15a-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="cc15a-124">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cc15a-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

