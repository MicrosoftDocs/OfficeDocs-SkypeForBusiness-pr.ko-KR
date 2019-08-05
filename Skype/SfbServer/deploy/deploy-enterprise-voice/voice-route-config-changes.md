---
title: 비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '요약: 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 1ff33dee1518581e4a94aac56ecae34d9bfd1159
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197147"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시
 
**요약:** 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하는 방법에 대해 알아봅니다.
  
**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후에는이 절차를 수행 하 여 보류 중인 변경 내용을 검토 하거나 게시 하거나 취소 합니다.
  
> [!IMPORTANT]
> 한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정 하도록 합니다. 
  
> [!NOTE]
> 보류 중인 모든 변경 내용은 **모두 커밋** 명령을 실행 하 여 동시에 게시 해야 합니다. 보류 중인 변경 내용을 선택적으로 게시할 수 없습니다. 보류 중인 변경 내용을 게시 하기 전에 **커밋되지 않은 변경 내용 검토** 명령을 실행 하 고 게시 하지 않으려는 구성 변경 내용을 취소 합니다.
  
> [!NOTE]
> 보류 중인 변경 내용을 커밋하기 전에 **음성 라우팅** 그룹의 페이지에서 다른 위치로 이동 하면 보류 중인 변경 내용이 모두 손실 됩니다. 그러나 보류 중인 변경 내용을 포함 하 여 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트 된 구성을 가져오고 게시할 수 있습니다. 자세한 내용은 [비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기를](voice-route-configuration-import-export.md)참조 하세요. 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.
    
4. **음성 라우팅** 그룹의 각 페이지에 대 한 설정을 원하는 대로 변경 합니다.
    
5. 보류 중인 변경 내용을 게시 하지 않고 검토 하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토** 를 선택 합니다.
    
6. 보류 중인 변경 내용을 취소 하려면 다음 중 하나를 수행 합니다.
    
   - **커밋** 메뉴에서 **커밋되지 않은 변경 내용 모두 취소** 를 선택 합니다.
    
   - 취소 하려는 보류 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동 하 고 보류 중인 변경 내용이 있는 항목을 선택한 다음 **커밋을**클릭 하 고 **선택한 변경 내용 취소**를 클릭 합니다.
    
7. 보류 중인 변경 내용을 모두 검토 하 고 게시 하지 않으려는 작업을 취소 한 후에는 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
8. 모든 보류 중인 변경 내용 목록을 표시 하는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다. 
    
    비즈니스용 Skype Server 제어판에서 변경 내용이 커밋되면 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 나타납니다.
    

