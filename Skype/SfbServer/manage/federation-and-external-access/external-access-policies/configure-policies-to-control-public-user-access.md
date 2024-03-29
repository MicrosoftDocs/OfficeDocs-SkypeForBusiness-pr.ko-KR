---
title: 공용 사용자 액세스를 컨트롤하는하는 정책 구성
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: ublic IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 공용 IM 서비스 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다.
ms.openlocfilehash: d05827c7af0f7712db6d2436f2ecdb00838ea53f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398962"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>공용 사용자 액세스를 제어하는 정책을 비즈니스용 Skype 서버

공용 IM(인스턴트 메시징) 연결을 사용하면 조직의 사용자가 IM을 사용하여 공용 IM 서비스 공급자가 제공하는 IM 서비스 사용자와 통신할 수 있습니다. 공용 사용자가 내부 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 비즈니스용 Skype 서버 있습니다. 공용 인스턴트 메시징 연결은 배포 및 사용자 구성에 의존하는 추가된 기능입니다. 또한 공용 IM 공급자의 서비스 프로비전에 따라 다릅니다. 

공용 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 비즈니스용 Skype 서버 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.

IM 초대의 경우 응답 여부는 클라이언트 소프트웨어에 따라 다릅니다. 사용자가 구성한 규칙(사용자 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단되는 경우가 아니면 요청이 수락됩니다. 또한 사용자가 자신의 **허용** 목록에 없는 사용자에 대해 모든 IM을 차단하도록 선택한 경우 IM 초대가 차단될 수 있습니다.



> [!NOTE]  
> 조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 공용 사용자 액세스를 제어하는 정책을 구성할 수 있습니다. 그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다. 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 안 [하도록 설정을 참조합니다](../access-edge/enable-or-disable-remote-user-access.md). 또한 공용 사용자 액세스를 제어하기 위한 사용자 정책을 지정하는 경우 정책은 공용 사용자 액세스를 비즈니스용 Skype 서버 및 정책을 사용하도록 구성된 사용자에게만 적용됩니다. 사용자 지정에 로그인할 수 있는 공용 사용자를 지정하는 비즈니스용 Skype 서버 외부 사용자 액세스 정책 할당[을 참조합니다](assign-an-external-user-access-policy.md).


다음 절차에 따라 하나 이상의 공용 IM 공급자 사용자의 액세스를 지원하기 위한 정책을 구성합니다.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>공용 사용자 액세스를 지원하기 위한 외부 액세스 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.
    
      - 공용 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 공용 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnablePublicUsers**).
    
      - 기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.

5.  (선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.

6.  다음 중 하나를 수행합니다.
    
      - 정책에 대한 공용 사용자 액세스를 사용하도록 설정하려면 **공용 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 정책에 대한 공용 사용자 액세스를 사용하지 않도록 설정하려면 **공용 사용자와의 통신 사용** 확인란 선택을 취소합니다.

7.  **커밋** 을 클릭합니다.

공용 사용자 액세스를 사용하도록 설정하려면 조직에서 페더레이션 지원도 사용하도록 설정해야 합니다. 자세한 내용은 [Configure policies to control federated user access in 비즈니스용 Skype 서버](configure-policies-to-control-federated-user-access.md).

사용자 정책의 경우에는 공용 사용자와 공동 작업하도록 할 공용 사용자에게도 정책을 적용해야 합니다. 


## <a name="see-also"></a>참고 항목

[조직의 SIP 페더레이션 제공자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
