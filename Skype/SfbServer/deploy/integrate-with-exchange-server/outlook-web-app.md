---
title: 온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버와 Outlook Web App을 통합 합니다.'
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797039"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성

**요약:** 비즈니스용 Skype 서버와 Outlook Web App을 통합 합니다.

온-프레미스 비즈니스용 Skype Server 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App을 통해 상호 운용성을 구성할 수 있습니다. 상호 운용성 기능에는 Outlook Web App 인터페이스와의 단일 사인온 및 인스턴트 메시징 (IM) 및 현재 상태 통합이 포함 됩니다. 이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 비즈니스용 Skype 서버 배포에서 Edge 서버를 구성 해야 합니다.

- 공유 SIP 주소 공간 구성

- Edge 서버에서 호스팅 공급자 구성

- 업데이트 된 중앙 관리 저장소의 복제 확인

## <a name="configure-a-shared-sip-address-space"></a>공유 SIP 주소 공간 구성

Exchange Online을 사용 하 여 온-프레미스 비즈니스용 Skype 서버를 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다. 동일한 SIP 도메인 주소 공간은 비즈니스용 Skype 서버와 Exchange Online 서비스에서 모두 지원 됩니다.

비즈니스용 Skype Server Management Shell을 사용 하 여 다음 예제에 표시 된 매개 변수를 사용 하 여 **Set-CSAccessEdgeConfiguration** cmdlet을 실행 하 여 페더레이션의 Edge 서버를 구성 합니다.

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** 매개 변수 내부 사용자가 페더레이션 도메인의 사용자와 통신할 수 있는지 여부를 지정 합니다. 또한이 속성은 내부 사용자가 비즈니스용 Skype 서버 및 Exchange Online의 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.

비즈니스용 Skype 서버 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype Server Management shell](../../manage/management-shell.md)을 참조 하세요.

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Edge 서버에서 호스팅 공급자 구성

비즈니스용 Skype Server Management Shell을 사용 하 여 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 하 여 Edge 서버에서 호스팅 공급자를 구성 합니다.

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 중국에서 21Vianet에서 운영 하는 Office 365를 사용 하는 경우이 예제 ("exap.um.outlook.com")의 ProxyFqdn 매개 변수 값을 21Vianet이 운영 하는 서비스의 FQDN으로 바꿉니다. "exap.um.partner.outlook.cn". Office 365 GCC High를 사용 하는 경우이 예제 ("exap.um.outlook.com")의 ProxyFqdn 매개 변수 값을 GCC High ("exap.um.office365.us")의 FQDN으로 바꿉니다.

- **Id** 는 만들려는 호스팅 공급자에 대 한 고유한 문자열 값 식별자를 지정 합니다 (예: "Exchange Online"). 공백이 포함 된 값은 큰따옴표로 묶어야 합니다.

- **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이를 True로 설정 해야 합니다.

- **EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간 시나리오에 사용 되는지 여부를 나타냅니다. 이를 True로 설정 해야 합니다.

- **HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Office Communications Server 또는 비즈니스용 Skype Server를 호스트 하는지 여부를 나타냅니다. 이를 False로 설정 해야 합니다.

- **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다. Exchange Online의 FQDN은 exap.um.outlook.com입니다.

- **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다. 이를 False로 설정 해야 합니다.

- **VerificationLevel** 호스팅된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다. **UseSourceVerification**(호스팅 공급자에서 보내는 메시지에 포함된 확인 수준 사용)으로 설정합니다. 이 수준을 지정 하지 않으면 메시지가 비안정형로 거부 됩니다.

## <a name="verify-replication-of-the-updated-central-management-store"></a>업데이트 된 중앙 관리 저장소의 복제 확인

앞 섹션의 cmdlet을 사용 하 여 변경한 내용은 Edge 서버에 자동으로 적용 되며 일반적으로 복제 하는 데 1 분 미만이 걸립니다. 복제 상태에 대 한 유효성을 검사 한 후 다음 cmdlet을 사용 하 여 변경 내용이 Edge 서버에 적용 되었는지 확인할 수 있습니다.

비즈니스용 Skype Server 배포의 서버 내부에서 복제 업데이트를 확인 하려면 다음 cmdlet을 실행 합니다.

```powershell
Get-CsManagementStoreReplicationStatus
```
모든 복제본에 대해 UpToDate 값이 TRUE를 표시 하는지 확인 합니다.

변경 내용이 적용 되었는지 확인 하려면 Edge 서버에서 다음 cmdlet을 실행 합니다.

```powershell
Get-CsHostingProvider -LocalStore
```
표시 된 정보가 이전 단계에서 커밋된 변경 내용과 일치 하는지 두 번 확인 합니다.

## <a name="see-also"></a>참고 항목

[호스팅된 Exchange UM에서 비즈니스용 Skype 서버 사용자에 게 음성 메일 제공](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[비즈니스용 Skype 서버에서 호스팅되는 Exchange 통합 메시징 통합](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
