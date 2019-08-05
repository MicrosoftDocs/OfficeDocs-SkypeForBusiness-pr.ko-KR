---
title: 비즈니스용 Skype 서버의 근무 이벤트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: '요약: 비즈니스용 Skype 서버의 통합 커뮤니케이션 웹 API (c)에 대해 알아보세요.'
ms.openlocfilehash: bbded70318190fb4fa68ab524a696183c97ff07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188646"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 근무 이벤트
 
**요약:** 비즈니스용 Skype 서버의 통합 커뮤니케이션 웹 API (c)에 대해 알아보세요.
  
비즈니스용 Skype Server는 연락처 검색을 위해 Microsoft Exchange에 액세스 하 여 모바일 클라이언트에 대 한 현재 상태를 업데이트 하는 데 이르기까지 다양 한 용도로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.
  
작업 동작의 레코드를 이벤트 형식 정보, 경고 및 오류로 기록 합니다. 다음 표에서는 함께 사용할 수 있는 이벤트에 대해 설명 합니다.
  
|**이벤트 ID**|**이벤트 유형**|**요약**|**원인 및 해결 방법**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |나타낼  <br/> |초기화  <br/> |해당 없음  <br/> 해당 없음  <br/> |
|20002  <br/> |오류  <br/> |초기화 중에 예기치 않은 예외가 발생 했습니다.  <br/> |초기화 하는 동안 예기치 않은 오류가 발생 했습니다.  <br/> 연결 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.  <br/> |
|20003  <br/> |오류  <br/> |A;/WA에서 처리 되지 않은 예외가 발생 했습니다.  <br/> |처리 되지 않은 예외가 발생 했습니다.  <br/> 서버를 다시 시작 합니다. 문제가 지속 되 면 기술 지원팀에 문의 하세요.  <br/> |
|20004  <br/> |오류  <br/> |HD photo에 대 한 Exchange에 액세스할 수 없음  <br/> |Exchange에 대 한 연결을 사용할 수 없습니다.  <br/> Exchange에 대 한 연결을 사용할 수 있는지 확인  <br/> |
|20005  <br/> |나타낼  <br/> |HD photo에 대 한 Exchange 액세스 실패 복구  <br/> |해당 없음  <br/> |
|20006  <br/> |오류  <br/> |연락처 검색을 위해 Exchange에 액세스할 수 없음  <br/> |Exchange에 대 한 연결을 사용할 수 없습니다.  <br/> Exchange에 대 한 연결을 사용할 수 있는지 확인  <br/> |
|20007  <br/> |나타낼  <br/> |Exchange에서 연락처 검색 실패에서 복구 됨  <br/> |해당 없음  <br/> |
|20008  <br/> |오류  <br/> |앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.  <br/> |앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.  <br/> 클라이언트에 불필요 한 구독이 있는지 확인  <br/> |
|20009  <br/> |오류  <br/> |일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.  <br/> |일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.  <br/> 클라이언트에 불필요 한 구독이 있는지 확인  <br/> |
|20010  <br/> |오류  <br/> |Inband 데이터를 검색할 수 없음  <br/> |Inband 데이터를 검색할 수 없음  <br/> 문제가 지속 되 면 기술 지원팀에 문의 하세요.  <br/> |
|20011  <br/> |오류  <br/> |현재 상태를 구독할 수 없음  <br/> |현재 상태를 구독할 수 없음  <br/> 문제가 지속 되 면 기술 지원팀에 문의 하세요.  <br/> |
|20012  <br/> |오류  <br/> |끝점을 등록 하지 못했습니다.  <br/> |끝점을 등록 하지 못했습니다.  <br/> 문제가 지속 되 면 기술 지원팀에 문의 하세요.  <br/> |
|20013  <br/> |오류  <br/> |메신저 대화 MCU를 사용할 수 없음  <br/> |메신저 대화 MCU를 사용할 수 없음  <br/> 메신저 대화 MCU 실행 중인지 확인  <br/> |
|20014  <br/> |나타낼  <br/> |실패에서 메신저 대화에 연결 되지 않도록 복구 됨  <br/> |해당 없음  <br/> |
|20015  <br/> |오류  <br/> |AV MCU를 사용할 수 없음  <br/> |AV MCU를 사용할 수 없음  <br/> AV MCU가 실행 중인지 확인  <br/> |
|20016  <br/> |나타낼  <br/> |이 (가) AV MCU 연결 실패에서 복구 됨  <br/> |해당 없음  <br/> |
|20017  <br/> |오류  <br/> |MCU를 사용할 수 없음  <br/> |MCU를 사용할 수 없음  <br/> MCU가 실행 중인지 확인  <br/> |
|20018  <br/> |나타낼  <br/> |이 (가) MCU에 연결 하지 못한 경우 복구 됨  <br/> |해당 없음  <br/> |
|20019  <br/> |오류  <br/> |데이터 MCU를 사용할 수 없음  <br/> |데이터 MCU를 사용할 수 없음  <br/> 데이터 MCU가 실행 중인지 확인  <br/> |
|20020  <br/> |나타낼  <br/> |데이터 MCU 연결에 실패 하 여 복구 되지 않음  <br/> |해당 없음  <br/> |
|20021  <br/> |오류  <br/> |메신저 대화 MCU에 참가할 수 없음  <br/> |메신저 대화 MCU에 참가할 수 없음  <br/> 메신저 대화 MCU 실행 중인지 확인  <br/> |
|20022  <br/> |오류  <br/> |AV MCU에 참가할 수 없음  <br/> |AV MCU에 참가할 수 없음  <br/> AV MCU가 실행 중인지 확인  <br/> |
|20023  <br/> |오류  <br/> |MCU로 참가할 수 없음  <br/> |MCU로 참가할 수 없음  <br/> MCU가 실행 중인지 확인  <br/> |
|20024  <br/> |오류  <br/> |데이터 MCU에 참가할 수 없음  <br/> |데이터 MCU에 참가할 수 없음  <br/> 데이터 MCU가 실행 중인지 확인  <br/> |
|20025  <br/> |오류  <br/> |사진에 대 한 active directory에 액세스할 수 없음  <br/> |Active directory에 대 한 연결을 사용할 수 없습니다.  <br/> Active directory에 대 한 연결을 사용할 수 있는지 확인  <br/> |
|20026  <br/> |나타낼  <br/> |사진에 대 한 active directory 액세스가 실패 함에 복구 됨  <br/> |해당 없음  <br/> |
|20027  <br/> |오류  <br/> |Deserialize 할 수 없음  <br/> |Deserialize 할 수 없음  <br/> 문제가 지속 되 면 기술 지원팀에 문의 하세요.  <br/> |
   

