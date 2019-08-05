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
localization_priority: Normal
description: '조직에 비즈니스용 Skype를 배포 하는 경우 하나 이상의 비즈니스용 Skype Online 고객의 도메인과 페더레이션 할 수 있습니다. '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188793"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객에 대 한 페더레이션 지원 구성 

다음과 같은 방법으로 조직의 사용자에 게 통신 서비스를 제공할 수 있습니다.

  - 조직의 비즈니스용 Skype 서버 (온 *-프레미스 서비스*)를 배포 하 고 조직의 비즈니스용 skype 사용자 계정을 설정 합니다.
  - 호스팅 공급자를 사용 하 여 Microsoft 비즈니스용 Skype Online 고객 계정을 설정 하 고 호스팅 공급자와 사용자 계정을 설정 합니다 ( *온라인 서비스*라고 함).

조직에 비즈니스용 Skype를 배포 하는 경우 하나 이상의 비즈니스용 Skype Online 고객의 도메인과 페더레이션 할 수 있습니다. 온-프레미스 비즈니스용 Skype 배포 사용자와 비즈니스용 Skype Online 고객 간의 페더레이션을 사용 하려면 비즈니스용 Skype Online 고객의 도메인 및 사용자 간 지원을 구성 해야 합니다.

> [!NOTE]  
> 이 설명서는 비즈니스용 Skype Online 고객과의 페더레이션을 지원 하도록 조직을 구성 하는 절차에만 대해 설명 합니다. 이 문서에서는 페더레이션을 지원 하도록 비즈니스용 Skype Online 고객을 구성 하는 절차에 대해 설명 하지 않습니다. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과 페더레이션 하기 위한 필수 구성 요소

비즈니스용 Skype Online 고객과 페더레이션 하려면 조직의 비즈니스용 Skype 서버에 대 한 초기 배포 및 구성을 이미 완료 해야 합니다. 여기에는 다음이 포함 됩니다.

  - 조직에서 하나 이상의 Standard Edition server 또는 하나의 Enterprise Edition 프런트 엔드 풀을 배포 합니다. 
  - 비즈니스용 Skype 서버에서 내부 사용자 계정을 사용 하도록 설정 합니다. 
  - 하나 이상의 Edge 서버와 외부 사용자 액세스를 지 원하는 데 필요한 다른 구성 요소를 배포 합니다. 자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.
  - 조직 내에서 페더레이션을 지원 하도록 설정 하 고 페더레이션 도메인의 액세스를 제어 하기 위한 적절 한 방법을 구성 합니다. 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함](../access-edge/enable-or-disable-remote-user-access.md) 및 [조직의 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요.
  - 조직의 사용자에 대 한 외부 사용자 액세스를 사용 하도록 설정 자세한 내용은 [비즈니스용 Skype 사용 가능 사용자에 게 외부 사용자 액세스 정책 지정](../external-access-policies/assign-an-external-user-access-policy.md)을 참조 하세요.



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>비즈니스용 Skype Online 도메인에 대 한 페더레이션 지원 구성

비즈니스용 Skype Online 고객과 페더레이션 하려면 다음 단계를 완료 해야 합니다.

  - 비즈니스용 Skype Online 2010 고객의 도메인에 대 한 지원을 구성 합니다 (예: contoso.onmicrosoft.com). [비즈니스용 Skype Online 고객과 페더레이션 하기 위한 필수 구성 요소](#prerequisites-for-federating-with-a-skype-for-business-online-customer)에 지정 된 대로 조직에 대 한 페더레이션을 이미 사용 하도록 설정 해야 합니다. 페더레이션을 사용 하려면 페더레이션 도메인에서 액세스를 제어 하는 데 사용할 메서드를 지정 해야 합니다. 검색을 사용 하도록 조직을 구성한 경우 조직의 허용 목록에 도메인을 추가 하는 것은 선택 사항입니다. 도메인 검색을 사용 하도록 설정 하지 않은 경우 비즈니스용 Skype Online 고객의 도메인 이름을 허용 된 도메인 목록에 추가 해야 합니다. 비즈니스용 Skype Server 제어판을 사용 하거나 **새 CSAllowedDomain** cmdlet을 실행 하 여 도메인 이름을 추가할 수 있습니다. 도메인 검색 사용을 포함 하 여 비즈니스용 Skype Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 조직의 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요. **새-csalloweddomain** cmdlet을 사용 하 여 도메인을 추가 하는 방법에 대 한 자세한 내용은 [새 csalloweddomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)을 참조 하세요.

    > [!NOTE]  
    > 비즈니스용 Skype Online 고객은 여러 도메인을 가질 수 있습니다. 둘 이상의 도메인에 페더레이션 하려는 경우 페더레이션을 지원할 각 도메인에 대 한 지원을 구성 해야 하며 비즈니스용 Skype Online 고객의 관리자가 각 도메인에 대해 페더레이션을 사용 하도록 설정 해야 합니다. 페더레이션 할 수 있습니다.

  - 페더레이션 하려는 비즈니스용 Skype Online 고객 도메인의 호스팅 공급자에 대 한 지원을 구성 합니다. 이 섹션의 절차를 사용 하 여 호스팅 공급자에 대 한 지원을 구성 합니다.

    > [!NOTE]  
    > 이 단계는 페더레이션 파트너의 위치에서 온-프레미스를 사용 하는 도메인과 페더레이션 하는 것이 아니라 비즈니스용 Skype Online 고객 도메인이 있는 페더레이션에만 필요 합니다.


### <a name="to-configure-support-for-a-hosting-provider"></a>호스팅 공급자에 대 한 지원을 구성 하려면

1.  프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

2.  **새-CsHostingProvider** cmdlet을 실행 하 여 호스팅 공급자를 만들고 구성 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **Id** 는 만들려는 호스팅 공급자에 대 한 고유한 문자열 값 식별자를 지정 합니다. 이 Identity로 기존 공급자가 이미 구성된 경우에는 명령이 실패합니다.
    
      - **Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다. 이 값은 수정할 수 없습니다. 호스팅 공급자가 프록시 서버를 변경하는 경우 해당 공급자에 대한 항목을 삭제한 다음 다시 만들어야 합니다.
    
      - **VerificationLevel** 는 호스팅 공급자가 보낸 메시지를 확인 하 여 해당 공급자 로부터 보냈는지 확인 하는 방법을 지정 합니다.
    
      - **Enabled **는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다. 이 값이 **True **로 설정되어야 두 조직 간 메시지를 교환할 수 있습니다.
    
      - **EnabledSharedAddressSpace **는 호스팅 공급자가 공유 SIP 주소 공간(분할 도메인) 시나리오에서 사용 중인지 여부를 나타냅니다.
    
      - **HostsOCSUsers** 는 호스팅 공급자가 비즈니스용 Skype 서버 계정을 호스트 하는 데 사용 되는지 여부를 나타냅니다. **False **로 설정하면 공급자가 Microsoft Exchange 계정 등과 같은 다른 계정 유형을 호스팅합니다.
    
      - **Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다.
    
    이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [새-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)를 참조 하세요.

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>비즈니스용 Skype Online 고객과 페더레이션에 대 한 사용자 액세스 구성 

페더레이션 파트너와 통신할 수 있도록 조직의 모든 사용자에 대 한 사용자 계정을 구성 해야 합니다. 이 구성은 페더레이션을 지 원하는 Microsoft 비즈니스용 Skype Online 고객 도메인을 포함 하 여 모든 페더레이션 파트너에 적용 됩니다. 사용자 계정에 대 한 페더레이션 지원을 구성 하는 방법에 대 한 자세한 내용은 [페더레이션 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-federated-user-access.md) 참조 하 고 [비즈니스용 Skype 사용 가능 사용자에 게 외부 사용자 액세스 정책을 할당](../external-access-policies/assign-an-external-user-access-policy.md)합니다.

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비즈니스용 Skype Online 고객과 통신 확인

조직의 비즈니스용 Skype 사용자가 비즈니스용 Skype Online 고객의 사용자와 통신할 수 있도록 하려면 다음 단계를 완료 해야 합니다.

  - 모든 필수 조건을 충족 합니다. 여기에는 내부 및 경계 서버 배포, 조직에 대 한 페더레이션 지원 설정, 사용자 계정 설정 등이 포함 됩니다. 자세한 내용은 [비즈니스용 Skype Online 고객과 페더레이션 하기 위한 필수 구성 요소](#prerequisites-for-federating-with-a-skype-for-business-online-customer)를 참조 하세요.
  - 내부 배포에서 도메인 액세스 지원을 구성 했습니다. 여기에는 비즈니스용 Skype Online 고객 도메인에서 액세스할 수 있도록 호스트 공급자 항목을 만들고 배포를 구성 하는 작업이 포함 됩니다. 자세한 내용은 [비즈니스용 Skype Online 도메인에 대 한 페더레이션 지원 구성을](#configure-federation-support-for-a-skype-for-business-online-domain)참조 하세요.
  - 페더레이션을 지원 하도록 사용자 계정을 구성 했습니다. 자세한 내용은 [비즈니스용 Skype Online 고객과의 페더레이션에 대 한 사용자 액세스 구성을](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)참조 하세요.

이러한 모든 단계를 완료 하 고 비즈니스용 Skype Online 고객의 관리자가 조직과의 페더레이션을 지원 하기 위해 온라인 서비스의 모든 구성을 완료 한 후에는 간 통신을 테스트 하 여 통신을 확인 하세요. 조직의 내부 사용자 및 비즈니스용 Skype Online 고객의 사용자입니다. 통신에 실패 한 경우에는 Edge 서버의 로깅 도구를 사용 하 여 문제를 해결 하기 위해 로그 및 추적 파일을 캡처 하세요. 
