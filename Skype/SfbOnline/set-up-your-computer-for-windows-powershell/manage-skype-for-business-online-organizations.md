---
title: 온라인 비즈니스용 Skype 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Windows PowerShell 및 Get-CsTenant Get-CsTenantLicensingConfiguration cmdlet을 사용하여 비즈니스용 Skype 테넌트에 대한 정보를 얻을 수 있습니다.
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238788"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="59146-103">온라인 비즈니스용 Skype 관리</span><span class="sxs-lookup"><span data-stu-id="59146-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="59146-104">최신 Teams PowerShell 공개 미리 보기 릴리스는 비즈니스용 Skype 온라인 커넥터와 통합되어 단일 모듈을 제공하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) Teams 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59146-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="59146-105">Get-CsTenant 비즈니스용 Skype **Get-CsTenantLicensingConfiguration** cmdlet을 사용하여 온라인 테넌트에 대한 정보를 찾을 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="59146-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="59146-106">온라인 비즈니스용 Skype 관리</span><span class="sxs-lookup"><span data-stu-id="59146-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="59146-107">온라인 테넌트에 대한 정보를 비즈니스용 Skype 추가 매개 변수 없이 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="59146-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="59146-108">테넌트 이름 및 ID만 반환하는 경우 이 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59146-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="59146-109">[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 및 [Set-CsTenantFederationConfiguration과](/powershell/module/skype/Set-CsTenantFederationConfiguration)같은 cmdlet을 실행하는 경우 _TenantID_ 매개 변수의 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="59146-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="59146-110">지정된 테넌트에 대한 라이선스 정보를 비즈니스용 Skype 온라인 관리 센터에서 사용할 수 있는지 여부를 확인하려면 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="59146-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="59146-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="59146-111">Related topics</span></span>
[<span data-ttu-id="59146-112">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59146-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
