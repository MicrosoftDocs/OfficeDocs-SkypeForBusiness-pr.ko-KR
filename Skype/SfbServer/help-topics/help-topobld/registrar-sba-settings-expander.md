---
title: 등록자 SBA 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 탄성에 대한 설정을 편집하고 다음 속성을 구성합니다.
ms.openlocfilehash: 33c8ddd4c97a160a574287ccaca0d9d9675bda600e6857b6e5122cf6c22e755f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321710"
---
# <a name="registrar-sba-settings-expander"></a>등록자 SBA 설정 확장기

**탄성** 에 대한 설정을 편집하고 다음 속성을 구성합니다.

- 목록에서 연결된 사용자 서비스 및 **백업 등록자 풀을** 선택합니다.

    원하는 경우 **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 확인란을 선택합니다.

    **음성 실패 검색 간격(초)** 및 **음성 장애 복구(failback) 간격(초)** 을 구성합니다. 기본적으로 음성 실패 검색 간격은 120초이고 음성 장애 복구(failback) 간격은 240초입니다.

    > [!CAUTION]
    > 장애 조치(failover) 및 장애 복구(failback) 간격에 대해 정의하는 시간(초)은 면밀하게 테스트하여 탄성이 예상대로 작동하는지를 확인해야 합니다. 간격을 낮게(120초 미만으로) 설정하거나 장애 조치(failover) 및 장애 복구(failback)를 너무 가깝게 설정하면 실제 장애 조치(failover) 및 장애 복구(failback)가 예상대로 작동하지 않을 수 있습니다.

  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.

  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.

  **도움말**: 이 도움말 화면을 표시합니다.

## <a name="see-also"></a>참고 항목

[Enterprise Voice 복구 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)