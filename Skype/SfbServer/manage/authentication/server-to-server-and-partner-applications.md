---
title: OAuth(서버 대 서버 인증) 및 파트너 응용 프로그램을 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '요약: 2013에서 OAuth 및 파트너 응용 프로그램을 비즈니스용 Skype 서버.'
---

# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>OAuth(서버 대 서버 인증) 및 파트너 응용 프로그램을 비즈니스용 Skype 서버
 
**요약:** OAuth 및 파트너 응용 프로그램을 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 응용 프로그램 및 서버 제품과 안전하고 원활하게 통신할 수 있어야 합니다. 예를 들어 비즈니스용 Skype 서버 및/또는 보관 데이터가 Microsoft Exchange Server 2013에 저장하도록 비즈니스용 Skype 서버 Exchange 구성할 수 있습니다. 마찬가지로 Office Web Apps 서버 내에서 비즈니스용 Skype 서버 회의를 예약할 수 있습니다. 다시 말하면 두 서버(SharePoint 및 비즈니스용 Skype 서버)가 서로 트러스트하는 비즈니스용 Skype 서버 수 있습니다. 비즈니스용 Skype 서버 및 Exchange 통신에 하나의 인증 메커니즘을 사용할 수 있지만 비즈니스용 Skype 서버 및 SharePoint 통신을 위한 별도의 메커니즘을 사용할 수도 있지만 모든 서버 간 인증에 표준화된 방법을 사용하는 것이 보다 효율적입니다. 권한 부여.
  
서버 대 서버 인증에 표준화된 단일 방법을 사용하는 것은 서버 대 서버 인증을 사용하는 비즈니스용 Skype 서버. Office Server 2013 릴리스부터는 비즈니스용 Skype 서버 및 Exchange Server 및 SharePoint Server를 비롯한 기타 Microsoft Server 제품도 서버 대 서버 인증 및 권한 부여를 위한 OAuth(Open Authorization) 프로토콜을 지원했습니다. 대부분의 주요 웹 사이트에서 사용되는 표준 권한 부여 프로토콜인 OAuth를 사용하는 경우 사용자 자격 증명과 암호가 컴퓨터 간에 전달되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다.
  
OAuth 인증에는 일반적으로 서로 통신해야 하는 단일 인증 서버와 두 개의 두 개의 주체가 있습니다. 이 문서의  나중에 설명할 프로세스인 인증 서버를 사용하지 않고 서버 대 서버 인증을 할 수도 있습니다. 보안 토큰은 인증 서버(보안 토큰 서버라고도 불림)에서 통신해야 하는 두 가지에 대해 발급됩니다. 이러한 토큰은 한 가지에서 시작된 통신을 다른에서 신뢰해야 하는지 여부를 확인할 수 있습니다. 예를 들어 권한 부여 서버는 특정 비즈니스용 Skype 서버 해당 비즈니스용 Skype 서버 사용자가 지정된 Exchange 액세스할 수 있는지 확인하는 토큰을 발급할 수 있습니다.
  
> [!NOTE]
> 영역은 단순한 보안 컨테이너입니다. 기본적으로 비즈니스용 Skype 서버 SIP 도메인을 OAuth 영역으로 사용할 수 있습니다. 추가 SIP 네임스페이스는 OAuth 인증서의 주체 대체 이름 목록에 추가됩니다. 
  
비즈니스용 Skype 서버 서버 대 서버 인증 시나리오를 지원합니다. 이 비즈니스용 Skype 서버 다음을 할 수 있습니다.
  
- 비즈니스용 Skype 서버 및/또는 Exchange 서버의 사내 설치 간에 서버 간 인증을 SharePoint 구성합니다.
    
- 한 쌍의 Microsoft 365 또는 Office 365 구성 요소 간에 서버 간 인증 구성(예: Microsoft Exchange Server 및 비즈니스용 Skype 서버 또는 비즈니스용 Skype 서버 SharePoint)
    
- 크로스-프레미스 환경에서 서버 간 인증(즉, 사내 서버와 Microsoft 365 또는 Office 365 구성 요소 간의 서버 간 인증)을 구성합니다.
    
현재는 Exchange 2013, SharePoint Server, Lync Server 2013, 비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 2019에서만 서버 대 서버 인증을 지원하고, 이러한 서버 중 하나를 실행하지 않는 경우 OAuth 인증을 완전히 구현할 수 없습니다.
  
또한 서버 대 서버 인증은 선택 사항입니다. 비즈니스용 Skype 서버 다른 서버(예: Exchange)와 통신할 필요가 없는 경우 서버 대 서버 인증을 모두 건너뜁니다. Lync Server 2013 및 기타 응용 프로그램에 대해 서버 대 서버 인증이 이미 구성되어 있는 경우 서버 대 서버 인증을 다시 비즈니스용 Skype 서버. 
  
그러나 "통합 연락처 저장소"처럼 비즈니스용 Skype 서버 기능을 사용하려면 서버 비즈니스용 Skype 서버 인증이 필요합니다. 통합 연락처 저장소를 사용하면 비즈니스용 Skype 서버 연락처 정보가 Exchange 대신 비즈니스용 Skype 서버에 저장됩니다. 이를 통해 사용자는 비즈니스용 Skype, Outlook 또는 연락처 내에서 쉽게 액세스할 수 있는 단일 연락처 집합을 Outlook  웹 액세스. 통합 연락처 저장소를 사용하려면 비즈니스용 Skype 서버 정보를 공유해야 Exchange 기능을 배포하려면 서버 대 서버 인증을 사용해야 합니다. 또한 인스턴트 메시징 세션의 기록이 개별 데이터베이스 레코드가 아닌 전자 메일로 Exchange 보관을 사용하는 경우 서버 Exchange 인증이 필요합니다.
  
Microsoft 365 Office 365 버전의 비즈니스용 Skype 서버 해당 Exchange 통신하려면 비즈니스용 Skype 서버 먼저 인증 서버에서 보안 토큰을 얻어야 합니다. 비즈니스용 Skype 서버 보안 토큰을 사용하여 보안 토큰을 식별하여 Exchange. Microsoft 365 Office 365 또는 Exchange 버전과 통신하려면 동일한 프로세스를 비즈니스용 Skype 서버.
  
그러나 두 Microsoft 서버 간의 온-프레미스 서버 간 인증에서는 타사 토큰 서버를 사용할 필요가 없습니다. 비즈니스용 Skype 서버 Exchange 등의 서버 제품에는 서버 대 서버 인증을 지원하는 다른 Microsoft 서버(예: SharePoint Server)와의 인증에 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 비즈니스용 Skype 서버 자체적으로 보안 토큰을 발급하고 서명한 다음 해당 토큰을 사용하여 보안 토큰과 통신할 Exchange. 이러한 경우에는 타사 토큰 서버가 필요하지 않습니다.
  
비즈니스용 Skype 서버 구현에 대해 서버 대 서버 인증을 구성하려면 다음 두 가지 작업을 실행해야 합니다.
  
- 기본 제공 토큰 발급자에 비즈니스용 Skype 서버 할당합니다.
    
- 통신할 서버를 비즈니스용 Skype 서버 "파트너 응용 프로그램"으로 구성합니다. 예를 들어 비즈니스용 Skype 서버 통신해야 하는 Exchange 파트너 응용 프로그램으로 Exchange 구성해야 합니다.
    
> [!NOTE]
> "파트너 응용 프로그램"비즈니스용 Skype 서버 보안 토큰 서버를 거치지 않고 보안 토큰을 직접 교환할 수 있는 응용 프로그램입니다. 
  
OAuth는 제품의 핵심 부분으로, 사용하지 않도록 설정하거나 제거할 수 없습니다.
  
## <a name="see-also"></a>참고 항목

[서버에 서버 대 서버 인증 인증서를 비즈니스용 Skype 서버](assign-a-server-to-server-certificate.md)
  
[하이브리드 환경에서 하이브리드 비즈니스용 Skype 서버](configure-a-hybrid-environment.md)
