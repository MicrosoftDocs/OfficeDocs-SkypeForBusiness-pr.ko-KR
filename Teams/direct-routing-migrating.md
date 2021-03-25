---
title: 직접 라우팅으로 마이그레이션
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 비즈니스용 Skype Online 및 Teams 구성 관점에서 직접 라우팅으로 마이그레이션하는 데 필요한 내용을 알아보습니다.
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122202"
---
# <a name="migrate-to-direct-routing"></a>직접 라우팅으로 마이그레이션

이 문서에서는 비즈니스용 Skype Online 및 Microsoft Teams 구성 관점에서 직접 라우팅으로 마이그레이션하는 데 필요한 것을 설명합니다. 이 문서에서는 다음에서 마이그레이션하는 데 대해 다를 수 있습니다. 
 
- 통화 계획이 있는 전화 시스템(Teams 및 비즈니스용 Skype Online용) 
- 비즈니스용 Skype Server에서 PSTN 연결이 있는 전화 시스템(비즈니스용 Skype Online용)  
- 클라우드 커넥터 버전(비즈니스용 Skype Online용)을 사용하여온-프레미스 PSTN 연결을 사용하는 전화 시스템


이러한 구성 단계 외에도 새 경로로 호출을 라우팅하려면 SBC(세션 테두리 컨트롤러)에 구성이 필요합니다. 이 문서의 범위를 벗어날 수 있습니다. 자세한 내용은 SBC 공급업체 설명서를 참조하세요.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>다양한 PSTN 연결 옵션에 대한 사용자 프로비전 엔드 상태 

다음 표에서는 Phone System을 사용하여 선택한 PSTN 연결 옵션에 대해 프로비전된 사용자의 최종 상태를 보여줍니다. 음성과 관련된 특성만 표시됩니다.

|사용자 개체 특성 |통화 플랜을 사용하는 전화 시스템|비즈니스용 Skype 서버를 통해 PSTN에 연결되는 전화 시스템|Cloud Connector를 통한 PSTN 연결로 전화 시스템|직접 라우팅을 통해 프레미스 PSTN 연결이 있는 전화 시스템|
|---|---|---|---|---|
|클라이언트|비즈니스용 Skype 또는 Teams |비즈니스용 Skype |비즈니스용 Skype |Teams|
|라이선스|Skype Business Online</br>계획 2</br></br>MCOProfessional 또는 MCOSTANDARD)</br></br></br>전화 시스템(MCOEV)</br></br></br>통화 플랜</br>Teams|Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</br></br></br>전화 시스템(MCOEV)|Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</br></br></br>전화 시스템(MCOEV)|Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</br></br></br>전화 시스템(MCOEV)</br></br>Teams|
OnPremLineURI |해당 없음|전화 번호는 프레미스 AD에서 동기화되어야 합니다. |전화 번호는 프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.|전화 번호는 프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다. 그러나 조직에 비즈니스용 Skype가 있는 경우 이 수를 On-프레미스 Active Directory에서 동기화해야 합니다.|
|LineURI|PSTN 통화 전화 번호|OnPremLineURI 매개 변수에서 자동으로 설정|OnPremLineURI 매개 변수에서 자동으로 설정|OnPremLineURI 매개 변수에서 자동으로 설정|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|값이 있습니다.|값이 있습니다.|값이 있습니다.|해당 없음|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|값이 있습니다.|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|해당 없음|해당 없음|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|해당 없음|해당 없음|True|
||||||

<sup>1</sup> TeamsUpgradePolicy의 올바른 모드 선택은 시나리오에 따라 다릅니다. 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침의 다양한 모드에서 음성 환경에 [대해 읽어 주세요.](migration-interop-guidance-for-teams-with-skype.md)

이러한 노력의 일환으로 Microsoft는 최근 공존 모드를 기반으로 하는 새 관리 모델을 반영하기 위해 "Microsoft Teams 관리 센터"(모던 포털라고도도 하는)를 업데이트했습니다. 현대 포털에서 TeamsUpgradePolicy를 구성하면 TeamsInteropPolicy도 자동으로 일관된 값으로 설정되어 TeamsInteropPolicy가 사용자 인터페이스에 더 이상 노출되지 않습니다. 그러나 PowerShell을 사용하는 관리자는 적절한 라우팅을 보장하기 위해 TeamsUpgradePolicy와 TeamsInteropPolicy를 함께 설정해야 합니다. TeamsUpgradePolicy로 전환이 완료되면 TeamsInteropPolicy도 더 이상 설정할 필요가 없습니다.

자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침을 [참조하세요.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="migrating-from-calling-plans"></a>통화 계획에서 마이그레이션

통화 계획에서 마이그레이션하는 데 대한 자세한 내용은 다음을 참조하세요.

- [통화 플랜 설정](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 사용자](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
다음과 같이 이전에 구성된 라이선스 계획 정보를 제거하는 것이 좋습니다.
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서온-프레미스 PSTN 연결로 Office 365 Phone System에서 마이그레이션

비즈니스용 Skype Server의온-프레미스 PSTN 연결을 사용하여 Phone System에서 마이그레이션하는 자세한 내용은 다음을 참조하세요.

- [계획](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [배포](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> 전역 CsVoiceRoutingPolicy가 구성된 경우 이 전역 정책과 연결된 모든 PSTN 사용량을 제거하는 것이 좋습니다. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Cloud Connector Edition을 통해온-프레미스 PSTN 연결로 Office 365 Phone System에서 마이그레이션 

> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일을 사용 중지합니다. 조직이 Teams로 업그레이드된 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법에 대해 자세히 알아보습니다.](direct-routing-landing-page.md)

Cloud Connector를 통해온-프레미스 PSTN 연결을 사용하여 Phone System에서 마이그레이션하는 데 대한 자세한 내용은 다음을 참조하세요.

- [계획](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [배포](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [사용자 구성](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)