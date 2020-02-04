---
title: 레거시 병합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: 외부 사용자는 웹 회의 외부 FQDN을 사용 하 여 온-프레미스 모임에 참가할 수 있습니다. 레거시 Edge 서버의 웹 회의 외부 인터페이스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
ms.openlocfilehash: bb059855f7893ef7b2b9c601835bb53e6f0d280b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697093"
---
# <a name="legacy-merge"></a>레거시 병합

외부 사용자는 **웹 회의 외부 FQDN** 을 사용 하 여 온-프레미스 모임에 참가할 수 있습니다. 레거시 Edge 서버의 웹 회의 외부 인터페이스의 FQDN (정규화 된 도메인 이름)을 입력 합니다.

**443** 의 **외부 웹 회의 외부 포트** 값은 회의 클라이언트에 대해 구성 된 TCP (전송 제어 프로토콜)의 기본 SIP (세션 초기화 프로토콜) 포트입니다. 기본값을 사용 하지 않은 경우 **외부 웹 회의 외부 포트** 값을 업데이트 합니다.

이 Edge 서버를 페더레이션에 사용할 계획인 경우 **이 edge 풀을 페더레이션 및 공용 메신저 연결에 사용** 확인란을 선택 합니다. 여러 개의 Edge 서버가 배포 된 경우 페더레이션에 대 한 서버 중 하나만 사용 하도록 설정 됩니다. 이 확인란을 선택 하지 않고 나중에 페더레이션을 사용 하기로 결정 한 경우에는 토폴로지 작성기 병합 마법사를 다시 실행 하 고 토폴로지를 게시 해야 합니다. 자세한 내용은 [4 단계: 병합 토폴로지](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)를 참조 하세요.


