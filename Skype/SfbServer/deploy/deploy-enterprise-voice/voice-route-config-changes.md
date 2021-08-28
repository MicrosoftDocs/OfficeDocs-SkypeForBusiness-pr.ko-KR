---
title: 음성 라우팅 구성에 보류 중인 변경 내용을 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소하는 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 2873520be0b5f7709fb493912be18afa807884c2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583192"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>음성 라우팅 구성에 보류 중인 변경 내용을 비즈니스용 Skype
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소하는 비즈니스용 Skype 서버 방법을 참조합니다.
  
**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후 다음 절차를 수행하여 대기 중인 변경 내용을 검토, 게시 또는 취소할 수 있습니다.
  
> [!IMPORTANT]
> 한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정하도록 해야 합니다. 
  
> [!NOTE]
> 대기 중인 모든 변경 내용은 **모두 커밋** 명령을 실행하여 동시에 게시되어야 합니다. 대기 중인 변경 내용을 선택해서 게시할 수 없습니다. 대기 중인 변경 내용을 게시하기 전에 **커밋되지 않은 변경 내용 검토** 명령을 실행하고 게시하지 않을 구성 변경 내용을 모두 취소합니다.
  
> [!NOTE]
> 대기 중인 변경 내용을 커밋하기 전에 **음성 라우팅** 그룹의 페이지에서 이동할 경우 대기 중인 모든 변경 내용이 손실됩니다. 단, 대기 중인 모든 변경 사항을 비롯한 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트된 구성을 가져오고 게시할 수 있습니다. 자세한 내용은 음성 경로 구성 파일 [내보내기](voice-route-configuration-import-export.md)또는 가져오기 를 비즈니스용 Skype. 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 **CsVoiceAdministrator, CsServerAdministrator** 또는 **CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **음성 라우팅** 그룹의 각 페이지에서 구성 설정을 원하는 대로 변경합니다.
    
5. 대기 중인 변경 내용을 게시하지 않고 검토하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토** 를 선택합니다.
    
6. 대기 중인 변경 내용을 취소하려면 다음 중 하나를 수행합니다.
    
   - **커밋** 메뉴에서 **커밋되지 않은 모든 변경 내용 취소** 를 선택합니다.
    
   - 취소할 대기 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동하고 대기 중인 변경 내용이 포함된 항목을 선택한 후 **커밋**, **선택한 변경 내용 취소** 를 차례로 클릭합니다.
    
7. 대기 중인 변경 내용을 모두 검토하고 게시하지 않을 변경 내용을 취소했으면 **커밋**, **모두 커밋** 을 차례로 클릭합니다.
    
8. 대기 중인 모든 변경 내용에 대한 목록이 표시되는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인** 을 클릭합니다. 
    
    제어판에서 비즈니스용 Skype 서버 커밋하면 성공적으로 게시된 음성 라우팅 구성 **메시지가** 나타납니다.
    

