---
title: 비즈니스용 Skype 서버 2015와 Exchange 통합 계획
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
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '요약: Exchange Server 2016 또는 Exchange Server 2013과 비즈니스용 Skype 서버를 통합 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 995511f55d131bfd3d446f5691563436c19da2c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815886"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>비즈니스용 Skype 서버 2015와 Exchange 통합 계획
 
**요약:** 비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013와 통합 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
비즈니스용 Skype 서버와 Exchange Server를 통합 하려면 먼저 Exchange Server와 비즈니스용 Skype 서버가 모두 설치 되어 있고 실행 중인지 확인 해야 합니다. 
  
Exchange Server 설치에 대 한 자세한 내용은 exchange 버전에 대 한 Exchange Server 계획 및 배포 설명서를 참조 하세요. 
   
서버가 작동 하 고 실행 된 후에는 서버 간 인증 인증서를 비즈니스용 Skype 서버와 Exchange Server 모두에 할당 해야 합니다. 이러한 인증서는 비즈니스용 Skype 서버와 Exchange Server가 정보를 교환 하 고 서로 통신할 수 있도록 합니다. Exchange Server를 설치할 때 Microsoft Exchange Server 인증 인증서 이름의 자체 서명 된 인증서가 만들어집니다. 로컬 컴퓨터 인증서 저장소에서 찾을 수 있는이 인증서는 Exchange Server에서 서버 간 인증에 사용 해야 합니다. Exchange Server에서 인증서를 할당 하는 방법에 대 한 자세한 내용은 [메일 흐름 및 클라이언트 액세스 구성을](https://go.microsoft.com/fwlink/p/?LinkId=268540)참조 하세요.
  
비즈니스용 Skype 서버를 사용 하는 경우, 서버 간 인증 인증서로 기존 비즈니스용 Skype 서버 인증서를 사용할 수 있습니다. 예를 들어 기본 인증서는 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. 비즈니스용 Skype Server에서는 다음과 같은 경우 서버 간 인증을 위한 인증서로 웹 서버 인증서를 사용할 수 있습니다.
  
- 인증서는 제목 필드에 SIP 도메인의 이름을 포함 합니다.
    
- 동일한 인증서가 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서로 구성 되어 있습니다.
    
- 인증서의 길이는 최소 2048 비트입니다.
    
비즈니스용 Skype Server에 대 한 서버 간 인증 인증서에 대 한 자세한 내용은 비즈니스용 Skype 서버에 서버 간 [인증 인증서 할당](../../manage/authentication/assign-a-server-to-server-certificate.md)을 참조 하세요.
  
인증서를 할당 한 후에는 Exchange Server에서 자동 검색 서비스를 구성 해야 합니다. Exchange Server에서 자동 검색 서비스는 사용자 프로필을 구성 하 고 사용자가 시스템에 로그온 할 때 Exchange 서비스에 대 한 액세스를 제공 합니다. 사용자가 전자 메일 주소와 암호를 사용 하 여 자동 검색 서비스를 제공 합니다. 그런 다음 서비스는 사용자에 게 다음과 같은 정보를 제공 합니다.
  
- Exchange Server 내부 및 외부 연결 모두에 대 한 연결 정보.
    
- 사용자 사서함 서버의 위치입니다.
    
- 약속 있음/없음 정보, 통합 메시징, 오프 라인 주소록과 같은 Outlook 기능에 대 한 Url입니다.
    
- Outlook Anywhere 서버 설정
    
비즈니스용 Skype 서버 및 Exchange Server를 통합 하려면 자동 검색 서비스를 구성 해야 합니다. Exchange Server Management Shell에서 다음 명령을 실행 하 고 AutoDiscoverServiceInternalUri 속성 값을 확인 하 여 자동 검색 서비스가 구성 되었는지 여부를 확인할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

이 값이 비어 있으면 자동 검색 서비스에 URI를 할당 해야 합니다. 일반적으로이 URI는 다음과 같습니다.https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
다음과 같은 명령을 실행 하 여 자동 검색 URI를 할당할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

자동 검색 서비스에 대 한 자세한 내용은 [자동 검색 서비스](https://go.microsoft.com/fwlink/p/?LinkId=268542)를 참조 하세요.
  
자동 검색 서비스를 구성한 후에는 비즈니스용 Skype Server OAuth 구성 설정을 수정 해야 합니다. 이렇게 하면 비즈니스용 Skype 서버에서 자동 검색 서비스를 찾을 수 있는 위치를 인식 하 게 됩니다. 비즈니스용 Skype Server의 OAuth 구성 설정을 수정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다. 이 명령을 실행 하는 경우 Exchange Server에서 실행 되는 자동 검색 서비스에 대 한 URI를 지정 하 고 서비스에서 사용 하는 XML 파일을 **가리키는 자동 검색** 을 사용 하 여 서비스 위치를 가리키는 방법을 선택 **해야 합니다.**
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 앞의 명령에서 Identity 매개 변수는 선택 사항입니다. 이는 비즈니스용 Skype 서버 에서만 OAuth 구성 설정의 단일 전역 컬렉션을 사용할 수 있기 때문입니다. 즉, 다음과 같이 약간 더 간단한 명령을 사용 하 여 자동 검색 URL을 구성할 수 있습니다. 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> 기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용 하는 표준 인증 프로토콜입니다. OAuth를 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰의 교환에 기반을 둔 것입니다. 이러한 토큰은 특정 기간 동안 특정 리소스 집합에 대 한 액세스 권한을 부여 합니다. 
  
자동 검색 서비스를 구성 하는 것 외에도 Exchange Server를 가리키는 서비스에 대 한 DNS 레코드를 만들어야 합니다. 예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com에 있는 경우 Exchange 서버의 정규화 된 도메인 이름으로 확인 되는 autodiscover.litwareinc.com에 대 한 DNS 레코드를 만들어야 합니다 (예: atl-exchange-001.litwareinc.com).
  
Exchange Online과 함께 비즈니스용 Skype 서버를 통합 하는 경우 다음 단계는 온 [-프레미스 비즈니스용 Skype server 및 Outlook Web App 간 통합 구성](../../deploy/integrate-with-exchange-server/outlook-web-app.md)에 있습니다. 그렇지 않은 경우에는 비즈니스용 [Skype 서버와 Exchange server 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)을 참조 하세요.
  
## <a name="feature-support"></a>기능 지원
<a name="feature_support"> </a>

다음 표에서는 Exchange 및 비즈니스용 Skype에 대 한 다양 한 온라인 또는 온-프레미스 조합에서 지원 되는 기능에 대해 설명 합니다.
  
||**Exchange 2016/2013/2010 (온-프레미스) + 비즈니스용 Skype 서버 (온-프레미스)**|**Exchange Online + 비즈니스용 Skype 서버 (온-프레미스)**|**Exchange 2010 (온-프레미스) + 비즈니스용 Skype Online**|**Exchange 2016/2013 (온-프레미스) 및 비즈니스용 Skype Online**|**Exchange Online + 비즈니스용 Skype Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook에서의 현재 상태  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 영상 통화를 통해 응답  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook Web App에서 현재 상태  <br/> |피지  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|IM, PSTN 통화, Skype 통화 또는 OWA 전자 메일의 영상 통화를 통해 응답  <br/> |피지  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|Outlook Web App을 통해 온라인 모임 예약 및 참가  <br/> |피지  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|모바일 클라이언트에서 메신저 대화/현재 상태  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|모바일 클라이언트에서 온라인 모임 참가  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|연락처 목록 (통합 된 대화 상대 저장소를 통해)  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|고해상도 연락처 사진 (Lync 2013 또는 비즈니스용 Skype 클라이언트가 최소한으로 필요 합니다. LWA, 모바일 앱, Lync 2010, Mac 용 Lync 및 기타 이전 클라이언트에는 지원 되지 않습니다.  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |개  <br/> |피지  <br/> |피지  <br/> |
|모임 위임  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Exchange에서 콘텐츠 (IM 및 모임) 보관  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|보관 된 콘텐츠 검색  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |개  <br/> |개  <br/> |피지  <br/> |
|Exchange UM 음성 메일  <br/> |피지  <br/> |피지  <br/> |개  <br/> |개  <br/> |개  <br/> |
|서버 쪽 대화 내용  <br/> |피지  <br/> |피지  <br/> |개  <br/> |피지  <br/> |피지  <br/> |

> [!NOTE]
> 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype Server 2015, Lync Server 2013에 대해 지원 되는 클라우드 보이스 메일 서비스가 있습니다.
> 

## <a name="see-also"></a>참고 항목
<a name="feature_support"> </a>

[온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[비즈니스용 Skype Online 및 온-프레미스 간 OAuth 구성](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Exchange Server와 비즈니스용 Skype 서버 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013을 Lync Server 2013, 비즈니스용 Skype Online 또는 Lync Server 2013 하이브리드 배포와 통합 하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[비즈니스용 Skype 서버 및 Microsoft Exchange Server에서 파트너 응용 프로그램 구성](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
