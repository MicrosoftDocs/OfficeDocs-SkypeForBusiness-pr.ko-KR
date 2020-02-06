---
title: 비즈니스용 Skype 서버의 번역 규칙
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 비즈니스용 Skype Server Enterprise Voice에서 번역 규칙 및 다이얼 문자열 정규화에 대해 알아봅니다.
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802398"
---
# <a name="translation-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 번역 규칙

비즈니스용 Skype Server Enterprise Voice에서 번역 규칙 및 다이얼 문자열 정규화에 대해 알아봅니다.

 Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다. 번역 규칙은 숫자와 통화 번호를 모두 지원 합니다. Thetrunk 피어 (즉, 연결 된 게이트웨이, PBX (사설 branch exchange) 또는 SIP 트렁크)는 해당 번호를 지역 전화 걸기 형식으로 요구할 수 있습니다. E-164 형식의 숫자를 지역 전화 걸기 형식으로 번역 하려면 하나 이상의 번역 규칙을 정의 하 여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다. 예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.

서버에서 아웃 바운드 경로 변환을 수행 하 여 전화 번호를 지역 전화 걸기 형식으로 변환 하기 위해 각각의 각 트렁크 피어에 대 한 구성 요구 사항을 줄일 수 있습니다. 특정 조정 서버 클러스터와 연결할 게이트웨이 및 게이트웨이의 수를 계획 하는 경우에는 유사한 지역 전화 걸기 요구 사항으로 트렁크 피어를 그룹화 하는 것이 유용할 수 있습니다. 이렇게 하면 필요한 번역 규칙의 수와 기록 하는 데 걸리는 시간을 줄일 수 있습니다.

> [!IMPORTANT]
> 하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 대신 트렁크 피어에서 번역 규칙을 구성할 수 있습니다. 두 규칙이 충돌할 수 있으므로 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요.

## <a name="example-translation-rules"></a>예제 번역 규칙

다음 번역 규칙 예제에서는 서버에서 규칙을 개발 하 여 E. \ 164 형식의 숫자를 트렁크 피어의 로컬 형식으로 변환 하는 방법을 보여 줍니다.

번역 규칙을 구현 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.

|**설명**|**시작 번호**|**Content-length**|**제거할 숫자**|**더할 숫자**|**일치 패턴**|**변환용**|**예**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|미국 내 기존 시외 전화 통화  <br/> (' + ' 제거)  <br/> |+ 1  <br/> |정확히 12  <br/> |1  <br/> |0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+ 14255551010이 14255551010  <br/> |
|미국 국제 장거리 전화  <br/> (' + '를 제거 하 고 011을 추가 합니다.)  <br/> |+  <br/> |11 개 이상  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011 $1  <br/> |+ 441235551010이 011441235551010  <br/> |


