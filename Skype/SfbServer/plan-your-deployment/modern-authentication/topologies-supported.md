---
title: 최신 인증으로 지원 되는 비즈니스용 Skype 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 이 문서에는 비즈니스용 Skype의 최신 인증에서 지원 되는 온라인 및 온-프레미스 토폴로지가 나열 되어 있으며 각 토폴로지에 적용 되는 보안 기능에 대해 설명 합니다.
ms.openlocfilehash: 2eb043768c46406696b32da5dfb84e2358a30749
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815826"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>최신 인증으로 지원 되는 비즈니스용 Skype 토폴로지
 
이 문서에는 비즈니스용 Skype의 최신 인증에서 지원 되는 온라인 및 온-프레미스 토폴로지가 나열 되어 있으며 각 토폴로지에 적용 되는 보안 기능에 대해 설명 합니다.
  
## <a name="modern-authentication-in-skype-for-business"></a>비즈니스용 Skype의 최신 인증

비즈니스용 Skype는 최신 인증의 보안 이점을 활용할 수 있습니다. 비즈니스용 Skype는 Exchange와 밀접 하 게 연동 되므로 비즈니스용 skype 클라이언트 사용자의 로그인 동작은 Exchange의 MA 상태에도 영향을 받게 됩니다. 비즈니스용 Skype 분할 도메인 하이브리드이 있는 경우에도 적용 됩니다. 이는 이동 부품이 많지만, 여기에 있는 목적은 지원 되는 토폴로지 목록을 시각화 하기가 쉽습니다.
  
비즈니스용 Skype, 비즈니스용 Skype online, Exchange Server, Exchange online, MA에서 지원 되는 토폴로지는 무엇 인가요?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>비즈니스용 Skype에서 지원 되는 MA 토폴로지

MA에 사용 되는 비즈니스용 Skype 토폴로지와 관련 된 두 대의 서버 응용 프로그램 및 두 개의 Office 365 작업 부하가 있을 수 있습니다.
  
- 온-프레미스 (비즈니스용 Skype server) (CU (5)
    
- 비즈니스용 Skype online (SFBO)
    
- Exchange server 온-프레미스
    
- Exchange server online (EXO)
    
MA의 또 다른 중요 한 부분은 사용자의 인증 (authN) 및 권한 부여 (승인)가 발생 하는 위치를 아는 것입니다. 두 가지 옵션은 다음과 같습니다.
  
- Azure AD, Microsoft 클라우드의 온라인
    
- 온-프레미스 ADFS (Active Directory Federation Server)
    
이는 Azure AD를 사용 하는 클라우드에서는 EXO와 SFBO, Exchange Server (EXO) 및 비즈니스용 Skype 서버 (SFB)에 대 한 온-프레미스에 대 한 자세한 내용은 다음과 같습니다.
  
![모든 응용 프로그램 (Exchange 및 비즈니스용 Skype) 및 작업 부하 (EXO 및 SFBO)와 MA를 설정할 때 참여할 수 있는 권한 부여 서버 (ADF 및 evoSTS)의 예입니다.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
지원 되는 토폴로지는 다음과 같습니다. 그래픽의 키에 유의 하세요.
  
- 아이콘이 흐리게 또는 회색으로 표시 된 경우 시나리오에서 사용 되지 않습니다.
    
- EXO는 Exchange Online입니다.
    
- 비즈니스용 Skype Online은 SFBO입니다.
    
- EXCH는 Exchange 온-프레미스입니다.
    
- 비즈니스용 Skype 온-프레미스를 SFB.
    
- 예를 들어 서버에 대 한 권한 부여는 삼각형으로 표시 됩니다. 예를 들어 Azure AD는 그 뒤에 클라우드가 있는 삼각형입니다.
    
- 클라이언트가 지정 된 서버 리소스에 도달 하려고 할 때 사용 될 권한 부여 서버를 가리키는 화살표입니다.
    
먼저, 온-프레미스 전용 또는 클라우드 전용 토폴로지 모두에서 비즈니스용 Skype를 사용 하 여 MA를 살펴보겠습니다.
  
> [!IMPORTANT]
> 비즈니스용 Skype Online에서 최신 인증을 설정할 준비가 되었나요? 이 기능을 사용 하도록 설정 하는 단계는 [여기](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)에서 바로 확인 하세요. 
  
|토폴로지 이름  <br/> |예  <br/> |설명  <br/> |지원  <br/> |
|:-----|:-----|:-----|:-----|
|클라우드만  <br/> |![MA 토폴로지, 클라우드 전용으로 지원 되는 SFB.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)사용자 홈/사서함 위치: 온라인  <br/> |MA가 EXO 및 SFBO 둘 다에 대해 켜져 있습니다.  <br/> 따라서 인증 서버는 Azure AD입니다.  <br/> |MFA (다단계 인증), 클라이언트-인증서 기반 인증 (CBA), Intune을 사용 하는 CA (조건부 액세스)/MAM (모바일 응용 프로그램 관리) \*  <br/> |
|온-프레미스  <br/> |![MA 토폴로지, 온-프레미스 전용으로 지원 되는 SFB.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)사용자 홈/사서함 위치: 온-프레미스  <br/> |MA가 온-프레미스에 대해 SFB입니다.  <br/> 따라서 인증 서버는 ADFS입니다.  <br/> 구성 세부 정보는 [이 문서](https://technet.microsoft.com/en-us/library/mt710548.aspx) 를 참조 하세요. <br/> |MFA (Windows 데스크톱 전용-모바일 클라이언트는 지원 되지 않음) Exchange 통합 기능이 없습니다.  <br/><p> **이 방법을 사용 하지 않는 것이 좋습니다. 다음을 참조 하세요.**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> 메시지 수를 줄이려면 MA 상태가 비즈니스용 Skype 및 Exchange (및 온라인 대응)에서 동일 하 게 유지 되도록 하는 것이 좋습니다. 
  
혼합 토폴로지에는 SFB 분할 도메인 하이브리드 조합이 포함 됩니다. 현재 지원 되는 혼합 토폴로지는 다음과 같습니다.
  
|토폴로지 이름  <br/> |예  <br/> |설명  <br/> |지원  <br/> |
|:-----|:-----|:-----|:-----|
|혼합 1  <br/> |![MA 토폴로지, 혼합 1 (EXO + SFB)으로 지원 되는 SFB.](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 사용자 홈/사서함 위치: EXO 및 SFB  <br/> |MA는 SFB에 대해 사용 하도록 설정 되지 않습니다. 이 토폴로지에서는 SFB MA 기능을 사용할 수 없습니다.  <br/> |SFB에 대 한 MA 기능이 없습니다.  <br/> |
|혼합 2  <br/> |![S4B 혼합 토폴로지 2, SFBO + MA와 함께 지원 되는 MA on-프레미스를 사용 하 여 작업](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 사용자 홈/사서함 위치: EXCH 및 SFBO  <br/> |MA는 SFBO에 대해서만 켜져 있습니다. 권한 부여 서버는 SFBO에 속한 사용자의 Azure AD 이며 EXCH 온-프레미스의 광고입니다.  <br/> |Intune을 사용 하는 MFA, CBA, CA/MAM\*  <br/> |
|혼합 3  <br/> |![SFB, MA가 설정 되어 있는 EXO, EXO 및 SFB 온-프레미스로 지원 되는 MA.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 사용자 홈/사서함 위치: EXO + SFB 또는 EXO + SFB  <br/> |이 토폴로지에서는 SFB MA 기능을 사용할 수 없습니다.  <br/> |SFB에 대 한 MA 기능이 없습니다.  <br/> |
|혼합 4  <br/> |![SFB, SFBO와 함께 지원 되는 MA, + m CH 및 SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 사용자 홈/사서함 위치: EXCH + SFBO 또는 EXCH + SFB  <br/> |MA가 SFBO에 대해 설정 되어 있으므로 인증 서버는 SFBO에 속한 사용자의 Azure AD입니다. SFB 및 EXO의 프레미스 사용자가 광고를 사용 합니다.  <br/> |온라인 사용자 용 Intune을 사용 하는 MFA, CBA, CA/MAM\*  <br/> |
|혼합 5  <br/> |![SFB에서 지원 되는 MA, MA와 함께 EXO, MA와 SFBO, e SFB](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 사용자 홈/사서함 위치: EXO + SFBO, EXO + SFB, EXO + SFBO 또는 EXO + SFB  <br/> |MA가 EXO 및 SFBO 둘 다에서 켜져 있으므로 인증 서버는 SFBO에 속한 사용자의 Azure AD입니다. EXCH의 프레미스 사용자 및 SFB AD를 사용 합니다.  <br/> |온라인 사용자 용 Intune을 사용 하는 MFA, CBA, CA/MAM\*  <br/> |
|혼합 6  <br/> |![혼합 6 토폴로지에서 최신 인증은 최신 인증에 제공 되는 모든 4 가지 possibile 위치에서 이상적인 situtation입니다.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 사용자 홈/사서함 위치: EXO + SFBO, EXO + SFB, EXO + SFBO 또는 EXO + SFB  <br/> |MA는 모든 곳에서 사용할 수 있으므로 인증 서버는 모든 사용자에 대해 Azure AD입니다. (온라인 및 온-프레미스)  <br/>  배포 단계 [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) 를 참조 하세요. <br/> |모든 사용자에 대 한 MFA, CBA 및 CA/MAM (Intune을 통해)  <br/> |
   
\*-MFA에는 Windows 데스크톱, MAC, iOS, Android 장치, Windows phone이 포함 됩니다. CBA에는 Windows 데스크톱, iOS, Android 장치 등이 포함 됩니다. Intune을 사용 하는 CA/MAM에는 Android 및 iOS 장치가 포함 됩니다. 
  
> [!IMPORTANT]
> 모든 버전의 혼합 토폴로지의 경우와 같이 클라이언트가 필요로 하 고 요청 하는 모든 서버 리소스에서 MA 상태가 동일 하지 않은 경우에는 경우에 따라 사용자에 게 **여러 프롬프트가** 표시 될 수 있다는 점에 주의 해야 합니다.

> [!IMPORTANT]
> 또한 일부 경우 (혼합 1, 3, 5)는 Windows 데스크톱 클라이언트에 대 한 적절 한 구성에 대해 [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) 레지스트리 키를 설정 해야 한다는 점에 유의 하세요.
  

