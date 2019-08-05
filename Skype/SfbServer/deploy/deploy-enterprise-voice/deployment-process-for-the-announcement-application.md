---
title: 비즈니스용 Skype 서버의 알림 신청에 대 한 배포 프로세스
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 비즈니스용 Skype Server Enterprise Voice의 알림 신청에 대 한 배포 프로세스 및 단계.
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187341"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 알림 신청에 대 한 배포 프로세스
 
비즈니스용 Skype Server Enterprise Voice의 알림 신청에 대 한 배포 프로세스 및 단계.
  
알림 신청은 할당 되지 않은 확장명 (조직에 대해 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 확장명)에 대 한 호출을 구성할 수 있는 Enterprise Voice 기능입니다. 예를 들어 지정 하지 않은 번호로 통화를 구성 하 여 메시지를 재생 하거나 다른 대상 또는 둘 다로 전송할 수 있습니다.
  
알림 응용 프로그램은 엔터프라이즈 음성을 배포할 때 프런트 엔드 서버 또는 Standard Edition 서버에 응답 그룹 응용 프로그램의 기능으로 설치 됩니다. 오디오 파일을 업로드 하거나 텍스트 읽어주기 (TTS)를 구성 하 고 할당 되지 않은 번호 표를 구성 하 여 알림을 구성 해야 합니다.
  
이 섹션에서는 알림 신청 배포 단계에 대해 간략하게 설명 합니다. 알림을 구성 하기 전에 엔터프라이즈 음성을 배포 해야 합니다. 엔터프라이즈 음성을 구축할 때 알림 응용 프로그램에 필요한 구성 요소를 설치 하 고 사용할 수 있습니다.
  
**알림 배포 프로세스**

|**단계의**|**방법은**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|알림 설정 구성  <br/> | 오디오 파일을 기록 및 업로드 하거나 텍스트 음성 변환 (TTS)을 사용 하 여 알림을 만듭니다. <br/>  지정 하지 않은 번호 표에서 할당 되지 않은 번호 범위를 구성 하 고 적절 한 공지와 연결 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> Csviewadministrator  <br/> |[비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제](create-an-announcement.md) <br/> [비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정](create-or-modify-an-unassigned-number-range.md) <br/> |
|공지 사항 배포 확인  <br/> |알림을 청취 하 여 테스트를 수행 하 여 구성이 예상 대로 작동 하는지 확인 합니다.  <br/> |-  <br/> |[) 비즈니스용 Skype에서 알림 배포 확인](optional-verify-announcement-deployment.md) <br/> |
   

