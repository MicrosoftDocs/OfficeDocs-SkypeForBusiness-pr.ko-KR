---
title: 비즈니스용 Skype Online 고객에 대 한 페더레이션 지원 구성
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '조직에 비즈니스용 Skype를 배포 하는 경우 비즈니스용 Skype Online 고객의 도메인과 하나 이상의 도메인을 페더레이션 할 수 있습니다. '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037288"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객에 대 한 페더레이션 지원 구성 

다음 방법 중 하나를 통해 조직의 사용자에 게 통신 서비스를 제공할 수 있습니다.

  - 조직에서 비즈니스용 Skype 서버 ( *온-프레미스 서비스*라고 함)를 배포 하 고 조직에서 비즈니스용 skype 사용자 계정을 설정 합니다.
  - 호스팅 공급자를 사용 하 여 Microsoft 비즈니스용 Skype Online 고객 계정을 설정 하 고 호스팅 공급자 ( *온라인 서비스*)와 함께 사용자 계정을 설정 하는 경우

조직에 비즈니스용 Skype를 배포 하는 경우 비즈니스용 Skype Online 고객의 도메인과 하나 이상의 도메인을 페더레이션 할 수 있습니다. 온-프레미스 비즈니스용 Skype 배포 사용자와 비즈니스용 Skype Online 고객 간의 페더레이션을 사용 하도록 설정 하려면 비즈니스용 Skype Online 고객의 도메인과 사용자에 대 한 지원을 구성 해야 합니다.

> [!NOTE]  
> 이 문서에서는 비즈니스용 Skype Online 고객과의 페더레이션을 지원 하도록 조직을 구성 하는 절차에 대해서만 설명 합니다. 이 설명서에서는 페더레이션을 지원 하도록 비즈니스용 Skype Online 고객을 구성 하는 절차는 설명 하지 않습니다. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과의 페더레이션을 위한 필수 구성 요소

비즈니스용 Skype Online 고객과 페더레이션 하려면 조직에서 비즈니스용 Skype 서버의 초기 배포 및 구성을 이미 완료 해야 합니다. 여기에는 다음이 포함됩니다.

  - 조직에서 하나 이상의 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀 배포 
  - 비즈니스용 Skype 서버에 대 한 내부 사용자 계정을 사용 하도록 설정 합니다. 
  - 외부 사용자 액세스를 지 원하는 데 필요한 하나 이상의에 지 서버 및 다른 구성 요소를 배포 합니다. 자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.
  - 조직 내에서 페더레이션 지원을 설정하고 페더레이션된 도메인의 액세스를 제어하기 위해 적합한 방법을 구성합니다. 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함](../access-edge/enable-or-disable-remote-user-access.md) 및 [조직에 대 한 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요.
  - 조직의 사용자에 대해 외부 사용자 액세스를 설정합니다. 자세한 내용은 [비즈니스용 Skype 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](../external-access-policies/assign-an-external-user-access-policy.md)을 참조 하십시오.



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>비즈니스용 Skype Online 도메인에 대 한 페더레이션 지원 구성

비즈니스용 Skype Online 고객과 페더레이션 하려면 다음 단계를 완료 해야 합니다.

  - 비즈니스용 Skype 온라인 2010 고객의 도메인에 대 한 지원을 구성 합니다 (예: contoso.onmicrosoft.com). [비즈니스용 Skype Online 고객과의 페더레이션을 위한 필수 구성 요소](#prerequisites-for-federating-with-a-skype-for-business-online-customer)에 지정 된 대로 조직에 대해 페더레이션을 사용 하도록 이미 설정 되어 있어야 합니다. 페더레이션을 설정하려면 페더레이션된 도메인에서 액세스를 제어하기 위해 사용할 방법을 지정해야 합니다. 조직에 검색이 사용되도록 구성한 경우 필요에 따라 도메인을 조직의 허용 목록에 추가할 수 있습니다. 도메인 검색을 사용 하도록 설정 하지 않은 경우 비즈니스용 Skype Online 고객의 도메인 이름을 허용 도메인 목록에 추가 해야 합니다. 비즈니스용 Skype 서버 제어판을 사용 하거나 **새-CSAllowedDomain** cmdlet을 실행 하 여 도메인 이름을 추가할 수 있습니다. 도메인 검색 사용을 포함 하 여 비즈니스용 Skype 서버 제어판을 사용 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 조직에 대 한 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요. **새 csalloweddomain** cmdlet을 사용 하 여 도메인을 추가 하는 방법에 대 한 자세한 내용은 [New-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)를 참조 하십시오.

    > [!NOTE]  
    > 비즈니스용 Skype Online 고객은 여러 도메인을 가질 수 있습니다. 둘 이상의 도메인에 페더레이션 하려면 페더레이션을 지원할 각 도메인에 대 한 지원을 구성 해야 하며 비즈니스용 Skype Online 고객의 관리자가 각 도메인에 대해 페더레이션을 사용 하도록 설정 해야 합니다. 페더레이션

  - 페더레이션 할 비즈니스용 Skype Online 고객 도메인의 호스팅 공급자에 대 한 지원을 구성 합니다. 이 섹션의 절차에 따라 호스팅 공급자에 대한 지원을 구성합니다.

    > [!NOTE]  
    > 이 단계는 페더레이션 파트너의 위치에 온-프레미스에 배포 된 도메인과 페더레이션 하지 않고 비즈니스용 Skype Online 고객의 도메인을 페더레이션 하는 경우에만 필요 합니다.


### <a name="to-configure-support-for-a-hosting-provider"></a>호스팅 공급자에 대한 지원을 구성하려면

1.  프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.

2.  **New-CsHostingProvider** cmdlet을 실행하여 호스팅 공급자를 만들고 구성합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Identity**는 만들고 있는 호스팅 공급자에 대한 고유 문자열 값 식별자를 지정합니다. 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **ProxyFQDN**은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **VerificationLevel**은 호스팅 공급자가 보낸 메시지가 해당 공급자로부터 전송되었는지 확인하는 방법 또는 여부를 나타냅니다.
    
      - **Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True**로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace**는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
    
      - **HostsOCSUsers** 은 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스트 하는 데 사용 되는지 여부를 나타냅니다. **False**인 경우에는 공급자가 Microsoft Exchange 계정 등의 다른 계정 유형을 호스팅합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다.
    
    이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)를 참조 하십시오.

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과의 페더레이션을 위한 사용자 액세스 구성 

조직의 모든 사용자에 대한 사용자 계정이 페더레이션된 파트너와 통신할 수 있도록 구성해야 합니다. 이 구성은 페더레이션을 지 원하는 Microsoft 비즈니스용 Skype Online 고객 도메인을 포함 하 여 모든 페더레이션 파트너에 대해 적용 됩니다. 사용자 계정에 대 한 페더레이션 지원을 구성 하는 방법에 대 한 자세한 내용은 [페더레이션 사용자 액세스를 제어 하도록 정책 구성을](../external-access-policies/configure-policies-to-control-federated-user-access.md) 참조 하 고 [비즈니스용 Skype 사용 가능 사용자에 게 외부 사용자 액세스 정책을 할당](../external-access-policies/assign-an-external-user-access-policy.md)합니다.

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객과의 통신 확인

조직의 비즈니스용 Skype 사용자가 비즈니스용 Skype Online 고객의 사용자와 통신할 수 있도록 하려면 다음 단계를 완료 해야 합니다.

  - 모든 필수 구성 요소가 충족되었습니다. 여기에는 내부 및 에지 서버 배포, 조직의 페더레이션 지원 설정 및 사용자 계정 설정이 포함됩니다. 자세한 내용은 [비즈니스용 Skype Online 고객과의 페더레이션을 위한 필수 구성 요소](#prerequisites-for-federating-with-a-skype-for-business-online-customer)를 참조 하세요.
  - 내부 배포에서 도메인 액세스 지원을 구성했습니다. 여기에는 비즈니스용 Skype Online 고객의 도메인에서 액세스를 허용 하도록 배포를 구성 하 고 호스트 공급자 항목을 만드는 작업이 포함 됩니다. 자세한 내용은 [비즈니스용 Skype Online 도메인에 대 한 페더레이션 지원 구성을](#configure-federation-support-for-a-skype-for-business-online-domain)참조 하십시오.
  - 페더레이션을 지원하도록 사용자 계정을 구성했습니다. 자세한 내용은 [비즈니스용 Skype Online 고객과의 페더레이션을 위한 사용자 액세스 구성](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)를 참조 하세요.

이러한 모든 단계를 완료 하 고 비즈니스용 Skype Online 고객의 관리자가 조직과의 페더레이션을 지원 하기 위해 온라인 서비스의 모든 구성을 완료 한 후에는 통신을 테스트 하 여 조직의 내부 사용자 및 비즈니스용 Skype Online 고객의 사용자입니다. 통신이 실패할 경우 문제를 해결 하기 위해에 지 서버에서 로깅 도구를 사용 하 여 로그 및 추적 파일을 캡처합니다. 
