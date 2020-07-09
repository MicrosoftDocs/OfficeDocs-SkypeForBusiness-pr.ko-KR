---
title: 비즈니스용 Skype Online 조 직 관리
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
description: Windows PowerShell 및 CsTenant 및 CsTenantLicensingConfiguration cmdlet을 사용 하 여 비즈니스용 Skype Online 테 넌 트에 대 한 정보를 가져옵니다.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085694"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="614d4-103">비즈니스용 Skype Online 조 직 관리</span><span class="sxs-lookup"><span data-stu-id="614d4-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="614d4-104">최신 [팀 powershell 공개 미리 보기 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/) 는 비즈니스용 Skype Online 커넥터와 통합 되어 팀 PowerShell 관리를 위한 단일 모듈을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="614d4-105">**CsTenant** 및 **CsTenantLicensingConfiguration** cmdlet을 사용 하 여 비즈니스용 Skype Online 테 넌 트에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="614d4-106">비즈니스용 Skype Online 테 넌 트 관리</span><span class="sxs-lookup"><span data-stu-id="614d4-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="614d4-107">비즈니스용 Skype Online 테 넌 트에 대 한 정보를 반환 하려면 [CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet에 추가 매개 변수 없이 호출 하세요.</span><span class="sxs-lookup"><span data-stu-id="614d4-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="614d4-108">테 넌 트 이름 및 ID만 반환 하려면이 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="614d4-109">[Set-Csten앤틸리스 Publicprovider](https://go.microsoft.com/fwlink/p/?linkid=849602) 및 [set CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx)와 같은 cmdlet을 실행 하는 경우 _TenantID_ 매개 변수의 값이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="614d4-110">비즈니스용 Skype Online 관리 센터에서 지정 된 테 넌 트에 대 한 라이선스 정보를 사용할 수 있는지 여부에 대 한 정보를 찾으려면 [CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="614d4-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="614d4-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="614d4-111">Related topics</span></span>
[<span data-ttu-id="614d4-112">Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="614d4-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
