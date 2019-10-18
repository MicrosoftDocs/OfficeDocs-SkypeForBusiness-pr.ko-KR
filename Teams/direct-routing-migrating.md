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
description: 비즈니스용 Skype Online 및 팀 구성 관점에서 직접 라우팅하기 위해 마이그레이션하는 데 필요한 사항에 대해 알아보세요.
ms.openlocfilehash: 9fb644c938c61fd9dd1c78362ad90bfe855e97ec
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572182"
---
# <a name="migrate-to-direct-routing"></a>직접 라우팅으로 마이그레이션

이 문서에서는 비즈니스용 Skype Online 및 Microsoft 팀 구성 관점에서 직접 라우팅하기 위해 마이그레이션하는 데 필요한 사항에 대해 설명 합니다. 이 문서에서는 다음에서 마이그레이션하는 방법에 대해 설명 합니다. 
 
- 전화 요금제가 포함 되어 있는 Office 365 전화 시스템 (팀 및 비즈니스용 Skype Online) 
- 비즈니스용 skype Online에서 온-프레미스 PSTN 연결을 사용 하는 Office 365 전화 시스템 (비즈니스용 Skype Online)  
- 클라우드 커넥터 버전 (비즈니스용 Skype Online)을 사용 하 여 온-프레미스 PSTN 연결을 사용 하는 Office 365 전화 시스템

  
이러한 구성 단계 외에도 SBC (세션 경계 컨트롤러)에서 호출을 새 경로로 라우팅하는 데 구성이 필요 합니다. 이 문서에서는 다루지 않습니다. 자세한 내용은 SBC 공급 업체 문서를 참조 하세요.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>다양 한 PSTN 연결 옵션의 사용자 프로비저닝 종료 상태 

다음 표에는 Office 365 전화 시스템을 사용 하 여 선택한 PSTN 연결 옵션에 대해 프로 비전 된 사용자의 종료 상태가 나와 있습니다. 음성과 관련 된 특성만 표시 됩니다.

|사용자 개체 특성 |통화 요금제가 포함 되어 있는 전화 시스템|비즈니스용 Skype 서버를 통해 온-프레미스 PSTN 연결을 사용 하는 전화 시스템|클라우드 커넥터를 통해 온-프레미스 PSTN 연결을 사용 하는 전화 시스템|직접 라우팅을 통한 온-프레미스 PSTN 연결을 사용 하는 전화 시스템|
|---|---|---|---|---|
|클라이언트측|비즈니스용 Skype 또는 팀 |비즈니스용 Skype |비즈니스용 Skype |성과|
|라이센스|Skype Business Online</br>계획 2</br></br>MCOProfessional 또는 MCOPROFESSIONAL)</br></br></br>휴대폰 시스템 (MCOEV)</br></br></br>통화 요금제</br>성과|Skype Business Online 계획 2 (MCOProfessional 또는 MCOPROFESSIONAL)</br></br></br>휴대폰 시스템 (MCOEV)|Skype Business Online 계획 2 (MCOProfessional 또는 MCOPROFESSIONAL)</br></br></br>휴대폰 시스템 (MCOEV)|Skype Business Online 요금제 2 (MCOProfessional 또는 MCOPROFESSIONAL</br></br></br>휴대폰 시스템 (MCOEV)</br></br>성과|
OnPremLineURI |해당 없음|전화 번호는 온-프레미스 광고와 동기화 되어야 합니다. |전화 번호는 온-프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.|전화 번호는 온-프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다. 그러나 조직에 비즈니스용 Skype가 있는 경우에는 온-프레미스 Active Directory에서 번호를 동기화 해야 합니다.|
|LineURI|PSTN 통화 전화 번호|OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.|OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.|OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.|
|EnterpriseVoiceEnabled|False|False|False|False|
|HostedVoiceMail |False|False|False|False|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|값이 있음|값이 있음|값이 있음|해당 없음|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|값이 있음|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|False|해당 없음|해당 없음|False|
|TeamsCallingPolicy</br>AllowGroupCalling|False|해당 없음|해당 없음|False|
||||||

<sup>1</sup> TeamsUpgradePolicy의 오른쪽 모드 선택 시나리오에 따라 다릅니다. [비즈니스용 Skype와 함께 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)에서 서로 다른 모드의 음성 환경에 대해 알아보세요.

이 작업의 일환으로 Microsoft는 최근에 "Microsoft 팀 관리 센터" (최신 포털이 라고도 함)를 업데이트 하 여 공존 모드에 따라 새로운 관리 모델을 반영 합니다. 최신 포털에서 이제 TeamsUpgradePolicy를 구성 하면 TeamsInteropPolicy 일관성 있는 값으로 설정 되므로 TeamsInteropPolicy는 더 이상 사용자 인터페이스에 표시 되지 않습니다. 그러나 PowerShell을 사용 하는 관리자는 적절 한 라우팅이 가능 하도록 TeamsUpgradePolicy 및 TeamsInteropPolicy를 함께 함께 설정 해야 합니다. TeamsUpgradePolicy에 대 한 전환이 완료 된 후에는 TeamsInteropPolicy도 설정 하는 데 더 이상 필요 하지 않습니다.

자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)을 참조 하세요.

## <a name="migrating-from-calling-plans"></a>통화 요금제에서 마이그레이션

통화 계획에서 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- [통화 요금제 설정](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 사용자](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
다음과 같이 이전에 구성한 라이선스 계획 정보를 제거 하는 것이 좋습니다.
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365 전화 시스템 마이그레이션

비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- [계획](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [구축](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

다음과 같이 이전에 구성한 음성 라우팅 정보를 제거 하는 것이 좋습니다.

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>클라우드 커넥터 에디션을 통해 온-프레미스 PSTN 연결을 사용 하 여 Office 365 전화 시스템에서 마이그레이션 

클라우드 커넥터를 통해 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- [계획](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [구축](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [사용자 구성](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

다음과 같이 이전에 구성한 음성 라우팅 정보를 제거 하는 것이 좋습니다.
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[새로운 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[제거-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

