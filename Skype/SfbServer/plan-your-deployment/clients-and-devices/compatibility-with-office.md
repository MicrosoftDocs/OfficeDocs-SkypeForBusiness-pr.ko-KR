---
title: 비즈니스용 Skype 앱과의 Office 호환성
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 응용 프로그램 및 기타 응용 프로그램에서 비즈니스용 Skype 기능에 액세스할 Outlook 방법을 Microsoft Office 이해합니다.
ms.openlocfilehash: e4b826cf6ba79b8db31ec5dec57c8d6bfca5280f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773568"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>비즈니스용 Skype 앱과의 Office 호환성
 
응용 프로그램 및 기타 응용 프로그램에서 비즈니스용 Skype 기능에 액세스할 Outlook 방법을 Microsoft Office 이해합니다.
  
이 항목에서는 다양한 버전의 비즈니스용 Skype 제품군과의 호환성을 Microsoft Office 설명합니다. 
  
## <a name="office-and-skype-for-business"></a>Office 비즈니스용 Skype

다음 표에서는 비즈니스용 Skype와 통합에 설명된 비즈니스용 Skype 통합에 설명된 Office 배포 및 통합된 Office Exchange 버전에서 지원하는 비즈니스용 Skype 서버 [Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
**비즈니스용 Skype 및 Microsoft Office 호환성**

|**기능**|**Microsoft Office 2010**|**Microsoft Office, 2015 및 2016**|**Mac용 Office 2016** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 기능** ||||
|모임 Outlook 사용자 지정(로고 추가, 도움말 URL, 고지서, 발자국 텍스트 추가)  |아니오  |예   |예|
|기본적으로 참석자 오디오 및 비디오를 음소거하도록 모임 옵션 구성    |아니요    |예    |아니요    |
|통합 연락처 저장소에서 연락처 목록을 관리하기 위한 Office 비즈니스용 Skype    |아니요    |예(Exchange 2013 이상 필요)    |예    |
|고해상도 프로필 사진    |아니요    |예(Exchange 2013 이상 필요)    |예    |
|Microsoft Outlook, 시작 및Cc 필드의 현재 상태    |예    |예    |예    |
|IM으로 회신 또는 가용성 메뉴에서 전화 걸기    |예(대화 상대 카드에서)    |예(대화 상대 카드에서)    |예(대화 상대 카드에서)    |
|일정 정리 탭의 모임 요청의 현재 상태    |예    |예    |아니요    |
|받은 전자 메일 메시지의 도구 모음 또는 리본 메뉴에서 IM으로 회신 또는 전화 걸기    |예    |예    |예    |
|**기타 Office 앱**   ||||
|OneNote 메모    |아니오    |예    |아니요    |
|설치 프로그램에 통합된 Office 프로그램    |아니오    |예    |아니요    |
|PowerPoint 프레젠테이션 콘텐츠    |예    |예(VBSS도 사용 가능)    |예    |
|Microsoft Word 및 Microsoft Excel 파일(스마트 태그 사용)의 IM 및 현재 상태    |Microsoft Word 전용    |Microsoft Word 전용    |아니요    |
|Microsoft SharePoint 사이트(Outlook이 설치되어 있어야 함)의 IM 및 현재 상태    |예    |예    |아니요    |
   
&#x2776; - Mac 클라이언트 또는 Lync 2011 for Mac 클라이언트에서 비즈니스용 Skype 설치했다고 가정합니다.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 비즈니스용 Skype

다음 표에서는 다양한 비즈니스용 Skype 버전에 대한 지원에 대해 Exchange Server. 확장 MAPI 통화를 처리하려면 클라이언트 컴퓨터에 Outlook을 설치해야 하며 일부 기능의 경우 EWS(Exchange 웹 서비스)를 사용해야 합니다.
  
**비즈니스용 Skype 및 Exchange Server 호환성**

|**Exchange Server 버전**|**비즈니스용 Skype 지원**|
|:-----|:-----|
|Exchange Server 2019(비즈니스용 Skype 서버 2019만 해당) |2013 Exchange Server 동일    |
|Exchange Server 2016    |2013 Exchange Server 동일  <br/> |
|Exchange Server 2013  <br/> |추가 Exchange Server 2010 지원과 동일  <br/>&bull;&nbsp;&nbsp;통합 연락처 저장소  <br/>&bull;&nbsp;&nbsp;고해상도 그림  <br/>&bull;&nbsp;&nbsp;보관 통합  <br/> **참고:** 자세한 내용은 [비즈니스용 Skype 서버 통합을 Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/>(비즈니스용 Skype 서버 2015만 해당) |다음 기능은 EWS를 통해서만 사용할 수 있습니다.  <br/>&bull;&nbsp;&nbsp;대화 기록 폴더의 항목 읽기 또는 삭제  <br/>&bull;&nbsp;&nbsp;음성 메일 항목 읽기 또는 삭제  <br/>&bull;&nbsp;&nbsp;확장된 사용/사용 중 정보 및 모임 제목 및 위치 표시  <br/>&bull;&nbsp;&nbsp;Exchange 동기화  <br/> 공용 폴더는 2010년 Exchange Server 선택 사항입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목
 
[Windows 요구 사항 및 소프트웨어 지원](windows-requirements.md)
  
[모임 클라이언트 계획(Web App 및 모임 앱)](meetings-clients.md)

