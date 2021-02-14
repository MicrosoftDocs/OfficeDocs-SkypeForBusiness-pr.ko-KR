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
description: 이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359144"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정

이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다.
  
- 하이브리드 연결을 설정하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버와 비즈니스용 [Skype Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- 배포 계획에 대한 자세한 내용은 비즈니스용 Skype 서버의 PSTN 연결을 통해 전화 시스템 [계획(On-premises PSTN 연결)을 참조하세요.](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- 라이선싱 및 요금제 등 전화 시스템에 대한 자세한 내용은 [비즈니스용 Skype의 PSTN 통화 플랜을 참조하세요.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 비즈니스용 Skype 환경 간의 PSTN 연결도 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>사용자가 전화 시스템으로 이동(프레미스 PSTN 연결)

사용자를 비즈니스용 Skype Online으로 이동하기 전에 사용자를 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스로 사용하도록 설정한 다음 온라인으로 이동하는 것이 좋습니다. 자세한 내용은 비즈니스용 Skype 서버와 비즈니스용 [Skype Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 사용자가 Enterprise Voice(사용자가 홈으로 있는 동안 수행)에 대한 사용의 특별한 고려 [사항](enable-the-users-for-enterprise-voice-on-premises.md) 섹션을 참조하세요. 
  
모든 사용자는 Active Directory에서 만들어야 합니다. 지원되는 버전의 Azure AD Connector를 사용하여 Microsoft 365 또는 Office 365와 동기화해야 합니다. 사용자가 Azure AD에서 직접 만든 Office 365의 전화 시스템을 사용하도록 설정할 수 없습니다. Azure AD에서 만든 사용자에 대해 전화 시스템을 사용할 수 있도록 설정하려면 Azure AD에서 만든 사용자에 대해 새 계정을 만들고, 계정을 구성하고, 지원되는 버전의 Azure AD 커넥터 도구를 사용하여 계정을 동기화해야 합니다. 
  
사용자가온-프레미스 PSTN 연결을 통해 전화 시스템을 사용하도록 설정한 다음 비즈니스용 Skype Online으로 이동하려면 다음 단계가 필요합니다.
  
- [사용자가 Enterprise Voice(사용자가](enable-the-users-for-enterprise-voice-on-premises.md) 홈에 있는 동안 수행) Enterprise Voice 수 있도록 합니다.
    
- [음성 라우팅](assign-a-voice-routing-policy.md) 정책 할당(사용자가 홈에 있는 동안 수행)
    
- [사용자를 클라우드에](synchronize-users-to-the-cloud-and-assign-licenses.md) 동기화하고 라이선스를 할당합니다(Office 365를 사용하여 수행).
    
- [비즈니스용 Skype Online으로](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) Windows PowerShell 사용자를 이동(Windows PowerShell Office 365 관리자 자격 증명을 사용하여 수행)
    
- [사용자가 온라인 및 Enterprise Voice 시스템 음성메일을](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 사용할 수 있도록 합니다(원격 PowerShell을 사용하여 수행).
    

