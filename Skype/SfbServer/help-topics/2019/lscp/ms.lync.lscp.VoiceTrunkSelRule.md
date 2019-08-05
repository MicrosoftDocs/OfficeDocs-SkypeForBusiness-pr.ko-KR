---
title: 변환 규칙 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)를 사용하려면 번호가 로컬 전화 번호 형식이어야 합니다. 번호를 E.164 형식에서 로컬 전화 번호 형식으로 변환하려면 선택적으로 하나 이상의 변환 규칙을 정의하여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다. 예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191772"
---
# <a name="select-translation-rules"></a>변환 규칙 선택
 
 Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)를 사용하려면 번호가 로컬 전화 번호 형식이어야 합니다. 번호를 E.164 형식에서 로컬 전화 번호 형식으로 변환하려면 선택적으로 하나 이상의 변환 규칙을 정의하여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다. 예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.
  
> [!IMPORTANT]
> 하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 기능은 트렁크 피어에서 번역 규칙을 구성 하는 대신 사용 하도록 설계 되었습니다. 두 규칙이 충돌할 수 있기 때문에 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요. 
  
기존 변환 규칙을 사용하려면 목록에서 규칙을 클릭한 다음 **확인**을 클릭합니다.
  
 
  

