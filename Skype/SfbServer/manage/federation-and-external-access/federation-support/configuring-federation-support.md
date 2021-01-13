---
title: 비즈니스용 Skype Online 고객을 위한 페더레이션 지원 구성
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '조직에 비즈니스용 Skype를 배포하는 경우 하나 이상의 비즈니스용 Skype Online 고객의 도메인과 페더러가 될 수 있습니다. '
ms.openlocfilehash: f09e717af9e5209a0bb4bfdeb0ea50abbdaf7f86
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817238"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객에 대한 페더링 지원 구성 

다음과 같은 방법으로 조직의 사용자에게 통신 서비스를 제공할 수 있습니다.

  - 조직에 비즈니스용 Skype 서버(즉, 비즈니스용 Skype 서비스)를 배포하고 조직에서 비즈니스용 Skype 사용자 계정을 설정합니다.
  - 호스팅 공급자를 사용하여 Microsoft 비즈니스용 Skype Online 고객 계정을 설정하고 호스팅 공급자(온라인 서비스)를 사용하여 사용자 계정을 *설정합니다.*

조직에 비즈니스용 Skype를 배포하는 경우 하나 이상의 비즈니스용 Skype Online 고객의 도메인과 페더러가 될 수 있습니다. 비즈니스용 Skype 배포의 사용자와 비즈니스용 Skype Online 고객의 사용자 간에 페더미스를 사용하도록 설정하려면 비즈니스용 Skype Online 고객의 도메인 및 사용자에 대한 지원을 구성해야 합니다.

> [!NOTE]  
> 이 설명서에서는 비즈니스용 Skype Online 고객과의 페더링을 지원하기 위해 조직을 구성하는 절차만 설명하고 있습니다. 이 설명서에서는 페더링을 지원하기 위해 비즈니스용 Skype Online 고객을 구성하는 절차에 대해 설명하지 않습니다. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과의 페더맹을 위한 선행 요구

비즈니스용 Skype Online 고객과 페더에 연결하려면 조직에서 비즈니스용 Skype 서버의 초기 배포 및 구성을 이미 완료한 것입니다. 여기에는 다음이 포함됩니다.

  - 조직에 Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀을 하나 이상 배포합니다. 
  - 비즈니스용 Skype 서버에 대해 내부 사용자 계정을 사용하도록 설정 
  - 외부 사용자 액세스를 지원하는 데 필요한 하나 이상의 에지 서버 및 기타 구성 요소를 배포합니다. 자세한 내용은 비즈니스용 Skype 서버에 대한 외부 액세스 및 [페더링 관리를 참조하세요.](../managing-federation-and-external-access.md)
  - 조직 내에서 페더레이션 지원을 설정하고 페더레이션된 도메인의 액세스를 제어하기 위해 적합한 방법을 구성합니다. 자세한 내용은 조직에 대한 원격 [사용자](../access-edge/enable-or-disable-remote-user-access.md) 액세스 사용 또는 사용 안 하도록 설정 및 [SIP 페더타이트 공급자 관리를 참조합니다.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - 조직의 사용자에 대해 외부 사용자 액세스를 설정합니다. 자세한 내용은 비즈니스용 Skype 사용 가능 사용자에게 외부 사용자 액세스 정책 [할당을 참조하세요.](../external-access-policies/assign-an-external-user-access-policy.md)



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>비즈니스용 Skype Online 도메인에 대한 페더임 지원 구성

비즈니스용 Skype Online 고객과 페더맹을 사용하려면 다음 단계를 완료해야 합니다.

  - 비즈니스용 Skype Online 2010 고객의 도메인에 대한 지원을 구성합니다(예: contoso.onmicrosoft.com. 비즈니스용 [Skype Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer)고객과의 페더에 대한 전제 요구에 지정된 경우 조직에 대해 페더맹을 이미 사용하도록 설정해야 합니다. 페더레이션을 설정하려면 페더레이션된 도메인에서 액세스를 제어하기 위해 사용할 방법을 지정해야 합니다. 조직에 검색이 사용되도록 구성한 경우 필요에 따라 도메인을 조직의 허용 목록에 추가할 수 있습니다. 도메인 검색을 사용하도록 설정하지 않은 경우 비즈니스용 Skype Online 고객의 도메인 이름을 허용 도메인 목록에 추가해야 합니다. 비즈니스용 Skype 서버 제어판을 사용하여 또는 **New-CSAllowedDomain** cmdlet을 실행하여 도메인 이름을 추가할 수 있습니다. 도메인 검색을 사용하도록 설정하는 등 비즈니스용 Skype 서버 제어판 사용에 대한 자세한 내용은 비즈니스용 Skype 서버에서 조직의 SIP 페더전 공급자 [관리를 참조하세요.](../sip-providers/manage-sip-federated-providers-for-your-organization.md) **New-CSAllowedDomain** cmdlet을 사용하여 도메인을 추가하는 데 대한 자세한 내용은 [New-CsAllowedDomain을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)

    > [!NOTE]  
    > 비즈니스용 Skype Online 고객은 여러 도메인을 사용할 수 있습니다. 두 개 이상의 도메인과 페더미스를 구성하려면 페더전을 지원할 각 개별 도메인에 대한 지원을 구성해야 하고, 비즈니스용 Skype Online 고객의 관리자는 페더에 대해 각 도메인에 대해 페더전을 사용하도록 설정해야 합니다.

  - 페더링하려는 비즈니스용 Skype Online 고객 도메인의 호스팅 공급자에 대한 지원을 구성합니다. 이 섹션의 절차에 따라 호스팅 공급자에 대한 지원을 구성합니다.

    > [!NOTE]  
    > 이 단계는 비즈니스용 Skype Online 고객의 도메인과의 페더에만 필요하고, 페더임 파트너의 위치에 있는 모든 도메인과의 페더전에는 필요하지 않습니다.


### <a name="to-configure-support-for-a-hosting-provider"></a>호스팅 공급자에 대한 지원을 구성하려면

1.  프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 프로그램, 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.** 

2.  **New-CsHostingProvider** cmdlet을 실행하여 호스팅 공급자를 만들고 구성합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Identity** 는 만들고 있는 호스팅 공급자에 대한 고유 문자열 값 식별자를 지정합니다. 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **ProxyFQDN** 은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **VerificationLevel** 은 호스팅 공급자가 보낸 메시지가 해당 공급자로부터 전송되었는지 확인하는 방법 또는 여부를 나타냅니다.
    
      - **Enabled** 는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True** 로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
    
      - **HostsOCSUsers는** 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스팅하는 데 사용되는지 여부를 나타냅니다. **False인** 경우 공급자는 Microsoft Exchange 계정과 같은 다른 계정 유형을 호스팅합니다.
    
      - **IsLocal은** 호스팅 공급자가 사용하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지 내에 포함되어 있는지 여부를 나타냅니다.
    
    이 cmdlet 사용에 대한 자세한 내용은 [New-CsHostingProvider를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과의 페더에 대한 사용자 액세스 구성 

조직의 모든 사용자에 대한 사용자 계정이 페더레이션된 파트너와 통신할 수 있도록 구성해야 합니다. 이 구성은 사용자가 페더전을 지원하는 Microsoft 비즈니스용 Skype Online 고객 도메인을 포함하여 모든 페더러다임 파트너에 적용됩니다. 사용자 계정에 대한 페더링 지원을 구성하는 자세한 [](../external-access-policies/configure-policies-to-control-federated-user-access.md) 내용은 페더링된 사용자 액세스를 제어하는 정책 구성 및 비즈니스용 Skype 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당을 [참조하세요.](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객과의 통신 확인

조직의 비즈니스용 Skype 사용자가 비즈니스용 Skype Online 고객 사용자와 통신할 수 있도록 설정하려면 다음 단계를 완료해야 합니다.

  - 모든 필수 구성 요소가 충족되었습니다. 여기에는 내부 및 에지 서버 배포, 조직의 페더레이션 지원 설정 및 사용자 계정 설정이 포함됩니다. 자세한 내용은 비즈니스용 Skype Online 고객과 페더에 대한 사전 요구 [사항을 참조하세요.](#prerequisites-for-federating-with-a-skype-for-business-online-customer)
  - 내부 배포에서 도메인 액세스 지원을 구성했습니다. 여기에는 호스트 공급자 항목을 만들고 비즈니스용 Skype Online 고객의 도메인에서 액세스를 허용하도록 배포를 구성하는 것이 포함됩니다. 자세한 내용은 비즈니스용 Skype Online 도메인에 대한 페더전 지원 [구성을 참조하세요.](#configure-federation-support-for-a-skype-for-business-online-domain)
  - 페더레이션을 지원하도록 사용자 계정을 구성했습니다. 자세한 내용은 비즈니스용 Skype Online 고객과의 페더에 대한 사용자 액세스 [구성을 참조하세요.](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)

이러한 모든 단계를 완료하고 비즈니스용 Skype Online 고객의 관리자가 조직과의 페더맹을 지원하기 위해 온라인 서비스의 모든 구성을 완료한 후 조직의 내부 사용자와 비즈니스용 Skype Online 고객 사용자 간의 통신을 테스트하여 통신을 확인하세요. 통신에 성공하지 못하면 에지 서버의 로깅 도구를 사용하여 로그 및 추적 파일을 캡처하여 문제를 해결합니다. 
