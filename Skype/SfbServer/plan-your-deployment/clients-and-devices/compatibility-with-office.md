---
title: Office 앱과 비즈니스용 Skype 호환성
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Outlook 및 기타 Microsoft Office 응용 프로그램에서 비즈니스용 Skype 기능에 액세스 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187899"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Office 앱과 비즈니스용 Skype 호환성
 
Outlook 및 기타 Microsoft Office 응용 프로그램에서 비즈니스용 Skype 기능에 액세스 하는 방법에 대해 알아봅니다.
  
이 항목에서는 다양 한 버전의 Microsoft Office 제품군과 함께 비즈니스용 Skype의 호환성에 대해 설명 합니다. 
  
## <a name="office-and-skype-for-business"></a>Office 및 비즈니스용 Skype

다음 표에서는 exchange가 배포 된 후 여러 버전의 Office에서 지원 되는 비즈니스용 Skype 기능에 대해 설명 하 고 비즈니스용 [Skype 서버와의 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
**비즈니스용 Skype 및 Microsoft Office 호환성**

|**요소**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 및 2016**|**Mac 용 Office 2016** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 기능** ||||
|Outlook 모임 초대 사용자 지정 (로고 추가, 도움말 URL, 고 지 사항, 바닥글 텍스트)  |아니요  |'   |'|
|기본적으로 참석자 오디오 및 비디오를 음소거 하는 모임 구성 옵션    |아니요    |'    |아니요    |
|Office 및 비즈니스용 Skype에서 연락처 목록을 관리 하는 통일 된 대화 상대 저장소    |아니요    |예 (Exchange 2013 이상을 필요 합니다.)    |'    |
|고해상도 프로필 사진    |아니요    |예 (Exchange 2013 이상을 필요 합니다.)    |'    |
|Microsoft Outlook 보낸 사람, 받는 사람, 참조 필드의 현재 상태    |'    |'    |'    |
|사용 가능 시간 메뉴에서 메신저 대화 또는 통화와 함께 회신    |예 (대화 상대 카드에서)    |예 (대화 상대 카드에서)    |예 (대화 상대 카드에서)    |
|일정 정리 탭의 모임 요청에 있는 현재 상태    |'    |'    |아니요    |
|받은 전자 메일 메시지의 도구 모음 또는 리본에서 메신저 대화 또는 통화와 함께 회신    |'    |'    |'    |
|**다른 Office 앱**   ||||
|OneNote 공유 메모    |아니요    |'    |아니요    |
|Office 설치 프로그램에 통합 된 설정    |아니요    |'    |아니요    |
|PowerPoint 프레젠테이션 콘텐츠    |'    |예 (VBSS도 사용할 수 있음)    |'    |
|Microsoft Word 및 Microsoft Excel 파일의 메신저 대화 및 현재 상태 (스마트 태그 사용 가능)    |Microsoft Word만    |Microsoft Word만    |아니요    |
|Microsoft SharePoint 사이트의 메신저 대화 및 현재 상태 (Outlook이 설치 되어 있어야 함)    |'    |'    |아니요    |
   
&#x2776;-현재 사용자가 설치 되어 있고 Mac 클라이언트에서 비즈니스용 Skype를 실행 중이거나 Mac 용 Lync 2011 클라이언트를 사용 하 고 있다고 가정 합니다.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 및 비즈니스용 Skype

다음 표에서는 다양 한 버전의 Exchange Server에 대 한 비즈니스용 Skype 지원에 대해 설명 합니다. Outlook은 확장 MAPI 호출을 처리 하기 위해 클라이언트 컴퓨터에 설치 해야 하며, 일부 기능에는 EWS (Exchange Web Services)를 사용 해야 합니다.
  
**비즈니스용 Skype 및 Exchange Server 호환성**

|**Exchange Server 버전**|**비즈니스용 Skype 지원**|
|:-----|:-----|
|Exchange Server 2019 (비즈니스용 Skype Server 2019에만 해당) |Exchange Server 2013 지원과 같음    |
|Exchange Server 2016    |Exchange Server 2013 지원과 같음  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010와 동일 하며, 추가 기능으로  <br/>&bull;&nbsp;&nbsp;통합 된 대화 상대 저장소  <br/>&bull;&nbsp;&nbsp;고해상도 그림  <br/>&bull;&nbsp;&nbsp;아카이빙 통합  <br/> **참고:** 자세한 내용은 [Exchange server와 비즈니스용 Skype 서버 통합](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)을 참조 하세요.  <br/> |
|Exchange Server 2010  <br/>(비즈니스용 Skype Server 2015에만 해당) |다음 기능은 EWS를 통해서만 사용할 수 있습니다.  <br/>&bull;&nbsp;&nbsp;대화 내용 폴더에서 항목 읽기 또는 삭제  <br/>&bull;&nbsp;&nbsp;음성 메일 항목 읽기 또는 삭제  <br/>&bull;&nbsp;&nbsp;확장 된 약속 있음/없음 정보 및 모임 제목 및 위치 표시  <br/>&bull;&nbsp;&nbsp;Exchange 연락처 동기화  <br/> Exchange Server 2010에서 공용 폴더는 선택 사항입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목
 
[Windows 클라이언트 요구 사항 및 소프트웨어 지원](windows-requirements.md)
  
[모임 클라이언트 계획 (웹 앱 및 모임 앱)](meetings-clients.md)

