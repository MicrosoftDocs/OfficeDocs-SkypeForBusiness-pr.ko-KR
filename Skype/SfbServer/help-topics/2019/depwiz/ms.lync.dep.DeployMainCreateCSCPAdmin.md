---
title: 비즈니스용 Skype 서버 제어판 관리자 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 앱에 대한 액세스 권한을 비즈니스용 Skype 서버 다음을 합니다.
ms.openlocfilehash: 191149db88df737d0f20cdeb510bb03b4f17ddc40a4e85918240571a50ba5e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282161"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>비즈니스용 Skype 서버 제어판 관리자 만들기
 
앱에 대한 액세스 권한을 비즈니스용 Skype 서버 다음을 합니다.
  
1. Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.
    
2. **Active Directory 사용자 및 컴퓨터** 를 열고 도메인을 확장한 다음 **사용자** 컨테이너를 마우스 오른쪽 단추로 클릭하고 **속성** 을 클릭합니다.
    
3. **CSAdministrator 속성** 에서 **구성원** 탭을 클릭합니다.
    
4. 구성원 탭에서 **추가** 를 클릭합니다. **사용자, 연락처, 컴퓨터, 서비스 계정 또는 그룹 선택** 에서 **선택할 개체 이름을 입력하십시오.** 를 찾습니다. CSAdministrators 그룹에 추가할 사용자 이름 또는 그룹 이름을 입력합니다. **확인** 을 클릭합니다.
    
5. 구성원 탭에서 선택한 사용자 또는 그룹이 있는지 확인합니다. **확인** 을 클릭합니다.
    
> [!TIP]
> 비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다. CsAdministrator 그룹의 구성원 자격은 사용 가능한 모든 구성 기능에 대한 비즈니스용 Skype 서버 제어판을 사용하는 사용자에게 제공됩니다. 특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다. 사용자가 관리 그룹의 구성원으로 비즈니스용 Skype 서버 사용자에 대해 사용하도록 설정하지는 않습니다. 
  
기타 역할은 다음과 같습니다.
  
- **CsArchiving:** 이 그룹의 구성원은 보관 서버 역할 구성 및 관리와 같은 모든 보관 기능을 수행할 수 있습니다.
    
- **CsHelpDesk:** 이 그룹의 구성원은 사용자 속성 및 정책을 비롯한 구성과 배포를 볼 수 있습니다. 또한 구성원은 특정 문제 해결 작업을 수행할 수 있습니다.
    
- **CsLocationAdministrator:** 구성원은 E9-1-1(고급 9-1-1) 관리와 관련된 가장 낮은 수준의 사용자 권한을 가집니다. 구성원은 E9-1-1 위치 및 네트워크 식별자를 만들고 배포에서 이들을 연결할 수 있습니다.
    
- **CsResponseGroupAdministrator:** 구성원은 응답 그룹 서비스를 관리 및 구성할 수 있습니다.
    
- **CsServerAdministrator:** 구성원은 모든 서버에서 실행되는 모든 서버를 관리, 모니터링 및 비즈니스용 Skype 서버.
    
- **CsUserAdministrator:** 구성원은 사용자를 관리, 사용하도록 설정 및 사용하지 않도록 설정하고 사용자에게 기존 정책을 할당할 수 있습니다.
    
- **CsViewOnlyAdministrator:** 구성원은 서버 정보의 배포 및 구성을 볼 수 있습니다. 이 멤버 자격을 사용하면 구성원이 구성원 자격으로 실행 중인 서버의 비즈니스용 Skype 서버.
    
- **CsVoiceAdministrator:** 구성원은 사용자 계정에서 음성 관련 설정을 만들고 구성하고 관리할 수 비즈니스용 Skype 서버.
    
보안 및 역할 기반 액세스 제어 무결성을 유지하도록 지원하기 위해 사용자가 보안 배포를 관리하기 위해 수행하는 역할을 정의하는 그룹에 사용자를 비즈니스용 Skype 서버 합니다.
  

