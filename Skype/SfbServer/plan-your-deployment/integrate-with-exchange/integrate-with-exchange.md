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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '요약: 비즈니스용 Skype 서버 2016 또는 Exchange Server 2013과 통합하는 방법에 대한 자세한 내용은 이 Exchange Server 검토합니다.'
ms.openlocfilehash: f2650e8a18767e70ab98e8763e9ec2863e99df90
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012562"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange 통합 계획
 
**요약:** 비즈니스용 Skype 서버 2016 또는 Exchange Server 2013과 통합하는 방법에 대한 자세한 내용은 이 Exchange Server 검토하세요.
  
비즈니스용 Skype 서버 및 Exchange Server 통합하려면 Exchange Server 및 비즈니스용 Skype 서버 모두 설치 및 실행해야 합니다. 
  
설치에 대한 자세한 Exchange Server 버전에 대한 Exchange Server 계획 및 배포 설명서를 Exchange. 
   
서버가 실행되고 나면 서버 대 서버 인증 인증서를 서버와 서버 비즈니스용 Skype 서버 Exchange Server. 이러한 인증서를 비즈니스용 Skype 서버 Exchange Server 정보를 교환하고 서로 통신할 수 있습니다. 인증서를 Exchange Server 인증 인증서 이름과 Microsoft Exchange Server 자체 서명된 인증서가 만들어집니다. 로컬 컴퓨터 인증서 저장소에서 찾을 수 있는 이 인증서는 로컬 컴퓨터 인증서 저장소의 서버 대 서버 인증에 Exchange Server. 클라이언트에서 인증서를 할당하는 Exchange Server Configure Mail [Flow and Client Access을 참조합니다.](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)
  
이 비즈니스용 Skype 서버 기존 비즈니스용 Skype 서버 인증서를 서버 대 서버 인증 인증서로 사용할 수 있습니다. 예를 들어 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. 비즈니스용 Skype 서버 웹 서버 인증서를 다음에 제공된 서버 대 서버 인증에 대한 인증서로 사용할 수 있습니다.
  
- 인증서에는 주체 필드의 SIP 도메인 이름이 포함됩니다.
    
- 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서와 동일한 인증서가 구성됩니다.
    
- 인증서의 길이는 2048비트 이상입니다.
    
서버 대 서버 인증 인증서에 대한 자세한 비즈니스용 Skype 서버 에 서버 대 서버 인증 인증서 [할당을 비즈니스용 Skype 서버.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
인증서가 할당된 후 해당 인증서에서 자동 Exchange Server. 자동 Exchange Server 서비스에서 사용자 프로필을 구성하고 사용자가 시스템에 로그온할 때 Exchange 서비스에 대한 액세스를 제공합니다. 사용자는 전자 메일 주소와 암호를 사용하여 자동검버 서비스를 제공합니다. 서비스가 사용자에게 다음 정보를 제공합니다.
  
- 연결에 대한 내부 및 외부 연결에 대한 Exchange Server.
    
- 사용자의 사서함 서버 위치입니다.
    
- 무료/Outlook, 통합 메시징 및 오프라인 주소 Outlook 같은 기능의 URL입니다.
    
- Outlook Anywhere 서버 설정.
    
자동iscover 서비스를 구성해야 자동 비즈니스용 Skype 서버 통합할 Exchange Server. Exchange Server 관리 셸에서 다음 명령을 실행하고 AutoDiscoverServiceInternalUri 속성 값을 확인하여 자동 Exchange Server 서비스가 구성되어 있는지 여부를 확인할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

이 값이 비어 있는 경우 자동iscover 서비스에 URI를 할당해야 합니다. 일반적으로 이 URI는 다음과 유사합니다. https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
다음 명령을 실행하여 자동검사 URI를 할당할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Autodiscover 서비스에 대한 자세한 내용은 [Autodiscover Service 를 참조합니다.](/Exchange/architecture/client-access/autodiscover)
  
Autodiscover 서비스를 구성한 후 OAuth 구성 설정을 수정해야 비즈니스용 Skype 서버 합니다. 이렇게 하면 비즈니스용 Skype 서버 검색 서비스를 찾을 위치를 알 수 있습니다. 셸에서 OAuth 구성 설정을 비즈니스용 Skype 서버 관리 셸 내에서 다음 비즈니스용 Skype 서버 실행합니다. 이 명령을 실행하는 경우 Exchange Server 실행 중인 자동 검색 서비스에 대한 URI를 지정하고 **autodiscover.svc를** 사용하여 서비스 위치를 지정하는 대신 autodiscover.xml(서비스에서 사용하는 XML 파일을autodiscover.xml)를 지정해야 합니다.
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 이전 명령의 Identity 매개 변수는 선택 사항입니다. 이는 OAuth 비즈니스용 Skype 서버 컬렉션을 하나만 사용할 수 있기 때문에입니다. 특히, 이 명령은 약간 더 간단한 명령을 사용하여 자동검사 URL을 구성할 수 있습니다. 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> 기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용하는 표준 인증 프로토콜입니다. OAuth를 사용하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다. 
  
자동iscover 서비스를 구성하는 것 외에, 사용자 서버를 지점으로 하는 서비스에 대한 DNS 레코드도 만들어야 Exchange Server. 예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com 경우 autodiscover.litwareinc.com 도메인 이름(예: Exchange Server)으로 확인되는 dns 레코드를 만들어야 atl-exchange-001.litwareinc.com.
  
비즈니스용 Skype 서버 통합하는 Exchange Online 다음 단계는 [Configure integration between on-premises 비즈니스용 Skype 서버 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)에 있습니다. 그렇지 않으면 Integration 비즈니스용 Skype 서버 with을 참조하세요. [ Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>기능 지원
<a name="feature_support"> </a>

>[!Important]
> 비즈니스용 Skype 서비스가 포함된 아래에 나열된 Exchange 통합이 더 이상 지원되지 않는 2021년 7월 31일 온라인이 사용 중지됩니다.

다음 표에서는 여러 온라인 또는 온라인 및 온라인 프레미스를 조합하여 지원되는 기능을 Exchange 비즈니스용 Skype.
  
|&nbsp;|Exchange 2016/2013/2010(사내) + 비즈니스용 Skype 서버(사내)|Exchange Online + 비즈니스용 Skype 서버(비즈니스용 Skype 서버)**|**Exchange 2010(사내) + 비즈니스용 Skype Online|Exchange 2016/2013(사내) + 비즈니스용 Skype Online**|**Exchange Online + 비즈니스용 Skype Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|현재 Outlook   |Y   |Y   |Y   |Y   |Y   |
|IM, PSTN 통화, Skype 전자 메일에서 통화 또는 화상 통화를 Outlook 응답   |Y   |Y   |Y   |Y   |Y   |
|일정을 통해 온라인 모임 예약 및 Outlook   |Y   |Y   |Y   |Y   |Y   |
|현재 Outlook Web App   |Y   |Y   |N   |N   |Y   |
|IM, PSTN 통화, OWA Skype 통화 또는 화상 통화를 통해 응답   |Y   |Y   |N   |N   |Y   |
|모임을 통해 온라인 모임 예약 및 Outlook Web App   |Y   |Y   |N   |N   |Y   |
|모바일 클라이언트의 IM/현재 상태   |Y   |Y   |Y   |Y   |Y   |
|모바일 클라이언트에서 온라인 모임에 참가   |Y   |Y   |Y   |Y   |Y   |
|약속이 있는 약속 Outlook 정보를 기반으로 상태 게시   |Y   |Y   |Y   |Y   |Y   |
|연락처 목록(통합 연락처 저장소를 통해)   |Y(Exchange 2016/2013 필요)   |Y   |N   |N   |Y   |
|고해상도 연락처 사진(최소한 Lync 2013 또는 비즈니스용 Skype 클라이언트 필요). LWA, 모바일 앱, Lync 2010, Mac용 Lync 및 기타 이전 클라이언트에서는 지원되지 않습니다.   |Y(Exchange 2016/2013 필요)   |Y   |N   |Y   |Y   |
|모임 위임   |Y   |Y   |Y   |Y   |Y   |
|부재 중 대화 기록 및 통화 로그가 사용자의 Exchange 사서함에 기록됩니다.   |Y   |Y   |Y   |Y   |Y   |
|IM 및 모임의 콘텐츠 보관 Exchange   |Y(Exchange 2016/2013 필요)   |Y   |N   |N   |Y   |
|보관된 콘텐츠 검색   |Y(Exchange 2016/2013 필요)   |Y   |N   |N   |Y   |
|Exchange UM 음성 메일   |Y   |Y   |N   |N   |N   |
|서버 쪽 대화 기록   |Y   |Y   |N   |Y   |Y   |

> [!NOTE]
> 클라우드 음성 사서함 Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 및 Lync Server 2013에 대해 비즈니스용 Skype 지원되는 비즈니스용 Skype 서버 서비스가 있습니다.
> 

## <a name="see-also"></a>참고 항목
<a name="feature_support"> </a>

[프레미스 서버와 비즈니스용 Skype 서버 통합 Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[비즈니스용 Skype Online과 Exchange OAuth 구성](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[통합 비즈니스용 Skype 서버 통합 Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server Lync Server 2013, 비즈니스용 Skype Online 또는 Lync Server 2013 하이브리드 배포와 통합하는 방법](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[파트너 응용 프로그램을 비즈니스용 Skype 서버 Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)