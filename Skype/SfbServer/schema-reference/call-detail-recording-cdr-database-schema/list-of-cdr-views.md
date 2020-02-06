---
title: CDR 보기 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다. 실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 릴리스와 이전 버전과의 호환성을 유지 하는 것이 더 높기 때문입니다.
ms.openlocfilehash: 78bf18fe51cea8937de44c72b39f7c1b81c75544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815126"
---
# <a name="list-of-cdr-views"></a>CDR 보기 목록
 
뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다. 실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 릴리스와 이전 버전과의 호환성을 유지 하는 것이 더 높기 때문입니다.
  
|**이름 보기**|**설명**|
|:-----|:-----|
|[ClientVersions 보기](clientversions-0.md) <br/> |통신 세션에 사용 되는 클라이언트 소프트웨어/장치에 대 한 정보를 반환 합니다.  <br/> |
|[ConferenceMessageCount 보기](conferencemessagecount-0.md) <br/> |회의 중 사용자가 보낸 메시지 수에 대 한 정보를 반환 합니다.  <br/> |
|[회의 보기](conferences-0.md) <br/> |시작 시간, 종료 시간, 컨퍼런스 이끌이 등 회의 정보를 반환 합니다.  <br/> |
|[ConferenceSessionDetails 보기](conferencesessiondetails.md) <br/> |시작 및 종료 시간, 사용자 Id, 응답 코드, 진단 Id를 포함 하 여 모든 회의 세션에 대 한 세션 세부 정보를 반환 합니다.  <br/> |
|[ConferenceUris 보기](conferenceuris-0.md) <br/> |회의에 사용 되는 회의 Uri에 대 한 정보를 반환 합니다.  <br/> |
|[ErrorReport 보기](errorreport-0.md) <br/> |세션 중에 발생 한 오류에 대 한 정보를 반환 합니다.  <br/> |
|[FileTransfers 보기](filetransfers.md) <br/> |파일 이름과 전송 수락, 거부 또는 취소를 포함 하 여 파일 전송 세션에 대 한 정보를 반환 합니다.  <br/> |
|[FocusJoinsAndLeaves 보기](focusjoinsandleaves-0.md) <br/> |컨퍼런스 참가 및 탈퇴 활동에 대 한 정보를 반환 합니다.  <br/> |
|[McuJoinsAndLeaves 보기](mcujoinsandleaves-0.md) <br/> |컨퍼런스 참가 및 탈퇴 활동에 대 한 통합 된 정보를 반환 합니다 (각 회의 참가는 해당 회의 연결이 유지 됩니다.).  <br/> |
|[Mcus 보기](mcus-0.md) <br/> |회의 서버에 대 한 정보를 반환 합니다.  <br/> |
|[미디어 보기](media-0.md) <br/> |피어 투 피어 통신 세션에 사용 되는 미디어 형식에 대 한 정보를 반환 합니다.  <br/> |
|[ProgressReport 보기](progressreport-0.md) <br/> |완료 된 세션에 대 한 정보를 반환 합니다.  <br/> |
|[등록 보기](registration-0.md) <br/> |비즈니스용 Skype Server 2015의 등록에 대 한 정보를 반환 합니다.  <br/> |
|[SessionDetails 뷰](sessiondetails-0.md) <br/> |VoIP 전화 통화, 2 자리 IM 세션 또는 기타 피어 투 피어 통신 세션을 비롯 한 피어 투 피어 세션에 대 한 정보를 반환 합니다.  <br/> |
|[사용자 보기](user.md) <br/> |통신 세션에 참가 한 사용자에 대 한 정보를 반환 합니다.  <br/> |
|[VoIPDetails 보기](voipdetails.md) <br/> |하나 이상의 VoIP (음성 over IO) 사용자를 포함 하는 피어 투 피어 세션에 대 한 정보를 반환 합니다.  <br/> |
   

