---
title: 2015 및 비즈니스용 Skype 서버 파트너 응용 프로그램 Exchange Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 2013에 대해 서버 인증을 서버 비즈니스용 Skype 서버.'
ms.openlocfilehash: d7a3b99536524df5422521cdaf45a7e4dac911b3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387216"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>파트너 응용 프로그램을 비즈니스용 Skype 서버 Exchange Server
 
**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 2013에 대해 서버 인증을 비즈니스용 Skype 서버.
  
서버 대 서버 인증을 사용하려면 일반적으로 서로 통신해야 하는 서버 두 대와 타사 보안 토큰 서버가 필요합니다. 서버 A와 서버 B가 통신해야 하는 경우 이러한 두 서버 모두 일반적으로 토큰 서버에 연결하고 상호 신뢰할 수 있는 보안 토큰을 획득하는 것으로 시작됩니다. 그런 다음 서버 A는 해당 보안 토큰을 서버 B에 제시하고 그 반대의 경우도 마찬가지입니다.
  
그러나 이는 일반적인 규칙입니다. 비즈니스용 Skype 서버, Exchange Server 2016, Exchange Server 2013 및 SharePoint Server 2013은 통신할 때 타사 토큰 서버를 사용할 필요가 없습니다. 이러한 서버 제품은 별도의 토큰 없이도 다른 사용자가 수락할 수 있는 보안 토큰을 만들 수 있기 때문에  server. 이 기능은 비즈니스용 Skype 서버, Exchange Server, Exchange Server 2013 및 SharePoint Server 2013에서만 사용할 수 있습니다. 다른 Microsoft 서버 제품을 비롯한 다른 서버와의 서버 대 서버 인증을 설정해야 하는 경우 타사 토큰 서버를 사용하여 설정해야 합니다.
  
비즈니스용 Skype 서버 및 Exchange Server 간에 서버 간 인증을 설정하려면 1) 각 서버에 적절한 인증서를 할당해야 합니다. 그리고 2) 각 서버를 다른 서버의 파트너 응용 프로그램으로 구성해야 합니다. 즉, 서버 간 인증을 구성해야 비즈니스용 Skype 서버  를 설치하기 위한 파트너 Exchange Server 및 Exchange Server 응용 프로그램으로 구성해야 비즈니스용 Skype 서버.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>비즈니스 비즈니스용 Skype 서버 응용 프로그램으로 구성 Exchange Server

비즈니스용 Skype 서버 2016 또는 Exchange Server Exchange Server 2013이 있는 파트너 응용 프로그램으로 구성하는 가장 쉬운 방법은 Configure-EnterprisePartnerApplication.ps1 스크립트와 함께 Windows PowerShell 스크립트를 실행하는 Exchange Server. 이 스크립트를 실행하려면 비즈니스용 Skype 서버 인증 메타데이터 문서의 URL을 제공해야 합니다. 이 URL은 일반적으로 비즈니스용 Skype 서버 풀의 정식 도메인 이름 다음에 /metadata/json/1 접미사로 표시됩니다. 예제:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

비즈니스용 Skype 서버 응용 프로그램으로 구성하기 위해 Exchange 관리 셸을 열고 이와 유사한 명령을 실행합니다(Exchange C 드라이브에 설치되고 기본 폴더 경로를 사용하는 경우).
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

파트너 응용 프로그램을 구성한 후 사서함 및 클라이언트 액세스 서버에서 IIS(인터넷 정보 서비스)를 Exchange 다시 시작하는 것이 좋습니다. 다음과 같은 명령을 사용하여 IIS를 다시 시작할 수 있으며, 이 명령은 atl-exchange-001 컴퓨터에서 서비스를 다시 시작합니다.
  
```powershell
iisreset atl-exchange-001
```

이 명령은 관리 셸의 Exchange 관리자 권한으로 실행되는 다른 명령 창에서 실행할 수 있습니다.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>웹 Exchange Server 파트너 응용 프로그램으로 구성 비즈니스용 Skype 서버

비즈니스용 Skype 서버 2016 또는 Exchange Server Exchange Server 2013의 파트너 응용 프로그램으로 구성한 후 Exchange Server 응용 프로그램을 파트너 응용 프로그램으로 구성해야 비즈니스용 Skype 서버. 비즈니스용 Skype 서버 관리 셸을 사용하고 Exchange 인증 메타데이터 문서를 지정하면 됩니다. 이 작업은 일반적으로 Exchange 자동 검색 서비스의 URI 다음에 /metadata/json/1 접미사로 사용됩니다. 예제:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

이 비즈니스용 Skype 서버 파트너 응용 프로그램은 [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet을 사용하여 구성됩니다. 메타데이터 URI를 지정하는 것 외에도 응용 프로그램 신뢰 수준을 전체로 설정해야 합니다. 이렇게 하면 Exchange 모든 권한이 부여된 사용자를 모두 나타내는 데 사용할 수 있습니다. 예제:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

또는 서버 대 서버 인증 설명서에서 찾은 스크립트 코드를 복사하고 수정하여 비즈니스용 Skype 서버 응용 프로그램을 만들 수 있습니다. 자세한 내용은 [Manage server-to-server authentication (OAuth) and partner applications in 비즈니스용 Skype 서버](../../manage/authentication/server-to-server-and-partner-applications.md) 참조하십시오.
  
비즈니스용 Skype 서버 및 Exchange Server 둘 다에 대해 파트너 응용 프로그램을 성공적으로 구성한 경우 두 제품 간에 서버 간 인증도 성공적으로 구성한 것입니다. 비즈니스용 Skype 서버 서버 간 인증이 올바르게 구성되고 비즈니스용 Skype 서버 Storage 서비스에 연결할 수 있는지 확인할 수 있는 Windows PowerShell [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) cmdlet이 포함되어 있습니다. Exchange Server. 이 cmdlet은 Exchange Server 사용자의 사서함에 연결하고 해당 사용자의 대화 기록 폴더에 항목을 작성한 다음(선택적으로) 해당 항목을 삭제하여 이 파일을 삭제합니다.
  
비즈니스용 Skype 서버 및 Exchange Server 통합을 테스트하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음과 비즈니스용 Skype 서버 실행합니다.
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

위의 명령에서 SipUri는 계정이 Exchange Server 사용자의 SIP 주소를 나타내며, 이 경우 명령이 실패합니다. 유효한 사용자 계정이 없습니다.
  
> [!NOTE]
> 이 cmdlet에서 401 응답을 받는 경우 이 cmdlet에 대한 기본 구성에 Oauth Exchange 지원이 포함되어 있지 않을 수 있습니다. 2013에서 Oauth를 사용하는 Exchange [Configure OAuth authentication with SharePoint 2013 및](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help) 비즈니스용 Skype 서버. 
  
테스트가 성공하고 연결이 설정된 후에는 통합 보관 및 통합 연락처 저장소와 같은 선택적인 기능을 구성할 수 있습니다.