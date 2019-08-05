---
title: 조직에 대한 외부 액세스 정책 관리
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.
ms.openlocfilehash: 014077fb331bc33933d0c673771f7765b9341570
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188808"
---
# <a name="manage-external-access-policy-for-your-organization"></a>조직에 대한 외부 액세스 정책 관리

하나 이상의 Edge 서버를 배포한 후에는 조직에 대해 지원 되는 외부 액세스 유형을 사용 하도록 설정 해야 합니다.

기본적으로 조직에 대해 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 외부 사용자 액세스를 지원 하도록 구성 된 정책은 없습니다. 외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다. 다음 정책 범위를 만들고 구성할 수 있습니다. 기본적으로 전역 정책은 만들어지지만 삭제할 수는 없습니다.

  - **전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다. 기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다. 전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다. 전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다. 전역 정책을 삭제 해도 제거 되지 않습니다. 대신 기본 설정으로 다시 설정 합니다.

  - **사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다. 예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.

  - **사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다. 예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.


> [!IMPORTANT]  
> 하나의 정책 수준에서 적용 되는 정책 설정이 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.


이러한 옵션에는 다음과 같은 외부 액세스 유형이 포함 됩니다.

  - **페더레이션 사용자**   와의 통신 사용 페더레이션 파트너 도메인에 대 한 사용자 액세스를 지원 하려면이 기능을 사용 하도록 설정 합니다. 이 설정을 사용 하면 사용자가 다른 SIP 페더레이션 도메인과 통신 하는 기능 뿐만 아니라 Microsoft Office 365와 같은 호스트 공급자도 연결할 수 있습니다. 


  - **원격 사용자**   와 통신 설정 방화벽 외부에 있는 사용자 (예: 출장 중인 가정용 사용자)와 인터넷을 통해 비즈니스용 Skype 서버에 연결할 수 있도록 하려면이 옵션을 선택 합니다.

  - **공용 사용자**   와 통신 사용 내부 사용자가 공용 IM 공급자 연락처와 통신할 수 있도록 하려면이 옵션을 사용 하도록 설정 합니다.
   

> [!NOTE]  
> 외부 사용자 액세스 지원을 사용 하도록 설정 하는 것 외에도 사용자가 모든 종류의 외부 사용자 액세스를 사용할 수 있으려면 먼저 조직의 외부 사용자 액세스 사용을 제어 하는 정책을 구성 해야 합니다. 외부 사용자 액세스에 대 한 정책 만들기, 구성, 적용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](../access-edge/enable-or-disable-remote-user-access.md)참조 하세요.



**Windows PowerShell cmdlet을 사용 하 여 외부 액세스 정책을 보려면**

  - 비즈니스용 Skype Server Management Shell 및 **CsExternalAccessPolicy** cmdlet을 사용 하 여 외부 액세스 정책을 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 
    
    모든 외부 액세스 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
    `Get-CsExternalAccessPolicy`
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
