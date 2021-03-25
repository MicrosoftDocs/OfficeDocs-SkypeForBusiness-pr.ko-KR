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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120870"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정

이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .
  
- 하이브리드 연결을 설정하는 방법에 대한 자세한 내용은 [비즈니스용 Skype](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 서버와 비즈니스용 Skype Online 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
    
- 배포 계획에 대한 자세한 내용은 [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server을 참조하세요.](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- 라이선싱 및 요금제 등 전화 시스템에 대한 자세한 내용은 [PSTN Calling plans for Skype for Business을 참조하세요.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>사용자를 전화 시스템으로 이동(프레미스 PSTN 연결로)

사용자를 비즈니스용 Skype Online으로 이동하기 전에 사용자를 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스로 사용하도록 설정한 다음 온라인으로 이동하는 것이 좋습니다. 자세한 내용은 [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 및 Enable the users for Enterprise Voice for Enterprise Voice on-premises (performed while the users are home-premises) 섹션을 참조하십시오. [](enable-the-users-for-enterprise-voice-on-premises.md) 
  
모든 사용자는 Active Directory의 모든 사용자를 프레미스에서 만들어야 합니다. 지원되는 버전의 Azure AD 커넥터를 사용하여 Microsoft 365 또는 Office 365에 동기화해야 합니다. Azure AD에서 직접 만든 Office 365에서 전화 시스템을 사용하도록 설정할 수는 없습니다. Azure AD에서 만든 사용자에 대해 사내 PSTN 연결을 사용하여 전화 시스템을 사용하도록 설정하려면, 해당 사용자에 대해 새 계정을 만들고, 해당 계정을 사내에서 구성한 다음, 지원되는 버전의 Azure AD 커넥터 도구를 사용하여 계정을 동기화해야 합니다. 
  
사용자가 온라인 PSTN 연결을 통해 전화 시스템을 사용하도록 설정한 다음 비즈니스용 Skype Online으로 이동하려면 다음 단계가 필요합니다.
  
- [사용자가 Enterprise Voice(사용자가](enable-the-users-for-enterprise-voice-on-premises.md) 홈으로 있는 동안 수행)에 대해 사용자를 사용하도록 설정할 수 있습니다.
    
- 음성 라우팅 정책을 [할당합니다(사용자가](assign-a-voice-routing-policy.md) 사내에 있는 동안 수행).
    
- [사용자를 클라우드에 동기화하고 라이선스를](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 할당합니다(Office 365를 사용하여 수행).
    
- [비즈니스용 Skype Online으로](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) 사내 사용자를 이동(Windows PowerShell Office 365 관리자 자격 증명을 사용하여 수행)
    
- [사용자가 온라인 및 Enterprise Voice 시스템](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 음성메일(원격 PowerShell을 사용하여 수행)을 사용할 수 있도록 합니다.
