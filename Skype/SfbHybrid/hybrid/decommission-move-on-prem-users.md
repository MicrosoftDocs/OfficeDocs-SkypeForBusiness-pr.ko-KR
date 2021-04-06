---
title: 클라우드로 사용자 및 끝점 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype의 사내 환경을 해제하기 전에 사용자 및 끝점을 이동하세요.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593911"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>사내 환경을 해제하기 전에 필요한 사용자 및 끝점 이동

이 문서에서는 필요한 사용자 및 응용 프로그램 끝점을 Microsoft 클라우드로 이동한 후, 비즈니스용 Skype 환경을 해제하는 방법을 설명하고 있습니다. 이 단계는 다음 단계 중 1단계로, 프레미스 환경을 해제합니다.

- **1단계. 필요한 모든 사용자 및 응용 프로그램 끝점을 모든 프레미스에서 온라인으로 이동합니다.** (이 문서)

- 2단계. [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- 3단계. [비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>필요한 모든 사용자를 사내에서 클라우드로 이동

마이그레이션을 완료한 후에도 계속 사용할 모든 사용자는 먼저 사내에서 클라우드로 이동해야 합니다. 사용자는 사내 관리 도구를 사용하여 사용자를 이동합니다. 자세한 내용은 [Move users between on-premises and cloud을 참조합니다.](move-users-between-on-premises-and-cloud.md)

비즈니스용 Skype 서버 계정이 있는 사용자가 Teams를 사용할 수 있는 것은 가능하기는 하지만 이러한 사용자는 Teams의 전체 기능을 사용할 수 없습니다. 이러한 사용자는 비즈니스용 Skype를 여전히 사용하는 다른 사용자(온라인 또는 사내에 관계 없이)와 상호 연결하거나 페더러에 연결할 수 없습니다. 이러한 사용자는 Teams 클라이언트에서 PSTN 통화를 받을 수 없습니다. 따라서 이러한 사용자를 온라인으로 이동해야 합니다. 또한 이 단계를 통해 비즈니스용 Skype 서버에서 만든 연락처 또는 모임이 Teams로 마이그레이션됩니다.

사내 배포에 남은 사용자가 있는 경우 비즈니스용 Skype 서버 PowerShell 창에서 다음 cmdlet을 실행합니다.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

사용자가 반환되는 경우 출력을 검토하여 계정을 클라우드로 이동해야 하는지 여부를 확인한 다음 해당 사용자에 대해 여기에 있는 단계를 [따릅니다.](move-users-between-on-premises-and-cloud.md) 더 이상 필요하지 않습니다. 사용자 계정의 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 이 Disable-CsUser 실행하면 필터 조건을 충족하는 모든 사용자의 모든 비즈니스용 Skype 특성이 제거됩니다. 계속하기 전에 이러한 계정이 더 이상 필요하지 않습니다.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Microsoft 365로의 사내 하이브리드 응용 프로그램 끝점 이동

1. 다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 프레미스 하이브리드 응용 프로그램 끝점 설정을 검색하고 내보낼 수 있습니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Microsoft 365에서 새 리소스 계정을 만들고 라이선스를 부여하여 기존 사내 하이브리드 응용 프로그램 끝점을 대체합니다. [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts)

3. 새 리소스 계정을 기존 하이브리드 응용 프로그램 끝점과 연결합니다.

4. 다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 다음의 사내 하이브리드 응용 프로그램 끝점에 정의된 전화 번호를 제거합니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 이러한 계정의 전화 번호는 사내가 아니라 Microsoft 365에서 관리되는 것일 수 있기 때문에 비즈니스용 Skype Online PowerShell에서 다음 명령을 실행합니다.

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. 2단계에서 만든 새 리소스 계정에 전화 번호를 할당합니다. 리소스 계정에 전화 번호를 할당하는 방법에 대한 자세한 내용은 서비스 번호 할당 문서를 [참조하십시오.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)

7. 다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 사내 끝점을 삭제합니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
이제 하이브리드 구성을 [사용하지 않도록 설정할 준비가 완료되었습니다.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>참고 항목

- [비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

- [하이브리드 구성을 사용하지 않도록 설정](cloud-consolidation-disabling-hybrid.md)

- [비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)




