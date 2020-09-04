---
title: 비즈니스용 Skype 및 Exchange 통합 계획
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
description: '요약: Exchange Server 2016 또는 Exchange Server 2013에 비즈니스용 Skype 서버를 통합 하는 방법에 대 한 자세한 내용을 보려면이 항목을 검토 하십시오.'
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359264"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange 통합 계획
 
**요약:** 비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013와 통합 하는 방법에 대 한 자세한 내용은이 항목을 참조 하십시오.
  
비즈니스용 Skype 서버 및 Exchange Server를 통합 하려면 먼저 Exchange Server 및 비즈니스용 Skype 서버를 모두 설치 하 고 실행 중인지 확인 해야 합니다. 
  
Exchange Server 설치에 대 한 자세한 내용은 exchange Server 계획 및 배포 설명서를 참조 하십시오. 
   
서버를 가동 및 실행 한 후에는 비즈니스용 Skype 서버와 Exchange Server에 모두 서버 간 인증 인증서를 할당 해야 합니다. 이러한 인증서를 통해 비즈니스용 Skype 서버 및 Exchange 서버가 정보를 교환 하 고 서로 통신할 수 있습니다. Exchange Server를 설치 하면 Microsoft Exchange Server 인증 인증서 이름이 포함 된 자체 서명 된 인증서가 만들어집니다. 로컬 컴퓨터 인증서 저장소에서 찾을 수 있는이 인증서는 Exchange Server에서 서버 간 인증에 사용 해야 합니다. Exchange Server에서 인증서를 할당 하는 방법에 대 한 자세한 내용은 [Configure Mail Flow And Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540)을 참조 하십시오.
  
비즈니스용 Skype 서버에 대 한 기존 비즈니스용 Skype 서버 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 예를 들어 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. 비즈니스용 Skype 서버에서는 모든 웹 서버 인증서를 서버 간 인증을 위한 인증서로 사용할 수 있습니다.
  
- 인증서는 주체 필드에 SIP 도메인의 이름을 포함 합니다.
    
- 동일한 인증서가 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서로 구성 되어 있습니다.
    
- 인증서 길이가 최소 2048 비트입니다.
    
비즈니스용 Skype 서버에 대 한 서버 간 인증 인증서에 대 한 자세한 내용은 [비즈니스용 Skype 서버에](../../manage/authentication/assign-a-server-to-server-certificate.md)대 한 서버 간 인증 인증서 할당을 참조 하십시오.
  
인증서를 할당 한 후에는 Exchange Server에서 자동 검색 서비스를 구성 해야 합니다. Exchange Server에서 자동 검색 서비스는 사용자 프로필을 구성 하 고 사용자가 시스템에 로그온 할 때 Exchange 서비스에 대 한 액세스를 제공 합니다. 사용자는 전자 메일 주소와 암호를 사용 하 여 자동 검색 서비스를 제공 합니다. 그러면 서비스는 다음과 같은 정보를 사용자에 게 제공 합니다.
  
- Exchange Server에 대 한 내부 및 외부 연결에 대 한 연결 정보
    
- 사용자 사서함 서버의 위치입니다.
    
- 약속 있음/없음 정보, 통합 메시징 및 오프 라인 주소록 같은 Outlook 기능의 Url입니다.
    
- 외부에서 Outlook 사용 서버 설정
    
비즈니스용 Skype 서버 및 Exchange Server를 통합 하려면 자동 검색 서비스를 구성 해야 합니다. Exchange Server 관리 셸에서 다음 명령을 실행 하 고 AutoDiscoverServiceInternalUri 속성 값을 확인 하 여 자동 검색 서비스를 구성 했는지 여부를 확인할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

이 값이 비어 있으면 자동 검색 서비스에 URI를 할당 해야 합니다. 일반적으로이 URI는 다음과 같이 표시 됩니다. https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
다음과 같은 명령을 실행 하 여 자동 검색 URI를 할당할 수 있습니다.
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

자동 검색 서비스에 대 한 자세한 내용은 [자동 검색 서비스](https://go.microsoft.com/fwlink/p/?LinkId=268542)를 참조 하십시오.
  
자동 검색 서비스를 구성한 후에는 비즈니스용 Skype 서버 OAuth 구성 설정을 수정 해야 합니다. 이렇게 하면 비즈니스용 Skype 서버에서 자동 검색 서비스를 찾을 수 있는 위치를 알게 됩니다. 비즈니스용 Skype 서버에서 OAuth 구성 설정을 수정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다. 이 명령을 실행 하는 경우 Exchange Server에서 실행 되는 자동 검색 서비스에 대 한 URI를 지정 하 고 서비스에서 사용 하는 XML 파일을 가리키는 **autodiscover.xml** 대신 **자동 검색** 을 사용 하 여 서비스 위치를 가리키도록 해야 합니다.
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 위 명령에서 Identity 매개 변수는 선택 사항입니다. 비즈니스용 Skype 서버 에서만 OAuth 구성 설정의 단일 전역 컬렉션을 가질 수 있기 때문입니다. 즉, 다음과 같은 약간 간단한 명령을 사용 하 여 자동 검색 URL을 구성할 수 있습니다. 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> 이 기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용 되는 표준 인증 프로토콜입니다. OAuth를 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다. 
  
자동 검색 서비스를 구성 하는 것 외에도 Exchange 서버를 가리키는 서비스에 대 한 DNS 레코드도 만들어야 합니다. 예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com에 있는 경우 Exchange 서버의 정규화 된 도메인 이름 (예: atl-exchange-001.litwareinc.com)으로 확인 되는 autodiscover.litwareinc.com에 대 한 DNS 레코드를 만들어야 합니다.
  
비즈니스용 Skype 서버를 Exchange Online과 통합 하는 경우 다음 단계는 [온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간의 통합을 구성](../../deploy/integrate-with-exchange-server/outlook-web-app.md)합니다. 그렇지 않으면 [비즈니스용 Skype 서버와 Exchange server의 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)을 참조 하세요.
  
## <a name="feature-support"></a>기능 지원
<a name="feature_support"> </a>

>[!Important]
> 비즈니스용 Skype Online은 아래에 나열 된 Exchange 통합 (서비스 포함)이 더 이상 지원 되지 않는 경우 2021 년 7 월 31 일에 폐기 됩니다.

다음 표에서는 Exchange 및 비즈니스용 Skype에 대 한 다양 한 온라인 또는 온-프레미스 조합에서 지원 되는 기능에 대해 설명 합니다.
  
||**Exchange 2016/2013/2010 (온-프레미스) + 비즈니스용 Skype 서버 (온-프레미스)**|**Exchange Online + 비즈니스용 Skype 서버 (온-프레미스)**|**Exchange 2010 (온-프레미스) 및 비즈니스용 Skype Online**|**Exchange 2016/2013 (온-프레미스) 및 비즈니스용 Skype Online**|**Exchange Online + 비즈니스용 Skype Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook에서 현재 상태  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 비디오 통화를 통해 응답  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook을 통해 온라인 모임 예약 및 참가  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook Web App에서 현재 상태  <br/> |피지  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|OWA 전자 메일에서 IM, PSTN 통화, Skype 통화 또는 비디오 통화를 통해 응답  <br/> |피지  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|Outlook Web App을 통해 온라인 모임 예약 및 참가  <br/> |피지  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|모바일 클라이언트의 IM/현재 상태  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|모바일 클라이언트에서 온라인 모임 참가  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|연락처 목록 (통합 연락처 저장소를 통해)  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|고해상도 연락처 사진 (Lync 2013 또는 비즈니스용 Skype 클라이언트는 최소한 필요 합니다. LWA, 모바일 앱, Lync 2010, Lync for Mac 및 기타 이전 클라이언트에 대해서는 지원 되지 않습니다.  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |N  <br/> |피지  <br/> |피지  <br/> |
|모임 위임  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |피지  <br/> |
|Exchange의 콘텐츠 (IM 및 모임) 보관  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|보관 된 콘텐츠 검색  <br/> |Y (Exchange 2016/2013 필요)  <br/> |피지  <br/> |N  <br/> |N  <br/> |피지  <br/> |
|Exchange UM 음성 메일  <br/> |피지  <br/> |피지  <br/> |N  <br/> |N  <br/> |N  <br/> |
|서버 쪽 대화 기록  <br/> |피지  <br/> |피지  <br/> |N  <br/> |피지  <br/> |피지  <br/> |

> [!NOTE]
> 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 및 Lync Server 2013에 대해 지원 되는 클라우드 음성 메일 서비스가 있습니다.
> 

## <a name="see-also"></a>참고 항목
<a name="feature_support"> </a>

[온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[비즈니스용 Skype Online 및 온-프레미스 간 OAuth 구성](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Exchange Server와 비즈니스용 Skype 서버 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013을 Lync Server 2013, 비즈니스용 Skype Online 또는 Lync Server 2013 하이브리드 배포와 통합 하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[비즈니스용 Skype 서버 및 Microsoft Exchange Server에서 파트너 응용 프로그램 구성](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
