---
title: 영구 채팅 추가 기능
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 영구 채팅 페이지의 추가 기능 섹션을 사용 하 여 Url을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 클라이언트에서 채팅방의 대화 확장성 창에 표시됩니다. 관리자가 등록된 추가 기능 목록에 추가 기능을 추가하고, 채팅방 관리자/생성자가 등록된 추가 기능 중 하나와 채팅방을 연결해야 사용자가 클라이언트에서 이 업그레이드를 확인할 수 있습니다.
ms.openlocfilehash: da971a43c8e113dc1fff8ee9dc600f55a2fea955
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686221"
---
# <a name="persistent-chat-add-in"></a>영구 채팅 추가 기능

**영구 채팅** 페이지의 **추가 기능** 섹션을 사용 하 여 url을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 클라이언트에서 채팅방의 대화 확장성 창에 표시됩니다. 관리자가 등록된 추가 기능 목록에 추가 기능을 추가하고, 채팅방 관리자/생성자가 등록된 추가 기능 중 하나와 채팅방을 연결해야 사용자가 클라이언트에서 이 업그레이드를 확인할 수 있습니다.

추가 기능은 채팅방 내 환경을 확장하기 위해 사용됩니다. 일반적인 추가 기능에는 주식 시세 표시기가 채팅방에 게시 되는 경우를 가로채는 Silverlight 응용 프로그램을 가리키는 URL이 포함 될 수 있으며, 확장성 창에 주식 기록이 표시 됩니다. 다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.

영구 채팅방 용 추가 기능을 만들려면 비즈니스용 [Skype 서버 2015에서 영구 채팅방에 대 한 추가 기능 구성을](../../manage/persistent-chat/configure-add-ins.md)참조 하세요. 영구 채팅 관리자 인 경우 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 추가 기능을 만들 수 있습니다.

## <a name="tasks-that-you-can-perform"></a>수행할 수 있는 작업

**추가 기능** 페이지에서는 다음 작업을 수행할 수 있습니다.

- [영구 채팅방에 대해 추가 기능 구성](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>채팅방의 추가 기능을 구성하려면

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2. **시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)를 참조하세요.

3. 왼쪽 탐색 모음에서 **영구 채팅**을 클릭한 다음 **추가 기능**을 클릭합니다.

    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.

4. **추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.

5. **서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 추가 기능은 한 풀에서 다른 풀로 이동하거나 여러 풀 간에 공유할 수 없습니다.

6. **새 추가 기능**에서 다음을 수행합니다.

   - **이름**에 새 추가 기능 이름을 지정합니다.

   - **URL**에 추가 기능과 연결할 URL을 지정합니다. URL은 http 및 https 프로토콜로 제한됩니다.

7. **커밋**을 클릭합니다.

## <a name="see-also"></a>참고 항목

영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 비즈니스용 skype Server 2015의 영구 채팅 서버에 [대 한 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), 비즈니스용 [skype Server 2015의 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)및 비즈니스용 [Skype Server 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md)를 참조 하세요.


