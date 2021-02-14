---
title: 비즈니스용 Skype 서버의 모바일 성능 카운터
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
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: '요약: UCWA(Unified Communications Web API) 및 비즈니스용 Skype 서버 Mcx Mobility Service를 실행하는 서버를 모니터링하는 데 사용할 수 있는 성능 카운터를 제공합니다.'
ms.openlocfilehash: d711ada11cee9cb12a5cde25cab583f8b174ac50
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814408"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 모바일 성능 카운터
 
**요약:** UCWA(Unified Communications Web API) 및 비즈니스용 Skype 서버 Mcx Mobility Service를 실행하는 서버를 모니터링하는 데 사용할 수 있는 성능 카운터에 대해 자세히 알아보습니다.
  
다음 표에는 UCWA(통합 통신 웹 API) 및 비즈니스용 Skype 서버 Mcx Mobility Service를 실행하는 서버를 모니터링하는 데 사용할 수 있는 성능 카운터의 이름과 설명이 나열됩니다. 
  
UCWA 테이블의 카운터 범주 이름은 **LS:WEB - UCWA입니다.**
  
Mcx Mobility Service 테이블의 카운터 범주 이름은 **LS:WEB - Mobile Communication Service입니다.**

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
## <a name="performance-counters-for-ucwa"></a>UCWA에 대한 성능 카운터

|카운터|설명|
|:-----|:-----|
|활성 응용 프로그램 수  <br/> |현재 응용 프로그램 수  <br/> |
|활성 응용 프로그램 공유 모달성 수  <br/> |현재 응용 프로그램 공유 모달 수  <br/> |
|Active Audio Modality Count  <br/> |현재 오디오 모달 수  <br/> |
|활성 데이터 공동 작업 Modality Count  <br/> |현재 데이터 공동 작업 모달 수  <br/> |
|Active Directory 사진 Get Latency(ms)  <br/> |이 카운터는 Active Directory에서 사진을 검색하는 평균 시간(밀리초)을 보여 주며,  <br/> |
|Active Messaging Modality Count  <br/> |현재 메시징 모달 수  <br/> |
|활성 파노라마 비디오 부호 수  <br/> |파노라마 비디오의 현재 수  <br/> |
|활성 보류 중인 Get Count  <br/> |현재 활성 상태인 보류 중인 Get 수입니다. 서버에 대한 긴 연결  <br/> |
|활성 세션 수  <br/> |응용 프로그램 및 총 UCWA에 등록된 현재 끝점 수  <br/> |
|활성 사용자 인스턴스 수  <br/> |현재 사용자 인스턴스 수  <br/> |
|응용 프로그램이 없는 활성 사용자 인스턴스  <br/> |응용 프로그램이 없는 현재 사용자 인스턴스 수  <br/> |
|Active Video Modality Count  <br/> |비디오의 현재 수  <br/> |
|응용 프로그램 만들기 요청 수신/초  <br/> |수신된 응용 프로그램 만들기 요청의 초당 속도  <br/> |
|AS MCU 조인 실패  <br/> |AS MCU 조인 실패 횟수  <br/> |
|AV MCU 조인 실패  <br/> |AV MCU 조인 실패 횟수  <br/> |
|평균 응용 프로그램 시작 시간(ms)  <br/> |평균 응용 프로그램 시작 시간(밀리초)입니다.  <br/> |
|세션의 평균 수명(ms)  <br/> |세션의 평균 수명(밀리초)입니다.  <br/> |
|데이터 MCU 조인 실패  <br/> |데이터 MCU 조인 실패 횟수  <br/> |
|Exchange 연락처 검색 대기 시간(ms)  <br/> |이 카운터는 Exchange에서 연락처를 검색하는 평균 시간(밀리초)을 보여 주며,  <br/> |
|Exchange HD 사진 Get Latency(ms)  <br/> |이 카운터는 Exchange에서 사진을 검색하는 평균 시간(밀리초)을 보여 주며,  <br/> |
|HTTP 4xx 응답/초  <br/> |HTTP 4xx 코드를 사용하는 초당 응답 속도  <br/> |
|HTTP 5xx 응답/초  <br/> |HTTP 5xx 코드를 사용하는 초당 응답 속도  <br/> |
|IM MCU 가입 실패  <br/> |IM MCU 조인 실패 횟수  <br/> |
|Active Directory 사진 Get 실패 횟수  <br/> |Active Directory에서 사진을 검색하는 총 실패 횟수입니다.  <br/> |
|연락처 검색 실패 횟수  <br/> |Exchange에서 연락처를 검색하는 총 오류 수  <br/> |
|Deserialization Failures(Deserialization Failures) 수  <br/> |전사화 실패의 총 수  <br/> |
|HD 사진 Get 실패 횟수  <br/> |Exchange에서 HD 사진을 검색하는 총 오류 수  <br/> |
|응용 프로그램당 최대 구독 수 초과  <br/> |응용 프로그램당 허용되는 최대 구독 요청 수  <br/> |
|일괄 처리당 최대 구독 수 초과  <br/> |일괄 처리당 허용되는 최대 구독 요청 수  <br/> |
|현재 상태 구독 실패  <br/> |현재 상태 구독 실패 횟수  <br/> |
|끝점 오류 등록  <br/> |끝점 등록 실패 횟수  <br/> |
|Requests Received/Second  <br/> |수신된 요청의 초당 속도  <br/> |
|Requests Succeeded/Second  <br/> |성공한 요청의 초당 속도(HTTP 2xx/3xx 응답 코드)  <br/> |
|성공한 응용 프로그램 요청/초  <br/> |응용 프로그램 만들기 요청의 초당 성공률  <br/> |
|시간 미정 상태인 Get Count  <br/> |이 시간이 시간으로 정해진 보류 중인 수  <br/> |
|받은 총 응용 프로그램 만들기 요청 수  <br/> |서비스가 시작된 이후 수신된 총 응용 프로그램 만들기 요청 수입니다.  <br/> |
|총 HTTP 4xx 응답  <br/> |총 HTTP 4xx 응답 수  <br/> |
|총 HTTP 5xx 응답  <br/> |총 HTTP 5xx 응답 수  <br/> |
|명령 채널에서 받은 총 요청 수  <br/> |명령 채널에서 수신된 총 요청 수  <br/> |
|총 요청 성공  <br/> |성공한 총 요청 수  <br/> |
|시작된 총 세션 수  <br/> |서비스가 시작된 후 시작된 총 세션 수입니다.  <br/> |
|유휴 시간 제한 때문에 종료된 총 세션 수  <br/> |사용자 유휴 시간 제한으로 인하여 종료된 총 세션 수입니다.  <br/> |
|총 스로틀된 응용 프로그램  <br/> |스로틀된 응용 프로그램 수  <br/> |
   
**Mcx Mobility Service에 대한 성능 카운터**

|**카운터**|**설명**|
|:-----|:-----|
|세션의 평균 수명(밀리초)입니다.  <br/> |세션의 평균 수명(밀리초)입니다.  <br/> |
|현재 푸시 알림 구독  <br/> |현재 푸시 알림 구독 수입니다. 이 숫자는 현재 활성 세션 수와 함께 Windows Mobile 또는 iPhone 장치에 등록된 현재 활성 세션의 하위 집합을 나타내며,  <br/> |
|현재 활성 네트워크 시간 제한 폴링 수  <br/> |시간이 정해진 네트워크 폴링 수  <br/> |
|현재 활성 폴링 횟수  <br/> |현재 활성 폴링 수(서버에 대한 긴 연결)  <br/> |
|현재 활성 세션 수  <br/> |Mobility Service에 등록된 현재 끝점 수  <br/> |
|현재 활성 상태 구독이 있는 활성 세션 수  <br/> |활성 현재 상태 구독이 있는 현재 활성 세션 수  <br/> |
|푸시 알림 요청 실패/초  <br/> |실패한 푸시 알림의 초당 속도  <br/> |
|푸시 알림 요청 성공/초  <br/> |성공한 푸시 알림의 초당 속도  <br/> |
|푸시 알림 요청 스로틀/초  <br/> |제한 푸시 알림의 초당 속도  <br/> |
|푸시 알림 요청/초  <br/> |전송된 푸시 알림의 초당 속도  <br/> |
|요청 실패/초  <br/> |실패한 요청의 초당 속도  <br/> |
|Requests Received/Second  <br/> |수신된 요청의 초당 속도  <br/> |
|요청 거부/초  <br/> |거부된 요청의 초당 비율  <br/> |
|Requests Succeeded/Second  <br/> |성공한 요청의 초당 속도  <br/> |
|Succeeded Initiate Session Requests/Second  <br/> |성공적인 위치 요청의 초당 속도입니다. 세션 시작 요청은 서버에서 가장 많은 CPU를 소비합니다. 최대 지원 부하는 12/초입니다. 지속 가능성은 서버의 다른 부하에 따라 다를 수 있습니다. 세션을 시작하면 일반적으로 연장된 기간 동안 로그인된 사용자에 대한 로그인이 됩니다.  <br/> |
|총 거절된 인바운드 음성 통화  <br/> |거부된 총 인바운드 음성 통화 수  <br/> |
|총 실패한 인바운드 음성 통화  <br/> |실패한 총 인바운드 음성 통화 수  <br/> |
|총 실패한 아웃바운드 음성 통화  <br/> |실패한 총 아웃바운드 음성 통화 수  <br/> |
|사용자가 종료한 총 세션 수  <br/> |사용자가 종료한 총 세션 수  <br/> |
|총 푸시 알림 요청  <br/> |푸시 알림 요청의 총 수  <br/> |
|총 푸시 알림 요청 실패  <br/> |실패한 푸시 알림 요청의 총 수입니다.  <br/> |
|총 푸시 알림 요청 성공  <br/> |성공한 푸시 알림 요청의 총 수입니다.  <br/> |
|총 푸시 알림 요청 스로틀  <br/> |스로틀된 푸시 알림 요청의 총 수입니다.  <br/> |
|총 요청 실패  <br/> |실패한 총 요청 수  <br/> |
|명령 채널에서 받은 총 요청 수  <br/> |명령 채널에서 수신된 총 요청 수  <br/> |
|총 요청 거부  <br/> |거부된 총 요청 수  <br/> |
|총 요청 성공  <br/> |성공한 Mobility Service에 대한 총 요청 수입니다.  <br/> |
|총 세션 시작 횟수  <br/> |Mobility Service가 시작된 이후 시작된 총 세션 수입니다.  <br/> |
|사용자 유휴 시간 제한으로 인하여 종료된 총 세션 수  <br/> |사용자 유휴 시간 제한으로 인하여 종료된 총 세션 수입니다.  <br/> |
|총 성공한 인바운드 음성 통화  <br/> |성공한 총 인바운드 음성 통화 수  <br/> |
|총 성공한 아웃바운드 음성 통화  <br/> |성공한 총 아웃바운드 음성 통화 수  <br/> |
   
> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
