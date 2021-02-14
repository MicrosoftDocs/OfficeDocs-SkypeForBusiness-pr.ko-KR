---
title: 익명 사용자를 지원하기 위한 회의 정책 할당
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: 익명 사용자를 지원하도록 회의 정책을 구성하고 이 회의 정책을 특정 사용자에게 적용하여 익명 사용자를 초대할 수 있는 사용자를 제어합니다.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817458"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 익명 사용자를 지원하기 위한 회의 정책 할당 


기본적으로 모든 사용자는 익명 사용자를 모임에 참여하도록 초대할 수 없습니다. 익명 사용자를 지원하도록 회의 정책을 구성하고 이 회의 정책을 특정 사용자에게 적용하여 익명 사용자를 초대할 수 있는 사용자를 제어합니다. 익명 사용자를 지원하도록 회의 정책을 구성하는 방법에 대한 자세한 내용은 비즈니스용 [Skype](../../conferencing/create-policies.md) 서버에서 회의 정책 만들기 및 비즈니스용 [Skype](../managing-federation-and-external-access.md)서버에 대한 외부 액세스 관리 및 페더링 관리를 참조하세요.

이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용하려면 이 섹션의 절차를 사용합니다.

> [!NOTE]  
> 사용자가 익명 사용자를 초대할 수 있도록 정책을 구성하고 적용해야 할 뿐 아니라, 조직에서 익명 사용자를 지원하도록 설정해야 합니다. 자세한 내용은 비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어하는 [정책 구성을 참조하세요.](../external-access-policies/configure-policies-to-control-public-user-access.md)


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>모임의 익명 참가에 대한 사용자 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 

3.  왼쪽 탐색 모음에서 **회의** 를 클릭하고 다음 중 하나를 수행합니다.
    
    1.  새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 익명 사용자와 통신할 수 있도록 설정하는 사용자 정책의 경우 **EnableAnonymous**).
    
    2.  기존 사용자 정책을 구성하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시** 를 차례로 클릭합니다.

4.  **회의 정책** 대화 상자에서 **참가자가 익명 사용자를 초대할 수 있도록 허용** 확인란을 선택합니다.

5.  **커밋** 을 클릭합니다.

6.  왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성할 사용자 계정을 검색합니다.

7.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

8.  회의 **정책에서** 비즈니스용 Skype 서버 사용자 편집에서 이 사용자에게 적용할 익명 사용자 액세스 구성을 사용하여 사용자 정책을 선택합니다.  

    > [!NOTE]  
    > 자동 <STRONG> &lt; 설정은 &gt; </STRONG> 기본 서버 설치 설정을 적용하며 서버에 의해 자동으로 적용됩니다.


사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직에서 익명 사용자에 대한 지원을 사용하도록 설정해야 합니다. 자세한 내용은 비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어하는 [정책 구성을 참조하세요.](../external-access-policies/configure-policies-to-control-public-user-access.md)

