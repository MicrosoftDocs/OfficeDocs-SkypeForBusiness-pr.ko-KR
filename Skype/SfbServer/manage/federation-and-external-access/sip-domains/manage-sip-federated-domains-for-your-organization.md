---
title: 조직의 SIP 페더레이션 도메인 관리
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 페더맹할 수 있는 SIP 도메인을 관리 및 구성하는 방법을 알아보고,
ms.openlocfilehash: 0c79141a491f713c1a6858d6703fc3fac55d5b20
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386646"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>조직에서 조직의 SIP 페더전 도메인 비즈니스용 Skype 서버


페더레이션할 수 있는 SIP 도메인을 관리하고 구성하려면 다음을 수행할 수 있습니다.

  - SIP 페더레이션 파트너 도메인의 허용 도메인 목록을 만들거나 편집합니다.

  - SIP 페더레이션 도메인의 차단 도메인 목록을 만들거나 편집합니다.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>사용자 지정에서 허용되는 외부 도메인에 대한 지원을 비즈니스용 Skype 서버

페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 있는 특정 도메인을 관리할 수 있습니다. 하나 이상의 특정 외부 도메인을 허용된 페더레이션 도메인으로 구성합니다. 이렇게 하려면 각 도메인을 허용된 도메인 목록에 추가합니다. 조직에서 파트너 검색을 사용하는 경우에도 해당 도메인이 1,000명 이상의 사용자와 통신해야 하거나 초당 20개가 넘는 메시지를 보내야 할 수 있는 페더레이션 파트너인 경우에는 이와 같이 구성합니다. 조직에서 파트너 검색을 사용하지 않는 경우에는 허용된 도메인 목록에 추가하는 외부 도메인의 사용자만 조직 사용자와의 IM 및 회의에 참가할 수 있습니다. 페더레이션 도메인에 대한 액세스를 페더레이션 파트너의 액세스 에지 서비스를 실행하는 특정 서버로 제한하려면 허용된 도메인 목록의 각 도메인에 대해 액세스 에지 서비스를 실행하는 서버의 도메인 이름을 지정하면 됩니다.

> [!NOTE]  
> 이 절차에서는 특정 도메인에 대한 지원을 구성하는 방법에 대해 설명하지만 페더레이션 사용자에 대한 지원을 구현하려면 조직에서 페더레이션 사용자를 지원하도록 설정하고 페더레이션 사용자와 공동 작업할 수 있는 사용자를 제어하는 정책을 구성하고 적용해야 합니다. 페더링 사용자에 대한 지원을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 안 [하도록 설정을 참조합니다](../access-edge/enable-or-disable-remote-user-access.md). 페더링을 제어하는 정책을 구성하는 데 대한 자세한 내용은 [Configure policies to control federated user access을 참조합니다](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>허용 도메인 목록에 외부 도메인을 추가하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.
2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 
3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **페더레이션 도메인** 을 클릭합니다.
4.  **페더레이션 도메인** 페이지에서 **새로 만들기** 를 클릭한 다음 **허용 도메인** 을 클릭합니다.
5.  **새 페더레이션 도메인** 에서 다음을 수행합니다.
    
      - **도메인 이름 또는 FQDN** 에 페더레이션 파트너 도메인의 이름을 입력합니다.       

        > [!NOTE]  
        > 이 이름은 고유해야 하며, 액세스 에지 서비스를 실행하는 이 서버의 기존 허용 도메인과 같을 수 없습니다. 이름은 256자까지 지정할 수 있습니다.<BR><br>페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 **contoso.com** 을 입력하면 **it.contoso.com** 도메인도 검색 결과에 반환됩니다.<BR><br>페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다. 비즈니스용 Skype 서버 동기화하지 않도록 하여 이 문제를 방지할 수 있습니다.
    
      - 이 페더레이션 도메인에 대한 액세스를 액세스 에지 서비스를 실행하는 특정 서버의 사용자로 제한하려면 **액세스 에지 서비스(FQDN)** 에 액세스 에지 서비스를 실행하는 페더레이션 도메인 서버의 FQDN을 입력합니다.    
      - 추가 정보를 제공하려면 **설명** 에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.

6.  **커밋** 을 클릭합니다.
7.  허용할 각 페더레이션 파트너 도메인에 대해 4~6단계를 반복합니다.

페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다. 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 하도록 설정을 참조 합니다](../access-edge/enable-or-disable-remote-user-access.md).

또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다. 자세한 내용은 [Configure policies to control federated user access을 참조합니다](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>2013에서 차단된 외부 도메인에 대한 지원을 비즈니스용 Skype 서버 

페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 없도록 차단되는 도메인을 관리할 수 있습니다. 차단된 도메인 목록은 차단 목록(허용되지 않는 항목에 대한 목록)으로 작동하며 이 옵션을 설정한 경우 페더레이션 도메인 검색에 적용됩니다. 자세한 내용은 [Enable or disable discovery of federation partners을 참조하세요](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

하나 이상의 외부 도메인에서 조직에 연결하는 것을 차단합니다. 이렇게 하려면 차단된 도메인 목록에 도메인을 추가합니다.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>차단된 도메인 목록에 외부 도메인을 추가하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.
2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 
3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭합니다.
4.  **페더레이션 도메인** 에서 **새로 만들기** 를 클릭한 다음 **차단된 도메인** 을 클릭합니다.
5.  **새 페더레이션 도메인** 에서 다음을 수행합니다.
    
      - **도메인 이름 또는 FQDN** 에 차단할 페더레이션 파트너 도메인의 이름을 입력합니다.

        > [!NOTE]  
        > 이름은 256자까지 지정할 수 있습니다.<BR><br>페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 **contoso.com** 을 입력하면 **it.contoso.com** 도메인도 검색 결과에 반환됩니다.<BR><br>페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다. 비즈니스용 Skype 서버 동기화하지 않도록 하여 이 문제를 방지할 수 있습니다.
   
      - (선택 사항) **설명** 에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.

6.  **커밋** 을 클릭합니다.
7.  차단할 각 페더레이션 파트너에 대해 4~6단계를 반복합니다.

페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다. 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 하도록 설정을 참조 합니다](../access-edge/enable-or-disable-remote-user-access.md).

또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다. 자세한 내용은 [Configure policies to control federated user access을 참조합니다](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>참고 항목

[페더레이션 사용자 액세스를 컨트롤하는 정책 구성](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[페더레이션 파트너 검색을 사용하도록 설정 또는 해제](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

