---
title: 2015에서 영구 채팅 관리자 비즈니스용 Skype 서버 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '요약: 이 항목을 통해 영구 채팅 서버 관리자 역할을 만들어 2015년 비즈니스용 Skype 서버 영구 채팅 서비스의 초기 구성 및 관리를 사용하도록 설정할 수 있습니다.'
ms.openlocfilehash: bf534f937282aa90d7d66e2de9893f075a351251
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601873"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>2015에서 영구 채팅 관리자 비즈니스용 Skype 서버 만들기
 
**요약:** 이 항목을 통해 영구 채팅 서버 관리자 역할을 만들어 2015년 8월에 영구 채팅 서비스의 초기 구성 및 관리를 비즈니스용 Skype 서버 있습니다.
  
이 비즈니스용 Skype 서버 작업을 수행하는 사용자는 하나 이상의 특정 그룹의 구성원으로 할당되어야 합니다. Role-Based 액세스 제어(RBAC)는 미리 정의한 관리 역할에 사용자를 할당하여 비즈니스용 Skype 서버 사용됩니다. 이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당합니다. 영구 채팅 관리자 보안 그룹의 구성원인 CsPersistentChatAdministrator는 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 제어판을 사용하여 실행할 수 있는 영구 채팅 서버 cmdlet에 액세스할 수 있습니다.
  
영구 채팅 서버를 구성 및 관리하기 전에 적절한 사용자 권한 및 사용 권한이 설정되고 영구 채팅 관리자 역할을 할 모든 사용자가 영구 채팅 관리자 보안 그룹에 추가해야 합니다.
  
> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.

## <a name="create-a-persistent-chat-administrator"></a>영구 채팅 관리자 만들기

영구 채팅 관리자 보안 그룹인 CsPersistentChatAdministrator에 사용자를 추가하기 위해 다음 단계를 수행합니다.
  
1. Active Directory 그룹의 구성원 자격을 수정할 수 있는 권한이 있는 계정을 사용하여 Active Directory 사용자 및 컴퓨터가 설치된 컴퓨터에 로그온합니다.
    
2. 시작, 모든 프로그램, 관리 도구를 클릭한 다음 Active Directory 사용자 및 컴퓨터를 클릭합니다.
    
3. Active Directory 사용자 및 컴퓨터에서 도메인 이름을 확장하고 사용자 컨테이너를 클릭합니다.
    
4. 보안 그룹 CsPersistentChatAdministrator를 마우스 오른쪽 단추로 클릭한 다음 속성을 클릭합니다.
    
5. 속성 대화 상자의 구성원 탭에서 추가를 클릭합니다.
    
6. 사용자, 컴퓨터, 연락처 또는 그룹 선택 대화 상자의 선택할 개체 이름 입력 상자에 그룹에 추가할 사용자의 이름 또는 표시 이름을 입력한 다음 확인을 클릭합니다.
    
7. 속성 대화 상자에서 확인을 클릭합니다.
    

