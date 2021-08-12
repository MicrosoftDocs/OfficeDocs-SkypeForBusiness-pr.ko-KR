---
title: 배정되지 않은 전화 번호 새로 만들기 또는 기존 데이터 편집
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
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: 13b2caaa8e7b364fa60ab32e6c62f982612121c4861197cd2b76597975c0ba50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313396"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>지정되지 않은 전화 번호: 새로 만들기 또는 기존 항목 편집

지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.

> [!IMPORTANT]
> 새 지정되지 않은 번호 범위 만들기 또는 기존 지정되지 않은 번호 범위 편집을 마친 후 **확인** 을 클릭하면 모든 번호 범위의 목록이 표시되는 **지정되지 않은 번호** 페이지로 돌아갑니다. **새 지정되지 않은 번호 범위** 페이지 또는 **지정되지 않은 번호 범위 편집** 페이지에서 수행한 변경 내용은 **지정되지 않은 번호** 페이지에서 **모두 커밋** 을 클릭해야 데이터베이스로 커밋됩니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 지정되지 않은 번호 범위를 식별하는 설명적인 이름을 입력합니다. 범위를 저장한 후 이 이름은 변경할 수 없습니다.

- **번호 범위** 첫 번째 필드에 미지정 번호 범위의 시작 번호를 입력합니다. 두 번째 필드에 범위의 끝 번호를 입력합니다.

  - 범위의 시작 번호는 범위의 끝 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호나 끝 번호에 내선 번호가 포함된 경우에는 범위의 시작 번호와 끝 번호 둘 다에 내선 번호가 포함되어야 하며, 내선 번호는 시작 번호와 끝 번호에 대해 같아야 합니다.

  - 숫자는 정규식과 일치해야 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 합니다. 즉, 숫자가 문자열로 시작될 수 있습니다(해당 문자열을 자동으로 추가하는 경우), 더하기 `tel:` 기호(+) 및 숫자 1-9. 전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.

- **공지 서비스** 알림 **응용** 프로그램에서 수신 전화를 처리하거나 Exchange **UM에서** 수신 전화를 처리하게 Exchange UM을 자동 전화 교환 선택합니다.

- **알림 서비스** 에 대해 **알림** 을 선택한 경우 다음 옵션을 지정합니다.

  - **대상 서버의 FQDN** 이 지정되지 않은 번호 범위에 대한 수신 전화를 처리할 알림 응용 프로그램을 실행하는 응용 프로그램 서비스의 서비스 ID를 선택합니다.

  - **공지** 이 범위의 미지정 번호에 대해 재생할 공지 사항을 선택합니다.

- **알림 서비스** 에 대해 **Exchange UM** 을 선택한 경우 다음 옵션을 지정합니다.

  - **자동 전화 교환 번호** UM 연결의 전화 Exchange 선택합니다자동 전화 교환.

공지 사항 기능에 대한 자세한 내용은 계획 설명서에서 [Plan for the Announcement application in 비즈니스용 Skype 2015을](../../plan-your-deployment/enterprise-voice-solution/announcement.md) 참조하십시오. 지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers)을 참조하십시오.