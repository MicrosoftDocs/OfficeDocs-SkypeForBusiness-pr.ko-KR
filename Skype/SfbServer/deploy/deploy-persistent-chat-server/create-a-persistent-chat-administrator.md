---
title: 영구 채팅 관리자 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 요약:이 항목을 읽으면 비즈니스용 Skype Server 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용 하도록 설정 하는 영구 채팅 서버 관리자 역할을 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3692169a65d73c3951ce58e77b132a4f118c54e9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239772"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>영구 채팅 관리자 만들기
 
**요약:** 이 항목을 읽으면 비즈니스용 Skype Server 2015에서 영구 채팅 서비스의 초기 구성 및 관리를 사용 하도록 설정 하는 영구 채팅 서버 관리자 역할을 만드는 방법을 알아보세요.
  
비즈니스용 Skype Server에서 특정 작업을 수행 하는 사용자는 하나 이상의 특정 그룹의 구성원으로 할당 되어야 합니다. 사용자를 미리 정의 된 비즈니스용 Skype 서버 관리 역할에 할당 하 여 권한을 부여 하는 데는 RBAC (역할 기반 액세스 제어)가 사용 됩니다. 이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당 합니다. 영구 채팅 관리자 보안 그룹의 구성원에 게는 비즈니스용 skype 서버 관리 셸 또는 비즈니스용 Skype를 사용 하 여 실행할 수 있는 영구 채팅 서버 cmdlet에 대 한 액세스 권한이 부여 됩니다. CsPersistentChatAdministrator 서버 제어판.
  
영구 채팅 서버를 구성 하 고 관리 하기 전에 적절 한 사용자 권한 및 사용 권한이 있는지 확인 하 고 영구 채팅 관리자의 역할을 하는 사용자가 영구 채팅 관리자 보안 그룹에 추가 되어야 합니다.
  
> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.

## <a name="create-a-persistent-chat-administrator"></a>영구 채팅 관리자 만들기

영구 채팅 관리자 보안 그룹 CsPersistentChatAdministrator에 사용자를 추가 하려면 다음 단계를 수행 합니다.
  
1. Active Directory 그룹의 구성원 자격을 수정할 권한이 있는 계정을 사용 하 여 Active Directory 사용자 및 컴퓨터가 설치 된 컴퓨터에 로그온 합니다.
    
2. 시작을 클릭 하 고 모든 프로그램을 클릭 한 다음 관리 도구를 클릭 하 고 Active Directory 사용자 및 컴퓨터를 클릭 합니다.
    
3. Active Directory 사용자 및 컴퓨터에서 도메인의 이름을 확장 하 고 사용자 컨테이너를 클릭 합니다.
    
4. 보안 그룹 CsPersistentChatAdministrator을 마우스 오른쪽 단추로 클릭 한 다음 속성을 클릭 합니다.
    
5. 속성 대화 상자의 구성원 탭에서 추가를 클릭 합니다.
    
6. 사용자, 컴퓨터, 연락처 또는 그룹 선택 대화 상자에서 선택할 개체 이름 입력 상자에 그룹에 추가할 사용자의 사용자 이름 또는 표시 이름을 입력 하 고 확인을 클릭 합니다.
    
7. 속성 대화 상자에서 확인을 클릭 합니다.
    

