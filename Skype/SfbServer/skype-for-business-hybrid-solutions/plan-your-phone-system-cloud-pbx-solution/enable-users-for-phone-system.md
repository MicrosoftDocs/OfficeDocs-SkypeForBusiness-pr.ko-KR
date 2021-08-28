---
title: 사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 이 항목에서는 사용자가 전화 시스템 PSTN 연결을 사용할 수 있도록 설정하는 방법에 대해 설명합니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .
ms.openlocfilehash: 22e0db6b9cd99c7909bcc6477db28546feef21d3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625040"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정

이 항목에서는 사용자가 전화 시스템 PSTN 연결을 사용할 수 있도록 설정하는 방법에 대해 설명합니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .
  
- 하이브리드 연결을 설정하는 방법에 대한 자세한 내용은 Plan [hybrid connectivity between 비즈니스용 Skype 서버 and 비즈니스용 Skype Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 및 비즈니스용 Skype 서버 and 비즈니스용 Skype [Online를 참조하세요.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
    
- 배포 계획에 대한 자세한 내용은 [Plan 전화 시스템 with on-premises PSTN connectivity in 비즈니스용 Skype 서버.](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- 라이선스 및 요금제 등 전화 시스템 대한 자세한 내용은 [PSTN Calling plans for 비즈니스용 Skype.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> 비즈니스용 Skype 온라인은 2021년 7월 31에 사용 중지된 후 더 이상 서비스에 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 Cloud Connector Edition과 비즈니스용 Skype Online을 통한 PSTN 연결은 더 이상 지원되지 않습니다.  직접 라우팅 을 사용하여 프레미스 전화 통신 Teams [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>사용자를 전화 시스템 PSTN 연결을 통해 사용자 이동

사용자를 비즈니스용 Skype Online으로 이동하기 전에 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스에서 사용자를 사용하도록 설정한 다음 온라인으로 이동하는 것이 좋습니다. 자세한 내용은 [Plan hybrid connectivity between 비즈니스용 Skype 서버 and 비즈니스용 Skype Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 및 Enable the users for Enterprise Voice for Enterprise Voice [on-premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are home-premises) 섹션을 참조하십시오. 
  
지원되는 버전의 Azure AD 커넥터를 사용하여 모든 사용자를 Active Directory Microsoft 365 Office 365 동기화해야 합니다. Azure AD에서 직접 만든 전화 시스템 사용자가 Office 365 수 없습니다. Azure AD에서 만든 사용자에 대해 전화 시스템 PSTN 연결을 사용하여 전화 시스템 사용하도록 설정하려면 해당 사용자에 대해 새 계정을 만들고, 계정을 사내에서 구성한 다음 지원되는 버전의 Azure AD 커넥터 도구를 사용하여 계정을 동기화해야 합니다. 
  
사용자가 전화 시스템 PSTN 연결을 사용하도록 설정한 다음 비즈니스용 Skype Online으로 이동하려면 다음 단계가 필요합니다.
  
- [사용자가 Enterprise Voice(사용자가](enable-the-users-for-enterprise-voice-on-premises.md) 홈으로 있는 동안 수행)에 대해 사용자를 사용하도록 설정할 수 있습니다.
    
- 음성 라우팅 정책을 [할당합니다(사용자가](assign-a-voice-routing-policy.md) 사내에 있는 동안 수행).
    
- [사용자를 클라우드에 동기화하고 라이선스를](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 할당합니다(Office 365.
    
- [비즈니스용 Skype Online으로](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) 이동(Windows PowerShell 관리자 자격 증명을 사용하여 Windows PowerShell Office 365 수행).
    
- [사용자가 온라인 Enterprise Voice](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 음성 전화 시스템(원격 PowerShell을 사용하여 수행)를 사용할 수 있도록 합니다.
