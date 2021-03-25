---
title: 클라우드 음성메일 서비스 구성
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버에 있는 사용자에 대해 클라우드 기반 음성메일을 구현하기 위한 지침입니다.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118987"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>클라우드 음성메일 서비스 구성

## <a name="overview"></a>개요 
이 문서에서는 비즈니스용 Skype의 사내 사용자에 대해 Microsoft Cloud Voicemail 서비스를 구성하는 방법을 설명합니다.  

이 문서에서는 지원되는 토폴로지에서 비즈니스용 Skype 서버가 이미 배포되어 있으며 하이브리드 연결 설정에 대한 선행 방법을 충족했다고 가정합니다.

클라우드 음성메일 구현을 위한 이점, 계획 고려 사항 및 요구 사항에 대한 자세한 내용은 [Plan Cloud Voicemail service을 참조하십시오.](plan-cloud-voicemail.md)




클라우드 음성메일 구성에는 다음 작업이 수행됩니다.

1.  [Plan Cloud Voicemail service](plan-cloud-voicemail.md)에 설명된 선행 조문을 충족해야 합니다.

2.  하이브리드 연결 계획 및 하이브리드 연결 [](plan-hybrid-connectivity.md) 구성에 설명된 바와 같이 하이브리드 [연결을 설정해야 합니다.](configure-hybrid-connectivity.md) 

3.  이 문서에 설명된 바와 같이 프런트 엔드 서버에서 호스팅 공급자로 Cloud [Voicemail을](#configure-cloud-voicemail-as-the-hosting-provider) 구성합니다.

4.  [이 문서에 설명된](#configure-a-hosted-voicemail-policy) 바와 같이 호스팅된 음성메일 정책을 구성합니다.

5.  [이 문서에 설명된](#assign-a-hosted-voicemail-policy) 바와 같이 호스팅된 음성메일 정책을 할당합니다.

6.  [이 문서에 설명된](#enable-a-user-for-cloud-voicemail) 바와 같이 사용자가 클라우드 음성메일을 사용할 수 있도록 합니다.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>호스팅 공급자로 Cloud Voicemail 구성 

다음 매개 변수와 함께 New-CsHostingProvider 사용하여 Cloud Voicemail을 프런트 엔드 서버에서 호스팅 공급자로 구성합니다.

- **Identity는** 만들 호스팅 공급자의 고유 문자열 값 식별자를 지정합니다. 예를 들어 Cloud Voicemail과 같습니다. 

- **Enabled** 는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 매개 변수는 True로 설정해야 합니다.

- **EnabledSharedAddressSpace** 는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다. 이 매개 변수는 True로 설정해야 합니다.

- **HostsOCSUsers는** 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스팅하는 데 사용되는지 여부를 나타냅니다. 이 매개 변수는 False로 설정해야 합니다.

- **ProxyFQDN은** 호스팅 공급자가 사용하는 프록시 서버의 FQDN(FQDN)을 지정합니다. 예를 들어 proxyserver.contoso.com. 이 정보는 호스팅 공급자에게 문의하십시오. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.

- **IsLocal은** 호스팅 공급자가 사용하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지 내에 포함되어 있는지 여부를 나타냅니다. 이 매개 변수는 False로 설정해야 합니다.

예를 들어 비즈니스용 Skype 관리 셸에서 다음 cmdlet은 Cloud Voicemail을 호스팅 공급자로 구성합니다.


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>호스팅된 음성메일 정책 구성

조직의 음성메일이 클라우드 음성메일 서비스로 라우팅되도록 조직에 대해 호스팅된 음성메일 정책을 구성해야 합니다. 대부분의 경우 호스팅된 음성메일 정책은 하나만 필요하며 모든 요구 사항을 충족하도록 글로벌 정책을 수정할 수 있습니다. 조직에 호스팅된 음성메일 정책이 여러 개 필요한 경우 new-cshostedvoicemailpolicy cmdlet을 사용하여 정책을 추가할 수 있습니다.

글로벌 정책을 수정하려면 조직 및 TenantID를 업데이트한 후 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행합니다.

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination은** 호스팅된 클라우드 음성메일 서비스의 FQDN(FQDN)을 지정합니다. 이 값은 를 로 **exap.um.outlook.com.**

- **조직은** 테넌트에 할당된 기본 도메인입니다. 테넌트 관리자가 로그인하여 관리 센터 앱을 office.com 왼쪽의 설치로 이동한 다음  도메인 을 클릭하여 이 정보를 검색할 **수 있습니다.** 예: mytenant.onmicrosoft.com.

    조직 이름은 Microsoft 365 또는 Office 365의 기본 도메인 이름입니다.

호스팅된 음성메일 정책이 만들어지기 위해 다음 명령을 실행합니다.

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>호스팅된 음성메일 정책 할당

기본적으로 전역 호스팅된 음성메일 정책은 모든 사용자에게 할당됩니다. 다른 정책을 사용하는 경우 호스팅된 음성메일에 대해 사용자를 사용하도록 설정하기 전에 [먼저 Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet을 사용하여 사용자에게 원하는 호스팅된 음성메일 정책을 부여해야 합니다.

예를 들어 다음 명령은 전역이 아닌 호스팅된 음성메일 정책을 사용자에게 할당합니다.


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>사용자가 클라우드 음성메일을 사용할 수 있도록 설정

사용자의 음성메일 통화가 클라우드 음성메일로 라우팅될 수 있도록 설정하려면 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet을 HostedVoiceMail 매개 변수와 함께 사용합니다. 

예를 들어 다음 명령은 클라우드 음성메일에 대해 사용자 계정을 사용할 수 있도록 합니다. 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

이 cmdlet은 전역, 사이트 또는 사용자 수준에서 Cloud Voicemail 정책이 이 사용자에게 적용되는지 검증합니다. 정책을 적용하지 않을 경우 cmdlet이 실패합니다.  

다음 예에서는 Cloud Voicemail에 대한 사용자 계정을 사용하지 않도록 설정합니다.

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

이 cmdlet은 전역, 사이트 또는 사용자 수준에서 호스팅된 음성메일 정책이 이 사용자에게 적용되는 것이 없는지 확인할 수 있습니다. 정책이 적용될 경우 cmdlet이 실패합니다.

> [!NOTE]
>  Microsoft Cloud Voicemail 서비스를 사용하려면 사용자가 엔터프라이즈 음성을 사용할 수 있어야 합니다.