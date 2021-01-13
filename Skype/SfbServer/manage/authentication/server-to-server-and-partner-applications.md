---
title: 비즈니스용 Skype 서버에서 OAuth(서버 대 서버 인증) 및 파트너 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '요약: 비즈니스용 Skype 서버에서 OAuth 및 파트너 응용 프로그램을 관리합니다.'
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828308"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 OAuth(서버 대 서버 인증) 및 파트너 응용 프로그램 관리
 
**요약:** 비즈니스용 Skype 서버에서 OAuth 및 파트너 응용 프로그램을 관리합니다.
  
비즈니스용 Skype 서버는 다른 응용 프로그램 및 서버 제품과 안전하고 원활하게 통신할 수 있어야 합니다. 예를 들어 연락처 데이터 및/또는 보관 데이터가 Microsoft Exchange Server 2013에 저장하도록 비즈니스용 Skype 서버를 구성할 수 있습니다. 그러나 이는 비즈니스용 Skype 서버와 Exchange가 안전하게 서로 통신할 수 있는 경우만 가능합니다. 마찬가지로 Office Web Apps 서버 내에서 비즈니스용 Skype 서버 회의를 예약할 수 있습니다. 다시 말하면 두 서버(SharePoint 및 비즈니스용 Skype 서버)가 서로 트러스트하는 것만 가능합니다. 비즈니스용 Skype 서버와 Exchange 간의 통신에는 하나의 인증 메커니즘을 사용할 수 있지만 비즈니스용 Skype 서버와 SharePoint 통신을 위한 별도의 메커니즘을 사용할 수도 있지만 모든 서버 간 인증 및 권한 부여에 표준화된 방법을 사용하는 것이 더 효율적이고 효율적입니다.
  
서버 대 서버 인증에 표준화된 단일 방법을 사용하는 것은 비즈니스용 Skype 서버에서 사용하는 방법입니다. Office Server 2013 릴리스부터 비즈니스용 Skype 서버(Exchange Server 및 SharePoint Server를 비롯한 기타 Microsoft Server 제품)는 서버 대 서버 인증 및 권한 부여를 위한 OAuth(Open Authorization) 프로토콜을 지원했습니다. 대부분의 주요 웹 사이트에서 사용되는 표준 권한 부여 프로토콜인 OAuth를 사용하는 경우 사용자 자격 증명과 암호가 컴퓨터 간에 전달되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다.
  
OAuth 인증에는 일반적으로 서로 통신해야 하는 두 개의 통합 서버와 단일 인증 서버의 세 주체가 있습니다. (이 문서의 나중에 설명될 프로세스인 인증 서버를 사용하지 않고 서버 대 서버 인증을 할 수도 있습니다.) 보안 토큰은 인증 서버(보안 토큰 서버라고도 불림)에서 통신해야 하는 두 가지에 대해 발급됩니다. 이러한 토큰은 한 가지에서 시작된 통신이 다른영야에서 신뢰하는지 확인해야 합니다. 예를 들어 권한 부여 서버는 특정 비즈니스용 Skype 서버의 사용자가 지정된 Exchange에 액세스할 수 있는지, 또는 그 반대로 액세스할 수 있는지를 확인하는 토큰을 발급할 수 있습니다.
  
> [!NOTE]
> 영역은 단순한 보안 컨테이너입니다. 기본적으로 비즈니스용 Skype 서버는 기본 SIP 도메인을 OAuth 영역으로 사용하게 됩니다. OAuth 인증서의 주체 대체 이름 목록에 추가 SIP 네임스페이스가 추가됩니다. 
  
비즈니스용 Skype 서버는 세 가지 서버 대 서버 인증 시나리오를 지원합니다. 비즈니스용 Skype 서버를 사용하여 다음을 할 수 있습니다.
  
- 비즈니스용 Skype 서버의 프레미스 설치와 Exchange 및/또는 SharePoint Server의 프레미스 설치 간에 서버 간 인증을 구성합니다.
    
- Microsoft 365 또는 Office 365 구성 요소 쌍(예: Microsoft Exchange Server 및 비즈니스용 Skype 서버 사이 또는 비즈니스용 Skype 서버와 SharePoint 간) 간에 서버 간 인증을 구성합니다.
    
- 크로스-프레미스 환경에서 서버 간 인증을 구성합니다(즉, Office 365 또는 Office 365 구성 요소와의 서버 간 인증).
    
이때는 Exchange 2013, SharePoint Server, Lync Server 2013, 비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 2019만 서버 대 서버 인증을 지원하고 있습니다. 이러한 서버 중 하나를 실행하지 않는 경우 OAuth 인증을 완전히 구현할 수 없습니다.
  
또한 서버 대 서버 인증은 선택 사항입니다. 비즈니스용 Skype 서버가 다른 서버(예: Exchange)와 통신할 필요가 없는 경우 서버 대 서버 인증을 모두 건너뜁니다. Lync Server 2013 및 기타 응용 프로그램에 대해 서버 대 서버 인증이 이미 구성되어 있는 경우 비즈니스용 Skype 서버에 대해 다시 구성할 필요가 없습니다. 
  
그러나 비즈니스용 Skype 서버의 일부 기능(예: "통합 연락처 저장소")을 사용하려면 서버 대 서버 인증이 필요합니다. 통합 연락처 저장소를 사용할 경우 비즈니스용 Skype 서버 연락처 정보는 비즈니스용 Skype 서버 대신 Exchange에 저장됩니다. 이를 통해 사용자는 비즈니스용 Skype, Outlook 또는 Outlook Web Access에서 쉽게 액세스할 수 있는 단일 연락처 집합을 사용할 수 있습니다. 통합 연락처 저장소를 사용하려면 비즈니스용 Skype 서버가 Exchange와 정보를 공유해야 하기 때문에 기능을 배포하려면 서버 대 서버 인증을 사용해야 합니다. 또한 인스턴트 메시징 세션의 기록이 개별 데이터베이스 레코드가 아닌 Exchange 전자 메일로 저장되는 Exchange 보관을 사용하려면 서버 대 서버 인증이 필요합니다.
  
비즈니스용 Skype 서버의 Microsoft 365 또는 Office 365 버전이 해당 Exchange 서버와 통신하려면 비즈니스용 Skype 서버가 먼저 인증 서버에서 보안 토큰을 얻어야 합니다. 그런 다음 비즈니스용 Skype 서버는 해당 보안 토큰을 사용하여 Exchange를 식별합니다. 비즈니스용 Skype 서버와 통신하려면 Microsoft 365 또는 Office 365 버전의 Exchange도 동일한 프로세스를 거치야 합니다.
  
그러나 두 Microsoft 서버 간의 온-프레미스 서버 간 인증에서는 타사 토큰 서버를 사용할 필요가 없습니다. 비즈니스용 Skype 서버 및 Exchange와 같은 서버 제품에는 서버 대 서버 인증을 지원하는 다른 Microsoft 서버(예: SharePoint Server)와의 인증에 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 비즈니스용 Skype 서버는 자체적으로 보안 토큰을 발급하고 서명한 다음 해당 토큰을 사용하여 Exchange와 통신할 수 있습니다. 이러한 경우에는 타사 토큰 서버가 필요하지 않습니다.
  
비즈니스용 Skype 서버의 프레미스 구현에 대해 서버 대 서버 인증을 구성하려면 다음 두 가지 작업을 해야 합니다.
  
- 기본 제공 비즈니스용 Skype 서버 토큰 발급자에 인증서를 할당합니다.
    
- 비즈니스용 Skype 서버가 통신할 서버를 "파트너 응용 프로그램"으로 구성합니다. 예를 들어 비즈니스용 Skype 서버가 Exchange와 통신해야 하는 경우 Exchange를 파트너 응용 프로그램으로 구성해야 합니다.
    
> [!NOTE]
> "파트너 응용 프로그램"은 비즈니스용 Skype 서버에서 타사 보안 토큰 서버를 거치지 않고도 보안 토큰을 직접 교환할 수 있는 응용 프로그램입니다. 
  
OAuth는 제품의 핵심 부분으로, 사용하지 않도록 설정하거나 제거할 수 없습니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에 서버 대 서버 인증 인증서 할당](assign-a-server-to-server-certificate.md)
  
[비즈니스용 Skype 서버에서 하이브리드 환경 구성](configure-a-hybrid-environment.md)
