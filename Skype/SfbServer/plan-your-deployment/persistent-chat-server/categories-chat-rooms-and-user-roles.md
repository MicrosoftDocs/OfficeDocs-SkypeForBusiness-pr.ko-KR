---
title: '비즈니스용 Skype 서버 2015의 영구 채팅 범주, 채팅방 및 사용자 역할'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: '요약: 이 항목을 통해 2015년 8월 영구 채팅 서버의 범주, 채팅방 및 사용자 및 관리자 역할에 비즈니스용 Skype 서버 있습니다.'
---

# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 영구 채팅 범주, 채팅방 및 사용자 역할
 
**요약:** 이 항목을 통해 2015년 8월 영구 채팅 서버의 범주, 채팅방 및 사용자 및 관리자 역할에 비즈니스용 Skype 서버 있습니다.
  
채팅방 범주를 만들고 범주 내의 범주 및 채팅방에 대한 액세스를 지정하여 채팅방에 대한 액세스를 제어할 수 있습니다. 또한 다양한 관리자 역할을 지정할 수 있습니다. 이 항목에서는 다음에 대해 설명합니다. 
  
- 채팅방 구성 범주
    
- 채팅방 및 사용자 역할
    
- 관리자 역할

> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요](/microsoftteams/upgrade-start-here). 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 
    
## <a name="categories-for-organizing-chat-rooms"></a>채팅방 구성 범주

범주를 사용하면 채팅방을 구성하고 해당 범주 내에서 채팅방을 만들거나 참가할 수 있는 사용자 및 그룹을 제어할 수 있습니다. 각 범주에는 범주 내의 채팅방에 사용할 수 있는 옵션을 결정하는 관련 속성이 있습니다. 특정 범주에 대한 액세스를 제어하기 위해 사용자가 액세스 허용인지 거부인지를 지정합니다.
  
허용 구성원과 거부 구성원 개념의 기본 근거는 강성적 벽입니다. 예를 들어 은행과 금융 기관은 정책 및 규칙을 구현하는 동안 거래자와 분석가들의 통신 내용 공유를 금지하는 교신 차단 경계를 설정할 수 있습니다. 이 요구 사항을 충족하기 위해 관리자는 여러 범주를 만들어 한 범주에서는 거래자들이 방을 작성 및 사용하도록 허용하고 다른 범주에서는 분석가들이 방을 작성 및 사용하도록 허용할 수 있습니다. 상위 범주에서 차단하는 경우 사용자를 채팅방의 구성원으로 추가할 수 없습니다.
  
> [!IMPORTANT]
> 범주의 허용 구성원과 거부 구성원은 영구 채팅방에 적용되는 구성원 역할  과는 다를 수 있습니다.> 검색을 수행하는 사용자가 허용 및 거부 구성원 목록에 있는 열려 있는 대화방과 닫힌 대화방이 모두 표시됩니다. 비밀 채팅방은 검색 수행 사용자가 해당 방의 구성원이 아니면 표시되지 않습니다. 사용자는 자신이 구성원으로 속해 있거나 구성원 자격을 요청할 수 있는 방만 검색할 수 있습니다. 
  
## <a name="chat-rooms-and-user-roles"></a>채팅방 및 사용자 역할

범주에 대해 허용 및 거부 구성원 외에도 작성자, 관리자, 구성원 및 발표자 사용자 역할을 지정하여 채팅방에 대한 액세스를 제어할 수 있습니다.
  
- **작성** 자: 채팅방을 만들 수 있는 권한이 있는 사용자입니다. 이러한 사용자는 특정 범주의 작성자 목록에 있습니다. 즉, 해당 범주에서 채팅방을 만들 수 있으며 범주에 따라 구성원을 할당하고 관리자를 할당하여 채팅방을 관리할 수도 있습니다. 대화방을 만드는 사용자는 자동으로 채팅방의 관리자로 추가됩니다.
    
    > [!NOTE]
    > 작성자에게는 단순히 채팅방 작성 권한만 제공됩니다. 작성자가 작성된 채팅 서비스에서 구체적인 구성원 자격, 관리자 등을 추가로 지정할 수 있도록 하기 위해 관리자로 자동 승격되는 것입니다. 
  
    이 역할은 조직에서 채팅방을 작성하는 사람을 제어하는 옵션을 제공하며, 특히 채팅방 만들기를 중앙에서 관리하여 정책과 규칙을 적용하고 이후에 채팅방 관리 권한을 조직의 다른 사용자에게 위임하려는 경우에 사용됩니다.
    
- **관리자(manager)**: 채팅방의 속성을 관리하는 사용자입니다. 채팅방 관리자는 구성원 목록을 수정(구성원 추가/제거)하고 채팅방 관리자 목록을 수정(관리자 추가/제거)할 수 있습니다. 채팅방 관리자는 채팅방에 참가할 수 있도록 자신을 구성원 또는 발표자(강당 채팅방의 경우) 목록에 추가할 수 있습니다. 또한 채팅방을 사용하지 않도록 설정할 수도 있습니다(관리자(administrator)가 사용하지 않도록 설정된 채팅방을 쿼리하여 영구적으로 삭제할 수 있음). 관리자는 채팅방 범주를 제외한 모든 채팅방 속성을 변경할 수 있습니다. 채팅방을 만든 후 영구 채팅 관리자만 범주를 변경할 수 있습니다.
    
    > [!IMPORTANT]
    > 다른 범주의 작성자이기도 한 관리자는 해당 범주를 자신이 방을 만들 권한이 있는 범주로 변경할 수 있습니다. 
  
- **구성원**: 채팅방의 구성원인 사용자입니다. 이러한 사용자는 디렉터리의 채팅방(비밀 채팅방 포함)을 보고 채팅방을 구독할 수 있으며(읽지 않은 메시지, 본인 검색 필터 및 키워드 필터와 같은 메타데이터 옵션도 포함됨) 채팅방에 참가할 수 있습니다(발표자만 게시, 콘텐츠 가져오기, 검색을 수행할 수 있는 강당 채팅방을 제외하고는 게시 가능). 채팅방의 구성원이 아닌 사용자는 범주의 허용 구성원 목록에 있는 경우 채팅방을 검색할 수 있지만 콘텐츠에 액세스하려면 이러한 채팅방에 참가하기 위한 액세스를 요청해야 합니다. 시스템에서 기본적으로 제공되는 요청 액세스 또는 승인 기능은 없으며, 이러한 작업은 전자 메일/전화/기타 연락 형식을 통해 외부적으로 수행됩니다.
    
- **발표자**: 강당 채팅방에 게시를 할 수 있는 사용자입니다.
    
## <a name="administrator-roles"></a>관리자 역할

영구 채팅 서버에 대한 관리자 역할은 다음과 같습니다.
  
- **영구** 채팅 관리자: 영구 채팅 관리자 역할은 채팅방을 관리할 수 있으며(구성원 자격, 관리자, 범주를 비롯한 모든 속성을 수정하고 방을 사용할 수 없는 것으로 표시) 채팅방을 만들고 액세스할 수 있는 사용자 정의 채팅방 범주를 만들고 관리할 수 있습니다. 또한 관리자는 채팅방을 사용할 수 없도록 표시하고 더 이상 사용되지 않는 채팅방을 정리할 수 있습니다. 관리자에게는 작성자 또는 허용 구성원의 제한이 적용되지 않습니다. 관리자는 어떤 종류의 채팅방이든 만들 수 있으며 모든 채팅방에 자신을 구성원으로 추가할 수 있습니다. 관리자는 영구 채팅 구성(풀 속성, 전역 설정 및 준수 구성)을 수정하고 관리할 수 있으며, 이전 그룹 채팅 서버 배포에서 비즈니스용 Skype 서버 2015 영구 채팅 서버로 마이그레이션을 계획하고 구현할 수도 있습니다.
    
    영구 채팅 관리자는 영구 채팅 서버가 Windows PowerShell 컴퓨터의 원격 cmdlet을 사용하여 영구 채팅 서버를 관리할 수 있습니다. 영구 채팅 서버는 영구 채팅 관리자가 영구 채팅 서버 프런트 엔드 서버에서 RTC 로컬 관리자 로컬 그룹의 구성원인지 검사합니다.
    
- **비즈니스용 Skype 서버 2015 관리자**: 배포를 담당하는 비즈니스용 Skype 서버 2015의 전체 엔터프라이즈 관리자입니다.
    
- **작업 관리자**: 일상적인 작업 관리를 담당하는 사용자입니다.
    
- **타사 개발자 및 관리자**: 타사 개발자는 시스템을 확장하고, 특히 그룹 대화용 교신 차단 영역 솔루션, 준수 지원 및 도구, 웹/모바일 클라이언트 및 봇 개발용 프레임워크를 제공합니다.
    
## <a name="for-more-information"></a>자세한 내용

채팅방 및 사용자 역할을 구성 및 관리하는 데 대한 자세한 내용은 다음 항목을 참조하십시오.
  
- [2015에서 영구 채팅 관리자 비즈니스용 Skype 서버 만들기](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 범주 관리](../../manage/persistent-chat/categories.md)
    
- [2015년 비즈니스용 Skype 서버 영구 채팅 서버에서 채팅방 관리](../../manage/persistent-chat/chat-rooms.md)
    

