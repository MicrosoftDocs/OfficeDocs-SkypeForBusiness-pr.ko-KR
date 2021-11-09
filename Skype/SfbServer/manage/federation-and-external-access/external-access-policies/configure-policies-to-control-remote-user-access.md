---
title: 원격 사용자 액세스를 컨트롤하는 정책 구성
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 원격 사용자가 내부 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 비즈니스용 Skype 서버 있습니다. 원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.
ms.openlocfilehash: a060622919fb8d948b55178a8e0b1d4da8b6e5cc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847291"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>원격 사용자 액세스를 제어하기 위한 정책 비즈니스용 Skype 서버

원격 사용자가 내부 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 비즈니스용 Skype 서버 있습니다. 원격 사용자 액세스를 제어하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 사이트 정책은 글로벌 정책보다 우선 적용되며 사용자 정책은 사이트 정책 및 글로벌 정책보다 우선 적용됩니다. 구성할 수 있는 정책 유형에 대한 자세한 내용은 [Managing federation and external access to 비즈니스용 Skype 서버.](../managing-federation-and-external-access.md) 비즈니스용 Skype 서버 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.

> [!NOTE]  
> 조직에 대해 원격 사용자 액세스를 사용하도록 설정하지 않았더라도 원격 사용자 액세스를 제어하는 정책을 구성할 수 있습니다. 그러나 구성하는 정책은 조직에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우에만 적용됩니다. 또한 원격 사용자 액세스를 제어하기 위한 사용자 정책을 지정하는 경우 해당 정책은 원격 사용자 액세스를 비즈니스용 Skype 서버 사용하도록 구성된 사용자에게만 적용됩니다. 원격 위치에서 원격 위치에 로그인할 수 있는 사용자를 비즈니스용 Skype 서버 자세한 내용은 [Assign an external user access policy 를 참조하세요.](assign-an-external-user-access-policy.md)

원격 사용자 액세스를 제어하는 데 사용할 각 외부 액세스 정책을 구성하려면 다음 절차를 사용합니다.


> [!NOTE]  
> 이 절차에서는 원격 사용자와의 통신을 가능하게 하는 정책을 구성하는 방법에 대해서만 설명하지만, 원격 사용자 액세스를 지원하기 위해 구성하는 각 정책은 페더레이션 사용자 액세스 및 공용 사용자 액세스도 구성할 수 있습니다. 페더링 사용자를 지원하도록 정책을 구성하는 데 대한 자세한 내용은 [Configure policies to control federated user access in 비즈니스용 Skype 서버.](configure-policies-to-control-federated-user-access.md) 공용 사용자를 지원하기 위한 정책을 구성하는 데 대한 자세한 내용은 [Manage SIP federated providers for your organization in 비즈니스용 Skype 서버.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>원격 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.
    
      - 원격 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책, **편집** 을 차례로 클릭한 다음 **세부 정보 표시** 를 클릭합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 에서 사용자 정책에서 다루는 내용을 나타내는 고유 이름을 **이름** 필드에 만듭니다(예: 원격 사용자에 대한 통신을 가능하게 하는 사용자 정책의 경우 **EnableRemoteUsers**).
    
      - 기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시** 를 차례로 클릭합니다.

5.  (선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.

6.  다음 중 하나를 수행합니다.
    
      - 정책에 대해 원격 사용자 액세스를 사용하도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 정책에 대해 원격 사용자 액세스를 사용하지 않도록 설정하려면 **원격 사용자와의 통신 사용** 확인란을 선택 취소합니다.

7.  **커밋** 을 클릭합니다.

원격 사용자 액세스를 사용하도록 설정하려면 조직에서 원격 사용자 액세스에 대한 지원을 사용하도록 설정해야 합니다. 자세한 내용은 [Enable or disable federation and public IM connectivity을 참조합니다.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

사용자 정책의 경우에는 원격으로 연결할 수 있도록 하려는 사용자에게도 정책을 적용해야 합니다. 자세한 내용은 외부 사용자 액세스 정책 [할당을 참조합니다.](assign-an-external-user-access-policy.md)
