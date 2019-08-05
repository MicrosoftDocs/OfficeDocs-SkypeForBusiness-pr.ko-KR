---
title: 비즈니스용 Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '요약: 비즈니스용 Skype 서버에서 OAuth 및 파트너 응용 프로그램을 관리 합니다.'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196907"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리
 
**요약:** 비즈니스용 Skype 서버에서 OAuth 및 파트너 응용 프로그램을 관리 합니다.
  
비즈니스용 Skype 서버는 다른 응용 프로그램 및 서버 제품과 통신 하 고 원활 하 게 통신할 수 있어야 합니다. 예를 들어 연락처 데이터 및/또는 보관 데이터가 Microsoft Exchange Server 2013에 저장 되도록 비즈니스용 Skype 서버를 구성할 수 있습니다. 그러나이 작업은 비즈니스용 Skype 서버와 Exchange가 서로 안전 하 게 통신할 수 있는 경우에만 가능 합니다. 마찬가지로 Office Web Apps 서버 내에서 비즈니스용 Skype 서버 회의를 예약할 수 있습니다. 이 작업은 두 서버 (SharePoint 및 비즈니스용 Skype Server)가 서로 신뢰 하는 경우에만 수행할 수 있습니다. 비즈니스용 Skype 서버와 Exchange 간의 통신에는 인증 메커니즘을 하나만 사용할 수 있지만, 비즈니스용 Skype 서버와 SharePoint 통신을 위한 별도의 메커니즘을 사용 하는 것이 더 쉽고 효율적인 방법을 사용 하는 것입니다. 모든 서버 간 인증 및 권한 부여에 대 한 표준화 된 방법입니다.
  
서버 간 인증에 대해 표준화 된 단일 메서드를 사용 하는 것은 비즈니스용 Skype 서버에서 수행 하는 방법입니다. Office server 2013 릴리스를 시작 하면 비즈니스용 Skype 서버 (Exchange Server 및 SharePoint Server 포함)는 OAuth (열기 권한 부여) 프로토콜을 사용 하 여 서버 간 인증을 지원 하 고 부여할. 여러 주요 웹사이트에서 사용 되는 OAuth, 표준 인증 프로토콜을 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰의 교환에 기반을 둔 것입니다. 이러한 토큰은 특정 기간 동안 특정 리소스 집합에 대 한 액세스 권한을 부여 합니다.
  
OAuth 인증은 일반적으로 하나의 인증 서버와 서로 통신 해야 하는 두 개의 영역과 관련 하 여 세 가지를 수행 합니다. (이 문서의 뒷부분에서 설명할 프로세스 인 권한 부여 서버를 사용 하지 않고 서버 간 인증을 수행할 수도 있습니다.) 보안 토큰은 통신 해야 하는 두 개의 영역에 대 한 권한 부여 서버 (보안 토큰 서버 라고도 함)에서 발급 합니다. 이러한 토큰은 한 영역에서 보낸 통신을 다른 영역에서 신뢰 해야 하는지 여부를 확인 합니다. 예를 들어 권한 부여 서버는 특정 비즈니스용 Skype 서버 영역의 사용자가 지정 된 Exchange 영역에 액세스할 수 있는지 확인 하는 토큰을 발급할 수 있으며 그 반대의 경우도 마찬가지입니다.
  
> [!NOTE]
> 영역은 단순히 보안 컨테이너입니다. 기본적으로 비즈니스용 Skype 서버는 기본 SIP 도메인을 OAuth 영역으로 사용 합니다. 추가 SIP 네임 스페이스는 OAuth 인증서의 주체 대체 이름 목록에 추가 됩니다. 
  
비즈니스용 Skype 서버는 세 가지 서버에서 서버 간 인증 시나리오를 지원 합니다. 비즈니스용 Skype 서버를 사용 하 여 다음을 수행할 수 있습니다.
  
- 비즈니스용 Skype Server의 온-프레미스 설치와 Exchange 및/또는 SharePoint Server의 온-프레미스 설치 간에 서버 간 인증을 구성 합니다.
    
- 한 쌍의 Office 365 구성 요소 (예: Microsoft Exchange Server와 비즈니스용 Skype 서버 간 또는 비즈니스용 Skype 서버와 SharePoint 간) 간에 서버 간 인증을 구성 합니다.
    
- 교차 구내 환경에서 서버 간 인증을 구성 합니다 (즉, 온-프레미스 서버와 Office 365 구성 요소 간에 서버 간 인증).
    
이 시점에서는 Exchange 2013, SharePoint Server, Lync Server 2013, 비즈니스용 Skype Server 2015 및 비즈니스용 Skype 2019만 서버 간 인증을 지원 합니다. 이러한 서버 중 하나를 실행 하지 않는 경우에는 OAuth 인증을 완전히 구현할 수 없습니다.
  
또한 서버 간 인증은 선택적입니다. 비즈니스용 Skype Server가 다른 서버 (예: Exchange)와 통신할 필요가 없는 경우에는 서버 간 인증을 완전히 건너뛸 수 있습니다. Lync Server 2013 및 기타 응용 프로그램에 대해 서버에서 서버 간 인증이 이미 구성 되어 있는 경우 비즈니스용 Skype Server에 대해 다시 수행할 필요가 없습니다. 
  
그러나 비즈니스용 Skype 서버의 일부 기능 (예: "통합 된 연락처 저장소")을 사용 하려는 경우 서버 간 인증이 필요 합니다. 통합 된 대화 상대 저장소에서 비즈니스용 Skype 서버 연락처 정보는 비즈니스용 Skype 서버 대신 Exchange에 저장 됩니다. 이를 통해 사용자는 비즈니스용 Skype, Outlook 또는 Outlook Web Access에서 쉽게 액세스할 수 있는 단일 연락처 집합을 가질 수 있습니다. 통합 된 연락처 저장소에는 Exchange와 정보를 공유 하는 비즈니스용 Skype 서버가 필요 하기 때문에 기능을 배포 하려면 서버에서 서버 간 인증을 사용 해야 합니다. 인스턴트 메시징 세션의 기록이 개별 데이터베이스 레코드가 아닌 Exchange 전자 메일로 저장 되는 Exchange 보관을 사용 하도록 선택한 경우에도 서버 간 인증이 필요 합니다.
  
Exchange와 통신 하는 Office 365 버전의 비즈니스용 Skype 서버의 경우 비즈니스용 Skype 서버에서 먼저 권한 부여 서버 로부터 보안 토큰을 얻어야 합니다. 그런 다음 비즈니스용 Skype 서버는 해당 보안 토큰을 사용 하 여 자신을 Exchange에 식별 합니다. Office 365 버전의 Exchange는 비즈니스용 Skype 서버와 통신 하기 위해 동일한 프로세스를 거쳐야 합니다.
  
그러나 두 Microsoft 서버 간에 온-프레미스 서버 간 인증은 타사 토큰 서버를 사용할 필요가 없습니다. 비즈니스용 Skype 서버 및 Exchange와 같은 서버 제품에는 서버 간 인증을 지 원하는 다른 Microsoft 서버 (예: SharePoint Server)의 인증 용도로 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 비즈니스용 Skype 서버는 보안 토큰 자체를 발급 하 고 서명을 한 다음 해당 토큰을 사용 하 여 Exchange와 통신 합니다. 이와 같은 경우에는 타사 토큰 서버를 사용할 필요가 없습니다.
  
비즈니스용 Skype Server의 온-프레미스 구현에 대해 서버 간 인증을 구성 하려면 다음 두 가지 작업을 수행 해야 합니다.
  
- 기본 제공 비즈니스용 Skype 서버 토큰 발행자에 인증서를 할당 합니다.
    
- 비즈니스용 Skype 서버에서 "파트너 응용 프로그램"으로 통신 하도록 서버를 구성 합니다. 예를 들어 비즈니스용 Skype 서버에서 Exchange와 통신 해야 하는 경우에는 파트너 응용 프로그램이 되도록 Exchange를 구성 해야 합니다.
    
> [!NOTE]
> "파트너 응용 프로그램"은 타사 보안 토큰 서버를 거치지 않고도 비즈니스용 Skype 서버가 보안 토큰을 직접 교환할 수 있는 응용 프로그램입니다. 
  
OAuth는 제품의 핵심 부분이 며 사용 하지 않도록 설정 하거나 제거할 수 없습니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에 서버 간 인증 인증서 할당](assign-a-server-to-server-certificate.md)
  
[비즈니스용 Skype 서버에서 하이브리드 환경 구성](configure-a-hybrid-environment.md)
