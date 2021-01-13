---
title: 비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '요약: 비즈니스용 Skype 서버와 비즈니스용 Skype Outlook Web App.'
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833968"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 Outlook Web App

**요약:** 비즈니스용 Skype 서버와 비즈니스용 Skype Outlook Web App.

비즈니스용 Skype 서버 배포를 사용하는 고객은 하이브리드 배포 모드에서 Microsoft Outlook Web App 서버와의 Microsoft Exchange Online 구성할 수 있습니다. 상호 운용성 기능에는 Outlook Web App 인터페이스와 통합된 Single Sign-On, 메신저, 현재 상태 등이 있습니다. 이 통합을 사용하도록 설정하려면 다음 작업을 완료하여 비즈니스용 Skype 서버 배포에서 에지 서버를 구성해야 합니다.

- 공유 SIP 주소 공간 구성

- 에지 서버에서 호스팅 공급자 구성

- 업데이트된 중앙 관리 저장소 복제 확인

## <a name="configure-a-shared-sip-address-space"></a>공유 SIP 주소 공간 구성

Exchange Online과 비즈니스용 Skype 서버를 통합하려면 공유 SIP 주소 공간을 구성해야 합니다. 동일한 SIP 도메인 주소 공간은 비즈니스용 Skype 서버와 Exchange Online 서비스에서 모두 지원됩니다.

비즈니스용 Skype 서버 관리 셸을 사용하여 다음 예에 표시된 매개 변수를 사용하여 **Set-CSAccessEdgeConfiguration** cmdlet을 실행하여 페더에 대한 에지 서버를 구성합니다.

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** 매개 변수는 내부 사용자가 페더레이션 도메인의 사용자와 통신하도록 허용되는지 여부를 지정합니다. 이 속성은 내부 사용자가 비즈니스용 Skype 서버 및 Exchange Online을 사용하여 공유 SIP 주소 공간 시나리오의 사용자와 통신할 수 있는지 여부도 결정됩니다.

비즈니스용 Skype 서버 관리 셸 사용에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>에지 서버에서 호스팅 공급자 구성

비즈니스용 Skype 서버 관리 셸을 사용하여 다음 예의 매개 변수를 사용하여 **New-CsHostingProvider** cmdlet을 실행하여 에지 서버에서 호스팅 공급자를 구성합니다.

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 중국의 21Vianet에서 운영하는 Microsoft 365 또는 Office 365를 사용하는 경우 이 예의 ProxyFqdn 매개 변수 값("exap.um.outlook.com")을 21Vianet에서 운영하는 서비스의 FQDN인 "exap.um.partner.outlook.cn"로 바랜다. Microsoft 365 또는 Office 365 GCC High를 사용하는 경우 이 예제의 ProxyFqdn 매개 변수 값("exap.um.outlook.com")을 GCC High에 대한 FQDN인 "exap.um.office365.us"로 바랜다.

- **ID는** 만들 호스팅 공급자의 고유 문자열 값 식별자(예: "Exchange Online")를 지정합니다. 공백이 포함된 값은 큰따옴표로 묶어야 합니다.

- **Enabled** 는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. True로 설정해야 합니다.

- **EnabledSharedAddressSpace** 는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다. True로 설정해야 합니다.

- **HostsOCSUsers는** 호스팅 공급자가 Office Communications Server 또는 비즈니스용 Skype 서버를 호스팅하는 데 사용되는지 여부를 나타냅니다. False로 설정해야 합니다.

- **ProxyFQDN** 은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다. Exchange Online의 경우 FQDN은 exap.um.outlook.com입니다.

- **IsLocal은** 호스팅 공급자가 사용하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지 내에 포함되어 있는지 여부를 나타냅니다. False로 설정해야 합니다.

- **VerificationLevel** 호스팅된 공급자와 보내고 보낸 메시지에 허용되는 확인 수준을 나타냅니다. 호스팅 공급자에서 보낸 메시지에 포함된 확인 수준에 따라 **UseSourceVerification을** 지정합니다. 이 수준을 지정하지 않으면 메시지가 확인되지 않는 것으로 거부됩니다.

## <a name="verify-replication-of-the-updated-central-management-store"></a>업데이트된 중앙 관리 저장소의 복제 확인

이전 섹션의 cmdlet을 사용하여 변경한 내용은 에지 서버에 자동으로 적용되며 일반적으로 복제하는 데 1분 미만이 걸릴 수 있습니다. 복제 상태의 유효성을 검사한 다음 다음 cmdlet을 사용하여 변경 내용이 에지 서버에 적용된 것을 확인할 수 있습니다.

복제 업데이트를 확인하기 위해 비즈니스용 Skype 서버 배포의 내부 서버에서 다음 cmdlet을 실행합니다.

```powershell
Get-CsManagementStoreReplicationStatus
```
UpToDate 값이 모든 복제본에 대해 TRUE를 표시하는지 검사합니다.

변경 내용이 적용된지 확인을 위해 에지 서버에서 다음 cmdlet을 실행합니다.

```powershell
Get-CsHostingProvider -LocalStore
```
표시된 정보가 이전 단계에서 커밋된 변경 내용과 일치하는지 다시 한 번 검사합니다.

## <a name="see-also"></a>참고 항목

[호스팅된 Exchange UM에서 비즈니스용 Skype 서버 사용자에게 음성 메일 제공](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[비즈니스용 Skype 서버에서 호스팅된 Exchange 통합 메시징 통합](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
