---
title: 2013의 공지 응용 프로그램에 대한 배포 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 2016년 8월에 발표 응용 프로그램에 대한 배포 프로세스 및 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: e579ca3877b35ae5cdbb85582516a3bfbac8c354
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745364"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>2013의 공지 응용 프로그램에 대한 배포 비즈니스용 Skype 서버
 
2016년 8월에 발표 응용 프로그램에 대한 배포 프로세스 및 비즈니스용 Skype 서버 Enterprise Voice.
  
공지사항 응용 Enterprise Voice 할당되지 않은 내선 번호(조직에 유효하지만 사용자나 전화에 할당되지 않은 내선 번호)에 대한 호출을 구성할 수 있는 Enterprise Voice 기능입니다. 예를 들어 지정되지 않은 번호로의 통화에 대해 메시지를 재생하거나 다른 대상으로 전달하도록 구성하거나 이 두 가지를 모두 구성할 수 있습니다.
  
공지사항 응용 프로그램은 배포할 때 프런트 엔드 서버 또는 Standard Edition 그룹 응용 프로그램의 기능으로 Enterprise Voice. 오디오 파일을 업로드하거나 TTS(텍스트 음성 변환)를 구성하고 지정되지 않은 번호 테이블을 구성하여 알림을 구성해야 합니다.
  
이 섹션에서는 공지 사항 응용 프로그램 배포와 관련된 단계에 대해 간략하게 설명합니다. 공지 사항을 구성하기 Enterprise Voice 배포해야 합니다. 공지 사항을 배포할 때 공지사항 응용 프로그램에 필요한 구성 요소가 Enterprise Voice.
  
**알림 배포 프로세스**

|**작업 단계**|**단계**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|알림 설정 구성  <br/> | 오디오 파일을 녹음하여 업로드하거나 TTS(텍스트 음성 변환)를 사용하여 알림을 만듭니다. <br/>  지정되지 않은 번호 표의 지정되지 않은 번호 범위를 구성하여 적절한 알림과 연결합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[사용자 계정에서 공지 사항을 만들거나 비즈니스용 Skype 서버](create-an-announcement.md) <br/> [새 번호에서 배정되지 않은 번호 범위를 만들거나 비즈니스용 Skype 서버](create-or-modify-an-unassigned-number-range.md) <br/> |
|알림 배포 확인  <br/> |알림 듣기를 테스트하여 구성이 제대로 작동하는지 확인합니다.  <br/> |-  <br/> |[(선택 사항) 2013에서 공지 사항을 배포 비즈니스용 Skype](optional-verify-announcement-deployment.md) <br/> |
   

