---
title: 온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 구성
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버에 있는 사용자에 대해 클라우드 기반 음성 메일을 구현 하기 위한 지침입니다.
ms.openlocfilehash: e3b18f8048f8779eac322dece88e5919b2aa7a96
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963006"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>온-프레미스 사용자를 위한 클라우드 음성 메일 서비스 구성

## <a name="overview"></a>개요 
이 문서에서는 비즈니스용 Skype 온-프레미스 사용자에 대해 Microsoft 클라우드 음성 메일 서비스를 구성 하는 방법을 설명 합니다.  

이 문서에서는 이미 지원 되는 토폴로지에서 비즈니스용 Skype 서버를 배포 했으며 하이브리드 연결을 설정 하기 위한 필수 구성 요소를 충족 했다고 가정 합니다.

클라우드 음성 메일을 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대 한 자세한 내용은 [클라우드 음성 메일 서비스 계획](plan-cloud-voicemail.md)을 참조 하세요.




클라우드 음성 메일을 구성 하려면 다음 작업을 수행 해야 합니다.

1.  [Plan Cloud 음성 메일 서비스](plan-cloud-voicemail.md)에 설명 된 대로 필수 구성 요소를 충족 하는지 확인 합니다.

2.  [하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [하이브리드 연결 구성](configure-hybrid-connectivity.md)에 설명 된 대로 하이브리드 연결을 설정 했는지 확인 합니다. 

3.  이 문서에 설명 된 대로 [,에 지 서버에서 호스팅 공급자로 클라우드 음성 메일을 구성](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) 합니다.

4.  이 문서에 설명 [된 대로 호스팅된 음성 메일 정책을 구성](#configure-a-hosted-voicemail-policy) 합니다.

5.  이 문서에 설명 [된 대로 호스팅된 음성 메일 정책을 할당](#assign-a-hosted-voicemail-policy) 합니다.

6.  이 문서에 설명 된 대로 [클라우드 음성 사서함에 대해 사용자를 사용 하도록 설정](#enable-a-user-for-cloud-voicemail) 합니다.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>에 지 서버에서 호스팅 공급자로 클라우드 음성 메일 구성 

다음 매개 변수를 사용 하 여 새-CsHostingProvider cmdlet을 통해 프런트 엔드 서버의 호스팅 공급자로 클라우드 음성 메일을 구성 합니다.

- **Identity** 는 만들려는 호스팅 공급자에 대 한 고유 문자열 값 식별자를 지정 합니다. 예를 들어 클라우드 음성 메일 

- **Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 매개 변수는 True로 설정 해야 합니다.

- **EnabledSharedAddressSpace**는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다. 이 매개 변수는 True로 설정 해야 합니다.

- **HostsOCSUsers** 은 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스트 하는 데 사용 되는지 여부를 나타냅니다. 이 매개 변수는 False로 설정 해야 합니다.

- **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 예: proxyserver.contoso.com. 이 정보는 호스팅 공급자에게 문의하십시오. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경 하는 경우 해당 공급자에 대 한 항목을 삭제 한 다음 다시 만들어야 합니다.

- **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다. 이 매개 변수는 False로 설정 해야 합니다.

예를 들어 비즈니스용 Skype 관리 셸에서 다음 cmdlet은 호스팅 공급자로 클라우드 음성 메일을 구성 합니다.


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>호스팅된 음성 메일 정책 구성

조직의 음성 메일이 클라우드 음성 메일 서비스로 라우팅되도록 하려면 조직에 대해 호스팅된 음성 메일 정책을 구성 해야 합니다. 대부분의 경우 호스팅된 음성 메일 정책은 하나만 필요 하며, 모든 요구 사항을 충족 하도록 글로벌 정책을 수정할 수 있습니다. 조직에서 호스팅된 음성 메일 정책이 여러 개 필요한 경우 set-cshostedvoicemailpolicy cmdlet을 사용 하 여 정책을 추가할 수 있습니다.

전역 정책을 수정 하려면 조직 및 TenantID를 업데이트 한 후 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- **대상** 호스트 된 클라우드 음성 메일 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다. 이 값은 **exap.um.outlook.com**로 설정 해야 합니다.

- **조직** 은 테 넌 트에 할당 된 기본 도메인입니다. 테 넌 트 관리자 로그인을 통해 office.com에이 정보를 검색할 수 있으며, 관리 센터 앱을 클릭 하 고, 왼쪽의 **설정** 으로 이동한 후 **도메인**을 클릭 합니다. 예: mytenant.onmicrosoft.com.

    조직 이름은 Office 365의 기본 도메인 이름 이기도 합니다.

- **테 넌 트** 는 Office 365에서 테 넌 트를 식별 하는 데 사용 됩니다. 자세한 내용은 [Office 365 테 넌 트 ID 찾기를](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)참조 하세요.

호스팅된 음성 메일 정책이 제대로 만들어졌는지 확인 하려면 다음 명령을 실행 합니다.

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>호스팅된 음성 메일 정책 할당

기본적으로는 글로벌 호스팅된 음성 메일 정책이 모든 사용자에 게 할당 됩니다. 다른 정책을 사용 하는 경우에는 사용자가 호스팅된 음성 메일을 사용 하도록 설정 하기 전에 먼저 [set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet을 사용 하 여 원하는 호스팅된 음성 메일 정책을 사용자에 게 부여 해야 합니다.

예를 들어 다음 명령은 비전역로 호스팅된 음성 메일 정책을 사용자에 게 할당 합니다.


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>사용자가 클라우드 음성 메일을 사용할 수 있도록 설정

사용자의 음성 메일 통화를 클라우드 음성 메일로 라우팅되도록 설정 하려면 HostedVoiceMail 매개 변수와 함께 [csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet을 사용 합니다. 

예를 들어 다음 명령은 클라우드 음성 메일에 대해 사용자 계정을 사용 하도록 설정 합니다. 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

이 cmdlet은 전역, 사이트 또는 사용자 수준에서 클라우드 음성 메일 정책이이 사용자에 게 적용 되는지 확인 합니다. 정책이 적용 되지 않으면 cmdlet이 실패 합니다.  

다음은 클라우드 음성 메일에 대 한 사용자 계정을 사용 하지 않도록 설정 하는 예입니다.

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

이 cmdlet은 전역, 사이트 또는 사용자 수준에서 호스팅된 음성 메일 정책 (이 사용자에 게 적용 됨)이 없는지 확인 합니다. 정책이 적용 되 면 cmdlet이 실패 합니다.

> [!NOTE]
>  Microsoft 클라우드 음성 메일 서비스를 사용 하려면 사용자가 enterprise voice를 사용 하도록 설정 되어 있어야 합니다.
