---
title: 영구 채팅 추가 기능 기본 페이지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 영구 채팅 페이지의 추가 기능 섹션을 사용하여 URL을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 대화 extensibility 창의 대화방에 있는 클라이언트에 표시됩니다. 관리자는 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 채팅방 관리자/작성자는 채팅방을 등록된 추가 기능 중 하나와 연결해야 사용자가 클라이언트에서 이 업그레이드를 볼 수 있습니다.
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803798"
---
# <a name="persistent-chat-add-in-main-page"></a>영구 채팅 추가 기능 기본 페이지

영구 채팅  페이지의 추가 기능  섹션을 사용하여 URL을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 대화 extensibility 창의 대화방에 있는 클라이언트에 표시됩니다. 관리자는 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 채팅방 관리자/작성자는 채팅방을 등록된 추가 기능 중 하나와 연결해야 사용자가 클라이언트에서 이 업그레이드를 볼 수 있습니다.

추가 기능은 방 내의 환경을 확장하는 데 사용됩니다. 일반적인 추가 기능으로는 주식 시세 표시가 대화방에 게시될 때 가로채고 주식 기록을 Extensibility(Extensibility) 창에 표시하는 Silverlight 응용 프로그램을 지정하는 URL이 있을 수 있습니다. 또 다른 예로는 OneNote 2013 URL을 채팅방에 추가 기능으로 포함하여 "관심 항목" 또는 "오늘의 항목"과 같은 일부 공유 컨텍스트를 포함하는 경우를 들 수 있습니다.

영구 채팅방에 대한 추가 기능을 만들 경우 비즈니스용 Skype 서버 [2015에서](../../manage/persistent-chat/configure-add-ins.md)영구 채팅방에 대한 추가 기능 구성을 참조하세요. 영구 채팅 관리자인 경우 제어판이나 cmdlet을 사용하여 추가 기능을 만들 Windows PowerShell 있습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**추가 기능** 페이지에서는 다음 작업을 수행할 수 있습니다.

- [비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>채팅방에 대해 추가 기능을 구성하려면

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

1. CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 [Open Lync Server 관리 도구를 참조합니다.](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)

3. 왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **추가 기능** 을 클릭합니다.

    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.

4. **추가 기능** 페이지에서 **새로 만들기** 를 클릭합니다.

5. 서비스 **선택에서** 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다. 추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.

6. **새 추가 기능** 에서 다음을 수행합니다.

   - **이름** 에서 새 추가 기능의 이름을 지정합니다.

   - **URL** 에서 추가 기능과 연결할 URL을 지정합니다. http 및 https 프로토콜의 URL만 사용할 수 있습니다.

7. **커밋** 을 클릭합니다.

## <a name="see-also"></a>참고 항목

영구 채팅 서버 기능에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)영구 채팅 서버 계획, 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)영구 채팅 서버 배포 및 영구 채팅 서버 관리(비즈니스용 [Skype 서버 2015)를](../../manage/persistent-chat/persistent-chat.md)참조하세요.


