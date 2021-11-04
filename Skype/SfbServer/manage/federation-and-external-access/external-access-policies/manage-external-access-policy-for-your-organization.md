---
title: 조직에 대한 외부 액세스 정책 관리
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Edge 서버를 하나 이상 배포한 후에는 조직에 대해 지원할 유형의 외부 액세스를 사용하도록 설정해야 합니다.
ms.openlocfilehash: d2e7e19e461e0b7777969aac4a73a50bb683e69c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763716"
---
# <a name="manage-external-access-policy-for-your-organization"></a>조직에 대한 외부 액세스 정책 관리

Edge 서버를 하나 이상 배포한 후에는 조직에 대해 지원할 유형의 외부 액세스를 사용하도록 설정해야 합니다.

조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 글로벌 정책이 만들어지지만 삭제할 수는 없습니다.

  - **글로벌 정책**   글로벌 정책은 에지 서버를 배포할 때 작성됩니다. 기본적으로 글로벌 정책에서는 외부 사용자 액세스 옵션이 사용하도록 설정되지 않습니다. 글로벌 수준에서 외부 사용자 액세스를 지원하려면 외부 사용자 액세스 옵션 유형을 하나 이상 지원하도록 글로벌 정책을 구성합니다. 글로벌 정책은 조직의 모든 사용자에게 적용되지만, 사이트 정책과 사용자 정책이 글로벌 정책을 다시 정의합니다. 삭제한 글로벌 정책은 제거되는 것이 아니라 기본 설정으로 다시 설정됩니다.

  - **사이트 정책**   하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스 지원을 제한할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다. 예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.

  - **사용자 정책**   하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스 지원을 제한할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다. 예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.


> [!IMPORTANT]  
> 한 정책 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.


이러한 옵션에는 다음과 같은 유형의 외부 액세스가 포함됩니다.

  - **페더러드 사용자와의**   통신 사용   페더타 파트너 도메인에 대한 사용자 액세스를 지원하려면 이 옵션을 사용하도록 설정하세요. 이 설정은 사용자가 다른 SIP 페더니트 도메인뿐만 아니라 호스트된 공급자(Microsoft 365 또는 페더리트 도메인)와 통신할 Microsoft 365 Office 365. 


  - **원격 사용자와의 통신 사용**   방화벽 외부에 있는 조직 사용자(예: 재직자 및 출장하는 사용자)가 인터넷을 통해 비즈니스용 Skype 서버 수 있도록 하려는 경우 이 옵션을 사용하도록 설정하세요.

  - **공용 사용자와의**   통신 사용   내부 사용자가 공용 IM 공급자 연락처와 통신할 수 있도록 하려는 경우 이 옵션을 사용하도록 설정하세요.
   

> [!NOTE]  
> 외부 사용자 액세스 지원을 사용하도록 설정하는 것 외에도, 조직에서 외부 사용자 액세스 사용을 제어하는 정책을 구성해야 사용자들이 외부 사용자 액세스 유형을 사용할 수 있습니다. 외부 사용자 액세스를위한 정책 작성, 구성 및 적용에 대한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안함](../access-edge/enable-or-disable-remote-user-access.md)을 참조하세요.



**Windows PowerShell cmdlet을 사용하여 외부 액세스 정책을 보려면**

  - 비즈니스용 Skype 서버 관리 셸 및 **Get-CsExternalAccessPolicy** cmdlet을 사용하여 외부 액세스 정책을 볼 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 
    
    모든 외부 액세스 정책에 대한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력하고 Enter 키를 누릅니다.
    
    `Get-CsExternalAccessPolicy`
    
    이 명령은 다음과 비슷한 정보를 반환합니다.
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
