---
title: 클라우드로 하이브리드 응용 프로그램 끝점 이동
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
description: 하이리드 응용 프로그램 끝점을 이동한 후 비즈니스용 Skype 환경을 해제합니다.
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684385"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>사내 환경을 해제하기 전에 하이브리드 응용 프로그램 끝점 이동

이 문서에서는 필요한 하이브리드 응용 프로그램 끝점을 Microsoft 클라우드로 이동한 후, 프레미스 클라우드 환경을 해제하는 비즈니스용 Skype 설명되어 있습니다. 이 단계는 다음 단계 중 3단계로, 프레미스 환경을 해제합니다.

- 1단계. [필요한 모든 사용자를 온라인에서 온라인으로 이동](decommission-move-on-prem-users.md)

- 2단계. [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- **3단계. 하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동** (이 문서)

- 4단계. [배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>필요한 모든 하이브리드 응용 프로그램 끝점 이동

이러한 끝점을 온라인으로 이동하려면 먼저 끝점에서 사용하는 모든 sip 도메인에 대한 Microsoft 365 DNS 레코드를 업데이트해야 합니다. DNS 레코드가온-프레미스를 지점으로 하는 경우 온라인 리소스 계정을 만들 수 없습니다. 자세한 내용은 하이브리드 구성 [사용 안 을 참조하세요.](cloud-consolidation-disabling-hybrid.md)

1. PowerShell 명령을 실행하여 다음 On-premises 하이브리드 응용 프로그램 끝점 설정을 비즈니스용 Skype 서버 내보낼 수 있습니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 기존 Microsoft 365 [](/microsoftteams/manage-resource-accounts) 하이브리드 응용 프로그램 끝점을 대체하기 위해 새 리소스 계정을 만들고 라이선스를 부여합니다.

3. 새 리소스 계정을 기존 하이브리드 응용 프로그램 끝점과 연결합니다.

4. PowerShell 명령에 대해 다음의 On-premises 비즈니스용 Skype 서버 실행하여 사내 하이브리드 응용 프로그램 끝점에 정의된 전화 번호를 제거합니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 이러한 계정의 전화 번호는 모든 계정의 전화 번호가 Microsoft 365 대신 온라인 PowerShell에서 비즈니스용 Skype 실행합니다.

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

6. 2단계에서 만든 새 리소스 계정에 전화 번호를 할당합니다. 리소스 계정에 전화 번호를 할당하는 방법에 대한 자세한 내용은 서비스 번호 할당 문서를 [참조하십시오.](/microsoftteams/manage-resource-accounts#assign-a-service-number)

7. PowerShell 명령에 대해 다음의 사내 비즈니스용 Skype 서버 실행하여 비즈니스용 Skype 서버 삭제합니다.

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
이제 배포 에서 프레미스 배포를 제거할 [비즈니스용 Skype 있습니다.](decommission-remove-on-prem.md)

## <a name="see-also"></a>참고 항목

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

- [필요한 모든 사용자를 온라인에서 온라인으로 이동](decommission-move-on-prem-users.md)

- [하이브리드 구성을 사용하지 않도록 설정](cloud-consolidation-disabling-hybrid.md)

- [온-프레미스 비즈니스용 Skype 배포 제거](decommission-remove-on-prem.md)




