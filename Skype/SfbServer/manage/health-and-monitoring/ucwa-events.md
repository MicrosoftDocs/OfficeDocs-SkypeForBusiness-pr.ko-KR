---
title: 비즈니스용 Skype 서버의 UCWA 이벤트
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: '요약: 비즈니스용 Skype 서버의 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816668"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 UCWA 이벤트
 
**요약:** 비즈니스용 Skype 서버의 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버는 연락처 검색을 위해 Microsoft Exchange에 액세스하는 것부터 모바일 클라이언트의 현재 상태 업데이트까지 다양한 목적으로 UCWA(Unified Communications Web API)를 사용하고 있습니다.
  
UCWA는 이벤트 유형 정보, 경고 및 오류 유형으로 작동 동작 레코드를 작성합니다. 다음 표에서는 UCWA 구성 요소에서 기록할 수 있는 이벤트에 대해 설명합니다.
  
|**이벤트 ID**|**이벤트 유형**|**요약**|**원인 및 해결**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |정보  <br/> |UCWA 초기화  <br/> |해당 없음  <br/> 해당 없음  <br/> |
|20002  <br/> |오류  <br/> |초기화 중에 UCWA에서 예기치 않은 예외가 발생했습니다.  <br/> |초기화 중에 예기치 않은 오류가 발생했습니다.  <br/> 관련 이벤트 로그 항목의 예외 세부 정보를 검사하여 가능한 원인 확인  <br/> |
|20003  <br/> |오류  <br/> |UCWA에서 처리되지 않은 예외가 발생했습니다.  <br/> |처리되지 않은 예외가 발생했습니다.  <br/> 서버를 다시 시작합니다. 문제가 지속되면 고객 지원에 문의  <br/> |
|20004  <br/> |오류  <br/> |HD 사진용 Exchange에 액세스할 수 없습니다.  <br/> |Exchange에 대한 연결을 사용할 수 없습니다.  <br/> Exchange에 대한 연결을 사용할 수 있는지 확인  <br/> |
|20005  <br/> |정보  <br/> |HD 사진에 대한 Exchange 액세스 실패에서 복구  <br/> |해당 없음  <br/> |
|20006  <br/> |오류  <br/> |연락처 검색을 위해 Exchange에 액세스할 수 없습니다.  <br/> |Exchange에 대한 연결을 사용할 수 없습니다.  <br/> Exchange에 대한 연결을 사용할 수 있는지 확인  <br/> |
|20007  <br/> |정보  <br/> |Exchange에서 검색 연락처 실패에서 복구  <br/> |해당 없음  <br/> |
|20008  <br/> |경고  <br/> |응용 프로그램당 허용되는 현재 상태 구독보다 더 많은 구독 시도  <br/> |응용 프로그램당 허용되는 현재 상태 구독보다 더 많은 구독 시도  <br/> 클라이언트에서 불필요한 구독 확인  <br/> |
|20009  <br/> |경고  <br/> |일괄 처리당 허용되는 현재 상태 구독보다 더 많은 구독 시도  <br/> |일괄 처리당 허용되는 현재 상태 구독보다 더 많은 구독 시도  <br/> 클라이언트에서 불필요한 구독 확인  <br/> |
|20010  <br/> |오류  <br/> |인밴드 데이터를 검색할 수 없습니다.  <br/> |인밴드 데이터를 검색할 수 없습니다.  <br/> 문제가 지속되면 고객 지원에 문의  <br/> |
|20011  <br/> |오류  <br/> |현재 상태 구독할 수 없습니다.  <br/> |현재 상태 구독할 수 없습니다.  <br/> 문제가 지속되면 고객 지원에 문의  <br/> |
|20012  <br/> |오류  <br/> |끝점을 등록하지 못했습니다.  <br/> |끝점을 등록하지 못했습니다.  <br/> 문제가 지속되면 고객 지원에 문의  <br/> |
|20013  <br/> |오류  <br/> |IM MCU를 사용할 수 없음  <br/> |IM MCU를 사용할 수 없음  <br/> IM MCU가 실행 중인지 확인  <br/> |
|20014  <br/> |정보  <br/> |IM MCU에 연결하지 못했습니다.  <br/> |해당 없음  <br/> |
|20015  <br/> |오류  <br/> |AV MCU를 사용할 수 없음  <br/> |AV MCU를 사용할 수 없음  <br/> AV MCU가 실행 중인지 확인  <br/> |
|20016  <br/> |정보  <br/> |AV MCU 연결 실패로부터 복구  <br/> |해당 없음  <br/> |
|20017  <br/> |오류  <br/> |AS MCU를 사용할 수 없음  <br/> |AS MCU를 사용할 수 없음  <br/> AS MCU가 실행 중인지 확인  <br/> |
|20018  <br/> |정보  <br/> |AS MCU에 연결하지 못하여 복구  <br/> |해당 없음  <br/> |
|20019  <br/> |오류  <br/> |데이터 MCU를 사용할 수 없음  <br/> |데이터 MCU를 사용할 수 없음  <br/> Data MCU가 실행 중인지 확인  <br/> |
|20020  <br/> |정보  <br/> |데이터 MCU에 연결하지 못했습니다.  <br/> |해당 없음  <br/> |
|20021  <br/> |오류  <br/> |IM MCU에 가입할 수 없습니다.  <br/> |IM MCU에 가입할 수 없습니다.  <br/> IM MCU가 실행 중인지 확인  <br/> |
|20022  <br/> |오류  <br/> |AV MCU에 가입할 수 없습니다.  <br/> |AV MCU에 가입할 수 없습니다.  <br/> AV MCU가 실행 중인지 확인  <br/> |
|20023  <br/> |오류  <br/> |AS MCU에 가입할 수 없습니다.  <br/> |AS MCU에 가입할 수 없습니다.  <br/> AS MCU가 실행 중인지 확인  <br/> |
|20024  <br/> |오류  <br/> |Data MCU에 가입할 수 없습니다.  <br/> |Data MCU에 가입할 수 없습니다.  <br/> Data MCU가 실행 중인지 확인  <br/> |
|20025  <br/> |오류  <br/> |사진에 대한 Active Directory에 액세스할 수 없습니다.  <br/> |Active Directory에 대한 연결을 사용할 수 없습니다.  <br/> Active Directory에 대한 연결을 사용할 수 있는지 확인  <br/> |
|20026  <br/> |정보  <br/> |사진에 대한 Active Directory 액세스 실패로부터 복구  <br/> |해당 없음  <br/> |
|20027  <br/> |경고  <br/> |Deserialize를 사용할 수 없습니다.  <br/> |Deserialize를 사용할 수 없습니다.  <br/> 문제가 지속되면 고객 지원에 문의  <br/> |
   

