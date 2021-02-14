---
title: 비즈니스용 Skype 및 Exchange 통합 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '요약: 비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013과 통합하는 방법에 대한 자세한 내용을 검토합니다.'
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810103"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange 통합 계획
 
**요약:** 비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 통합하는 방법에 대한 자세한 내용은 이 항목을 검토하세요.
  
비즈니스용 Skype 서버와 비즈니스용 Skype Exchange Server 통합하려면 Exchange Server 및 비즈니스용 Skype 서버가 모두 완전히 설치되고 실행되고 실행 중인지 확인해야 합니다. 
  
Exchange 설치에 대한 자세한 Exchange Server Exchange 버전에 대한 Exchange Server 계획 및 배포 설명서를 참조하십시오. 
   
서버가 실행되고 나면 비즈니스용 Skype 서버와 서버 모두에 서버 대 서버 인증 인증서를 할당해야 Exchange Server. 이러한 인증서를 통해 비즈니스용 Skype 서버와 Exchange Server 정보를 교환하고 서로 통신할 수 있습니다. 인증서를 Exchange Server 인증 인증서 이름과 함께 Microsoft Exchange Server 인증서가 만들어집니다. 로컬 컴퓨터 인증서 저장소에서 찾을 수 있는 이 인증서는 로컬 컴퓨터 인증서 저장소의 서버 대 서버 인증에 Exchange Server. 인증서를 할당하는 Exchange Server 메일 흐름 및 클라이언트 액세스 [구성을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268540)
  
비즈니스용 Skype 서버의 경우 기존 비즈니스용 Skype 서버 인증서를 서버 대 서버 인증 인증서로 사용할 수 있습니다. 예를 들어 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. 비즈니스용 Skype 서버를 사용하면 다음에 제공된 모든 웹 서버 인증서를 서버 대 서버 인증용 인증서로 사용할 수 있습니다.
  
- 인증서에는 주체 필드의 SIP 도메인 이름이 포함됩니다.
    
- 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서와 동일한 인증서가 구성됩니다.
    
- 인증서의 길이는 2048비트 이상입니다.
    
비즈니스용 Skype 서버의 서버 대 서버 인증 인증서에 대한 자세한 내용은 비즈니스용 Skype 서버에 서버 대 [서버 인증 인증서 할당을 참조하세요.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
인증서가 할당된 후 인증서에서 자동 Exchange Server. 자동 Exchange Server 서비스에서는 사용자 프로필을 구성하고 사용자가 시스템에 로그온할 때 Exchange 서비스에 대한 액세스를 제공합니다. 사용자가 전자 메일 주소와 암호를 사용하여 자동 자동 전자 메일 서비스를 제공합니다. 서비스가 사용자에게 다음 정보를 제공합니다.
  
- 연결에 대한 내부 및 외부 연결에 대한 Exchange Server.
    
- 사용자의 사서함 서버 위치입니다.
    
- 사용 중 정보, 통합 메시징 및 오프라인 주소 책과 같은 Outlook 기능의 URL입니다.
    
- Outlook Anywhere 서버 설정
    
비즈니스용 Skype 서버와 자동 검색 서버를 통합하려면 먼저 자동 검색 서비스를 Exchange Server. Exchange Server 관리 셸에서 다음 명령을 실행하고 AutoDiscoverServiceInternalUri 속성의 값을 확인하여 자동 Exchange Server 서비스가 구성되어 있는지 여부를 확인할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

이 값이 비어 있는 경우 자동iscover 서비스에 URI를 할당해야 합니다. 일반적으로 이 URI는 다음과 유사합니다. https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
다음 명령을 실행하여 자동 배달 URI를 할당할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Autodiscover 서비스에 대한 자세한 내용은 [Autodiscover Service를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268542)
  
자동 검색 서비스를 구성한 후 비즈니스용 Skype 서버 OAuth 구성 설정을 수정해야 합니다. 그러면 비즈니스용 Skype 서버에서 자동 검색 서비스를 찾을 위치를 알 수 있습니다. 비즈니스용 Skype 서버에서 OAuth 구성 설정을 수정하려면 비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 실행합니다. 이 명령을 실행하는 경우 Exchange Server 실행 중인 자동 검색 서비스에 대한 URI를 지정하고 **autodiscover.svc를** 사용하여 서비스에서 사용하는 XML 파일을autodiscover.xml대신 서비스 위치를 지정해야 **합니다.**
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 위의 명령의 Identity 매개 변수는 선택 사항입니다. 이는 비즈니스용 Skype 서버에서 OAuth 구성 설정의 전역 컬렉션을 하나만 사용할 수 있기 때문에입니다. 무엇보다도 다음 명령을 사용하여 자동 확인 URL을 구성할 수 있습니다. 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> 기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용하는 표준 인증 프로토콜입니다. OAuth를 사용하는 경우 사용자 자격 증명 및 암호가 한 컴퓨터에서 다른 컴퓨터로 전달되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다. 
  
자동Iscover 서비스를 구성하는 것 외에, 사용자 서버를 지점으로 하는 서비스에 대한 DNS 레코드도 Exchange Server. 예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com 있는 경우 autodiscover.litwareinc.com 도메인의 Exchange Server 도메인 이름(예: atl-exchange-001.litwareinc.com)으로 확인되는 DNS 레코드를 만들어야 합니다.
  
비즈니스용 Skype 서버를 Exchange Online과 통합하는 경우 다음 단계는 프레미스 비즈니스용 Skype 서버와 비즈니스용 [Skype](../../deploy/integrate-with-exchange-server/outlook-web-app.md)서버 Outlook Web App 통합에 있습니다. 그렇지 않으면 비즈니스용 [Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)서버 통합을 Exchange Server.
  
## <a name="feature-support"></a>기능 지원
<a name="feature_support"> </a>

>[!Important]
> 아래에 나열된 서비스를 포함 하는 Exchange 통합은 더 이상 지원되지 않는 2021년 7월 31일 비즈니스용 Skype Online이 사용 중지됩니다.

다음 표에서는 Exchange 및 비즈니스용 Skype에 대해 다양한 온라인 또는 프레미스 조합에서 지원되는 기능에 대해 자세히 설명되어 있습니다.
  
||**Exchange 2016/2013/2010(프레미스) + 비즈니스용 Skype 서버(프레미스)**|**Exchange Online + 비즈니스용 Skype 서버(프레미스)**|**Exchange 2010(프레미스) + 비즈니스용 Skype Online**|**Exchange 2016/2013(프레미스) + 비즈니스용 Skype Online**|**Exchange Online + 비즈니스용 Skype Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook의 현재 상태  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 화상 통화를 통해 응답  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|현재 Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|OWA 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 화상 통화를 통해 응답  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|모임을 통해 온라인 모임 예약 및 Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|모바일 클라이언트의 IM/현재 상태  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|모바일 클라이언트에서 온라인 모임 참가  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 일정 약속이 있는/약속 있는 일정 정보를 기준으로 상태 게시  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|연락처 목록(통합 연락처 저장소를 통해)  <br/> |Y(Exchange 2016/2013 필요)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|고해상도 연락처 사진(최소한 Lync 2013 또는 비즈니스용 Skype 클라이언트 필요). LWA, 모바일 앱, Lync 2010, Mac용 Lync 및 기타 이전 클라이언트에는 지원되지 않습니다.  <br/> |Y(Exchange 2016/2013 필요)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|모임 위임  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange에 콘텐츠(IM 및 모임) 보관  <br/> |Y(Exchange 2016/2013 필요)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|보관된 콘텐츠 검색  <br/> |Y(Exchange 2016/2013 필요)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Exchange UM 음성 메일  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|서버 쪽 대화 기록  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 및 Lync Server 2013에 대해 지원되는 클라우드 음성메일 서비스가 있습니다.
> 

## <a name="see-also"></a>참고 항목
<a name="feature_support"> </a>

[비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[비즈니스용 Skype Online과 Exchange온-프레미스 간의 OAuth 구성](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[비즈니스용 Skype 서버와 비즈니스용 Skype Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013을 Lync Server 2013, 비즈니스용 Skype Online 또는 Lync Server 2013 하이브리드 배포와 통합하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[비즈니스용 Skype 서버 및 비즈니스용 Skype 서버에서 파트너 Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
