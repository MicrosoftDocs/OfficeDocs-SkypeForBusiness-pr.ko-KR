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
description: 이 항목에서는 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템에서 사용자를 사용 하도록 설정 하는 방법을 설명 합니다. 이 항목의 단계를 수행 하기 전에 다음을 읽어야 합니다.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359144"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정

이 항목에서는 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템에서 사용자를 사용 하도록 설정 하는 방법을 설명 합니다. 이 항목의 단계를 수행 하기 전에 다음을 읽어야 합니다.
  
- 하이브리드 연결을 설정 하는 방법에 대 한 자세한 내용은 비즈니스용 skype [서버 및 비즈니스용 Skype online의 하이브리드 연결 계획](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 및 비즈니스용 skype [서버 및 비즈니스용 skype online 간 하이브리드 연결 배포](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)를 참조 하세요.
    
- 배포 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템 계획](plan-phone-system-with-on-premises-pstn-connectivity.md)을 참조 하십시오.
    
- 라이선스 및 요금제를 포함 하 여 전화 시스템에 대 한 자세한 내용은 [비즈니스용 Skype에 대 한 PSTN 통화 요금제](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)를 참조 하세요.
    
> [!Important]
> 비즈니스용 Skype Online은 서비스에 더 이상 액세스할 수 없게 되 고, 2021 년 7 월 31 일에 만료 됩니다.  또한 비즈니스용 Skype 서버 또는 클라우드 Connector Edition과 비즈니스용 Skype Online을 통해 온-프레미스 환경 간의 PSTN 연결이 더 이상 지원 되지 않습니다.  [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아봅니다.

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>온-프레미스 PSTN 연결을 사용 하 여 전화 시스템으로 사용자 이동

사용자를 비즈니스용 Skype Online으로 이동 하기 전에 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스 사용자를 사용 하도록 설정한 다음 온라인으로 이동 하는 것이 좋습니다. 자세한 내용은 [비즈니스용 Skype 서버 및 비즈니스용 Skype Online의 하이브리드 연결 계획](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 및 사용자가 온-프레미스에서 [Enterprise Voice For 프레미스를 사용 하도록 설정](enable-the-users-for-enterprise-voice-on-premises.md) 의 특수 고려 사항 섹션을 참조 하십시오. 
  
모든 사용자는 Active Directory에서 온-프레미스로 만들고 지원 되는 버전의 Azure AD Connector를 사용 하 여 Microsoft 365 또는 Office 365와 동기화 해야 합니다. Azure AD에서 직접 만든 Office 365에서 전화 시스템에 대 한 사용자를 사용 하도록 설정할 수는 없습니다. Azure AD에서 만든 사용자에 대해 온-프레미스 PSTN 연결을 통해 전화 시스템을 사용 하도록 설정 하려면 온-프레미스 AD에서 해당 사용자에 대 한 새 계정을 만들고 온-프레미스에 계정을 구성한 다음 지원 되는 Azure AD Connector 도구를 사용 하 여 계정을 동기화 해야 합니다. 
  
온-프레미스 PSTN 연결을 사용 하는 전화 시스템을 사용 하도록 설정한 다음이를 비즈니스용 Skype Online으로 이동 하려면 다음 단계를 수행 해야 합니다.
  
- 사용자가 온-프레미스에서 [Enterprise Voice를 사용 하도록 설정](enable-the-users-for-enterprise-voice-on-premises.md) 합니다 (사용자가 내부에 있는 동안 수행 됨).
    
- [음성 라우팅 정책 할당](assign-a-voice-routing-policy.md) (사용자가 온-프레미스에 있는 동안 수행 됨)
    
- [사용자를 클라우드와 동기화 하 고 라이선스](synchronize-users-to-the-cloud-and-assign-licenses.md) (Office 365을 사용 하 여 수행)를 할당 합니다.
    
- 온 [-프레미스 사용자를 비즈니스용 Skype Online으로 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) 합니다 (Windows PowerShell 온-프레미스를 사용 하지만 Office 365 관리자 자격 증명 사용).
    
- [사용자가 Enterprise Voice online 및 전화 시스템 음성 메일을 사용할 수 있도록](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 합니다 (원격 PowerShell을 사용 하 여 수행).
    

