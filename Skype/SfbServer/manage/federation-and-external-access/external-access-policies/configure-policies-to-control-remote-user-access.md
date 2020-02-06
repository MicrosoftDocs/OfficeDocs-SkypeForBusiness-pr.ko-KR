---
title: 원격 사용자 액세스를 제어하도록 정책 구성
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 원격 사용자가 비즈니스용 Skype Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 원격 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818299"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어 하도록 정책 구성

원격 사용자가 비즈니스용 Skype Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 원격 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 사이트 정책은 글로벌 정책 보다 우선 하며 사용자 정책은 사이트 및 전역 정책 보다 우선 합니다. 구성할 수 있는 정책의 유형에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요. 한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.

> [!NOTE]  
> 조직의 원격 사용자 액세스를 사용 하도록 설정 하지 않은 경우에도 원격 사용자 액세스를 제어 하도록 정책을 구성할 수 있습니다. 그러나 사용자가 구성한 정책은 조직에 대해 원격 사용자 액세스를 사용할 수 있는 경우에만 적용 됩니다. 또한 원격 사용자 액세스를 제어 하는 사용자 정책을 지정 하면 비즈니스용 Skype Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다. 원격 위치에서 비즈니스용 Skype 서버에 로그인 할 수 있는 사용자를 지정 하는 방법에 대 한 자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.

다음 절차를 사용 하 여 원격 사용자 액세스를 제어 하는 데 사용할 각 외부 액세스 정책을 구성 합니다.


> [!NOTE]  
> 이 절차에서는 원격 사용자와의 통신을 사용 하도록 정책을 구성 하는 방법에 대해 설명 하지만 원격 사용자 액세스를 지원 하도록 구성 하는 각 정책은 페더레이션된 사용자 액세스 및 공용 사용자 액세스를 구성할 수도 있습니다. 페더레이션 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](configure-policies-to-control-federated-user-access.md)참조 하세요. 공용 사용자를 지원 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 조직의 SIP 페더레이션 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요.


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>원격 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 원격 사용자 액세스를 지원 하도록 전역 정책을 구성 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다. **사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. **새 외부 액세스 정책**에서 사용자 정책이 적용 되는 항목을 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: remote users에 대 한 통신을 사용 하도록 설정 하는 사용자 정책에 대 한 **enableremoteusers** ).
    
      - 기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  ) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.

6.  다음 중 하나를 수행 합니다.
    
      - 정책에 대 한 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 정책에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

원격 사용자 액세스를 사용 하도록 설정 하려면 조직에서 원격 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.

사용자 정책 인 경우 원격으로 연결할 수 있도록 하는 사용자에 게도 정책을 적용 해야 합니다. 자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.
