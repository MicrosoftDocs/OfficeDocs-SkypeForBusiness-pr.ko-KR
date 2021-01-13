---
title: 비즈니스용 Skype 서버 2015 및 2013에서 파트너 응용 프로그램 Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에 대한 서버 인증을 서버로 구성합니다.'
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834048"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>비즈니스용 Skype 서버 및 비즈니스용 Skype 서버에서 파트너 Exchange Server
 
**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에 대한 서버 인증을 서버로 구성합니다.
  
일반적으로 서버 대 서버 인증을 사용하려면 서로 통신해야 하는 서버 두 대와 타사 보안 토큰 서버가 필요합니다. 서버 A와 서버 B가 통신해야 하는 경우 이러한 두 서버 모두 일반적으로 토큰 서버에 연결하고 상호 트러스트된 보안 토큰을 얻는 것으로 시작됩니다. 그런 다음 서버 A는 해당 보안 토큰을 서버 B에 제시하고 그 반대의 경우도 마찬가지 방법으로 해당 보안 토큰을 서버 B에 제시하여 신뢰성과 신뢰성을 보장합니다.
  
그러나 이는 일반적인 규칙입니다. 비즈니스용 Skype 서버, Exchange Server 2016, Exchange Server 2013 및 SharePoint Server 2013에서는 통신할 때 타사 토큰 서버를 사용할 필요가 없습니다. 이는 이러한 서버 제품이 별도의 토큰 서버 없이도 다른 서버에서 수락할 수 있는 보안 토큰을 만들 수 있기 때문에입니다. (이 기능은 비즈니스용 Skype 서버, Exchange Server 2016, Exchange Server 2013 및 SharePoint Server 2013에서만 사용할 수 있습니다. 다른 Microsoft 서버 제품을 비롯한 다른 서버와의 서버 대 서버 인증을 설정해야 하는 경우 타사 토큰 서버를 사용하여 설정해야 합니다.
  
비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간에 서버 간 인증을 설정하려면 Exchange Server 다음 두 가지 작업을 해야 합니다. 1) 각 서버에 적절한 인증서를 할당해야 합니다. 그리고 2) 각 서버를 다른 서버의 파트너 응용 프로그램으로 구성해야 합니다. 즉, 비즈니스용 Skype 서버를 비즈니스용 Skype 서버의 파트너 응용 프로그램으로 Exchange Server 구성해야 Exchange Server 비즈니스용 Skype 서버의 파트너 응용 프로그램으로 구성해야 합니다.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>비즈니스용 Skype 서버를 비즈니스용 Skype 서버의 파트너 응용 프로그램으로 Exchange Server

비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013의 파트너 응용 프로그램으로 구성하는 가장 쉬운 방법은 비즈니스용 Skype와 함께 Configure-EnterprisePartnerApplication.ps1 스크립트인 Windows PowerShell 스크립트를 실행하는 Exchange Server. 이 스크립트를 실행하려면 비즈니스용 Skype 서버 인증 메타데이터 문서의 URL을 제공해야 합니다. 이 이름은 일반적으로 비즈니스용 Skype 서버 풀의 정식 도메인 이름 다음에 /metadata/json/1 접미사로 표시됩니다. 예제:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

비즈니스용 Skype 서버를 파트너 응용 프로그램으로 구성하기 위해 Exchange 관리 셸을 열고 이와 유사한 명령을 실행합니다(Exchange가 C 드라이브에 설치되어 있으며 기본 폴더 경로를 사용하는 경우).
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

파트너 응용 프로그램을 구성한 후 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS(인터넷 정보 서비스)를 중지했다가 다시 시작하는 것이 좋습니다. 다음과 같은 명령을 사용하여 IIS를 다시 시작할 수 있으며, 이 명령은 atl-exchange-001 컴퓨터에서 서비스를 다시 시작합니다.
  
```powershell
iisreset atl-exchange-001
```

이 명령은 Exchange 관리 셸 내에서 실행하거나 관리자 권한으로 실행된 다른 명령 창에서 실행할 수 있습니다.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>비즈니스용 skype Exchange Server 응용 프로그램으로 구성

비즈니스용 Skype 서버를 Exchange Server 2016 또는 Exchange Server 2013의 파트너 응용 프로그램으로 구성한 후 Exchange Server 비즈니스용 Skype 서버의 파트너 응용 프로그램으로 구성해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용하고 Exchange에 대한 인증 메타데이터 문서를 지정하면 됩니다. 일반적으로 Exchange 자동 검색 서비스의 URI 다음에 /metadata/json/1 접미사가 입니다. 예제:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

비즈니스용 Skype 서버에서 파트너 응용 프로그램은 [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet을 사용하여 구성됩니다. 메타데이터 URI를 지정하는 것 외에도 응용 프로그램 신뢰 수준을 Full로 설정해야 합니다. 이렇게 하면 Exchange에서 해당 사용자와 해당계의 권한이 부여된 사용자를 모두 표현할 수 있습니다. 예제:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

또는 비즈니스용 Skype 서버 서버-서버 인증 설명서에 있는 스크립트 코드를 복사하고 수정하여 파트너 응용 프로그램을 만들 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 문서의 [OAuth(서버](../../manage/authentication/server-to-server-and-partner-applications.md) 대 서버 인증) 및 파트너 응용 프로그램 관리 문서를 참조하세요.
  
비즈니스용 Skype 서버와 비즈니스용 Skype 서버 둘 다에 대해 파트너 Exchange Server 구성한 경우 두 제품 간에 서버 간 인증도 성공적으로 구성한 것입니다. 비즈니스용 Skype 서버에는 Windows PowerShell cmdlet인 [Test-CsExStorageConnectivity가](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) 포함되어 서버 간 인증이 올바르게 구성되고 비즈니스용 Skype 서버 저장소 서비스가 서버에 연결할 수 있는지 확인할 수 Exchange Server. 이 cmdlet은 Exchange Server 사용자의 사서함에 연결하고 해당 사용자의 대화 기록 폴더에 항목을 쓴 다음 해당 항목을 삭제(선택 사항)하여 이 파일을 삭제합니다.
  
비즈니스용 Skype 서버 및 서버 Exchange Server 테스트하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 실행합니다.
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

위의 명령에서 SipUri는 계정이 있는 사용자의 SIP 주소를 Exchange Server. 명령이 실패합니다. 이는 유효한 사용자 계정이 아니기 때문에 실패합니다.
  
> [!NOTE]
> 이 cmdlet에서 401 응답을 받는 경우 Exchange의 기본 구성에 Oauth 토큰 수락 지원이 포함되어 있지 않은 것일 수 있습니다. Exchange에서 Oauth를 사용하는 방법은 [SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=513103)및 비즈니스용 Skype 서버에서 OAuth 인증 구성을 참조하세요. 
  
테스트가 성공하고 연결이 설정된 후에는 통합 보관 및 통합 연락처 저장소와 같은 선택적인 기능을 구성할 수 있습니다.
