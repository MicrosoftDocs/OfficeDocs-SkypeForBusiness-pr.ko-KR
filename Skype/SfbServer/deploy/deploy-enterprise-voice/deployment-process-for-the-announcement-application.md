---
title: 비즈니스용 Skype 서버의 공지 응용 프로그램에 대한 배포 프로세스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 비즈니스용 Skype 서버 2013의 배포 프로세스 및 Enterprise Voice.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812308"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 공지 응용 프로그램에 대한 배포 프로세스
 
비즈니스용 Skype 서버 2013의 배포 프로세스 및 Enterprise Voice.
  
공지 Enterprise Voice 기능으로, 할당되지 않은 내선 번호(조직에 유효하지만 사람 또는 전화에 할당되지 않은 내선 번호)에 대한 통화를 구성할 수 있습니다. 예를 들어 지정되지 않은 번호로의 통화에 대해 메시지를 재생하거나 다른 대상으로 전달하도록 구성하거나 이 두 가지를 모두 구성할 수 있습니다.
  
공지 사항을 배포할 때 공지 응용 프로그램은 프런트 엔드 서버 또는 Standard Edition 서버에 응답 그룹 응용 프로그램의 기능으로 Enterprise Voice. 오디오 파일을 업로드하거나 TTS(텍스트 음성 변환)를 구성하고 지정되지 않은 번호 테이블을 구성하여 알림을 구성해야 합니다.
  
이 섹션에서는 공지 사항 응용 프로그램 배포와 관련된 단계에 대해 간략하게 설명합니다. 공지 사항을 구성하기 Enterprise Voice 배포해야 합니다. 공지사항 응용 프로그램에 필요한 구성 요소는 배포할 때 설치 및 Enterprise Voice.
  
**알림 배포 프로세스**

|**작업 단계**|**단계**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|알림 설정 구성  <br/> | 오디오 파일을 녹음하여 업로드하거나 TTS(텍스트 음성 변환)를 사용하여 알림을 만듭니다. <br/>  지정되지 않은 번호 표의 지정되지 않은 번호 범위를 구성하여 적절한 알림과 연결합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[비즈니스용 Skype 서버에서 공지 만들기 또는 삭제](create-an-announcement.md) <br/> [비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정](create-or-modify-an-unassigned-number-range.md) <br/> |
|알림 배포 확인  <br/> |알림 듣기를 테스트하여 구성이 제대로 작동하는지 확인합니다.  <br/> |-  <br/> |[(선택 사항) 비즈니스용 Skype에서 공지사항 배포 확인](optional-verify-announcement-deployment.md) <br/> |
   

