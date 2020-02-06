---
title: 지정 되지 않은 전화 번호 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792166"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>미지정 전화 번호: 새로 만들기 또는 기존 항목 편집

> [!NOTE]
> Exchange UM은 비즈니스용 Skype 2019을 Exchange 2013 또는 Exchange 2016와 통합할 때 비즈니스용 Skype 서버 2019에서 계속 사용할 수 있습니다. Exchange 2019에서 지원 되는 변경 사항으로 인해 클라우드 보이스 메일과 클라우드 자동 전화 교환 기능 때문에 Exchange UM 통합이 더욱 강조 됩니다.

지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.

> [!IMPORTANT]
> 지정 하지 않은 새 번호 범위 또는 기존 항목을 편집 하는 작업이 완료 되 면 **확인** 을 클릭 하 여 번호 범위가 모두 나열 된 지정 되지 **않은 번호** 페이지로 돌아갑니다. 지정 하지 않은 번호 **범위** 페이지 또는 지정 하지 않은 번호 **Rage** 페이지에서 변경한 내용은 사용자가 지정 하지 **않은 번호** 페이지에서 **모두 커밋을** 클릭할 때까지 데이터베이스에 커밋되지 않습니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 지정 되지 않은 숫자 범위를 식별 하는 설명적인 이름을 입력 합니다. 범위를 저장 한 후에는이 이름을 변경할 수 없습니다.

- **숫자 범위** 첫 번째 필드에 지정 되지 않은 숫자 범위의 시작 번호를 입력 합니다. 두 번째 필드에 범위의 끝 번호를 입력 합니다.

  - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.

  - 번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?. 즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 자동으로 추가 하도록 지정 하지 않는 경우), 더하기 기호 (+), 숫자 1 ~ 9 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.

- **알림 서비스** **알림을** 선택 하면 알림 응용 프로그램에서 수신 전화 또는 **exchange um** 을 처리 하 여 Exchange um 자동 전화 교환이 수신 전화를 처리 하도록 합니다.

- **알림 서비스**에 대 한 **알림을** 선택 하는 경우:

  - **대상 서버의 FQDN** 지정 하지 않은이 범위의 번호로 들어오는 호출을 처리 하는 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 선택 합니다.

  - **공지 사항** 지정 하지 않은이 번호 범위에 대해 재생할 공지 사항을 선택 합니다.

- **알림 서비스**용 **Exchange UM** 을 선택한 경우 다음을 수행 합니다.

  - **자동 전화 교환 전화 번호** Exchange UM 자동 전화 교환의 전화 번호를 선택 합니다.

알림 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype에서 알림 신청 계획](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) 을 참조 하세요. 지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)을 참조하세요.


