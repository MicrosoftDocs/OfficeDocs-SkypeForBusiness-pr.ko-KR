---
title: 비즈니스용 Skype 서버 제어판 관리자 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 비즈니스용 Skype 서버 2015에 대 한 액세스 권한을 부여 하려면 다음을 수행 합니다.
ms.openlocfilehash: 6fe5fee80921121c71ccdc4bb6e6de29ac4302fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197244"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>비즈니스용 Skype 서버 제어판 관리자 만들기
 
비즈니스용 Skype 서버 2015에 대 한 액세스 권한을 부여 하려면 다음을 수행 합니다.
  
1. Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.
    
2. **Active Directory 사용자 및 컴퓨터**를 열고 도메인을 확장한 다음 **사용자** 컨테이너를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.
    
3. **CSAdministrator 속성**에서 **구성원** 탭을 클릭합니다.
    
4. 구성원 탭에서 **추가**를 클릭합니다. **사용자, 연락처, 컴퓨터, 서비스 계정 또는 그룹 선택**에서 **선택할 개체 이름을 입력하십시오.** 를 찾습니다. CSAdministrators 그룹에 추가할 사용자 이름 또는 그룹 이름을 입력합니다. **확인**을 클릭합니다.
    
5. 구성원 탭에서 선택한 사용자 또는 그룹이 있는지 확인합니다. **확인**을 클릭합니다.
    
> [!TIP]
> 비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다. CsAdministrator 그룹의 구성원은 비즈니스용 Skype Server 제어판을 사용 하는 사용자에 게 사용할 수 있는 모든 구성 기능에 대 한 모든 권한을 제공 합니다. 특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다. 관리 그룹의 구성원으로 만들려면 비즈니스용 Skype 서버용으로 사용자를 설정 하지 않아도 됩니다. 
  
다른 역할은 다음과 같습니다.
  
- **Csarchiving:** 이 그룹의 구성원은 보관 서버 역할 구성 및 관리 등의 모든 보관 기능을 수행할 수 있습니다.
    
- **CsHelpDesk:** 이 그룹의 구성원은 사용자 속성 및 정책을 비롯한 구성과 배포를 볼 수 있습니다. 또한 구성원은 특정 문제 해결 작업을 수행할 수 있습니다.
    
- **CsLocationAdministrator:** 구성원은 E9-1-1(고급 9-1-1) 관리와 관련된 가장 낮은 수준의 사용자 권한을 가집니다. 구성원은 E9-1-1 위치 및 네트워크 식별자를 만들고 배포에서 이들을 연결할 수 있습니다.
    
- **CsResponseGroupAdministrator:** 구성원은 응답 그룹 서비스를 관리 및 구성할 수 있습니다.
    
- **Csserveradministrator:** 회원은 비즈니스용 Skype Server를 실행 하는 모든 서버를 관리 하 고 모니터링 하 고 문제를 해결할 수 있습니다.
    
- **CsUserAdministrator:** 구성원은 사용자를 관리하고, 사용자를 설정하거나 해제하고, 사용자에게 기존 정책을 할당할 수 있습니다.
    
- **Csviewadministrator:** 구성원은 서버 정보의 배포 및 구성을 볼 수 있습니다. 이 구성원 자격을 통해 구성원은 비즈니스용 Skype Server 2015을 실행 하는 서버의 상태를 모니터링할 수 있습니다.
    
- **CsVoiceAdministrator:** 회원은 비즈니스용 Skype 서버에서 음성 관련 설정을 만들고, 구성 하 고, 관리할 수 있습니다.
    
보안 및 역할 기반 액세스 제어 무결성을 유지 하려면 사용자가 비즈니스용 Skype Server 배포 관리에서 수행 하는 역할을 정의 하는 그룹에 사용자를 추가 합니다.
  

