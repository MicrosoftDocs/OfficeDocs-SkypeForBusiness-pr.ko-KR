---
title: 모임 구성 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 모임 구성 설정은 사용자가 예약한 회의에 대한 사용자 참가 환경을 정의합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 클라이언트에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc 모임에는 적용되지 않습니다.
ms.openlocfilehash: 5812c73fd3f72d3c61994a95c977f9d4046be07f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742284"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>모임 구성: 새로 만들기 또는 기존 항목 편집

모임 구성 설정은 사용자가 예약한 회의에 대한 사용자 참가 환경을 정의합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 클라이언트에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc **모임에는** 적용되지 않습니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **범위** 만들거나 수정할 모임 구성의 범위(전역, 사이트 또는 풀)를 식별합니다.

- **이름** 모임 구성의 이름은 기본적으로 지정되어 있으며 이름은 변경할 수 없습니다.

- **PSTN 발신자 우회 대기실** PSTN(Public Switched Telephone Network) 전화 회선으로 전화 회의에 전화 접속하는 사용자를 자동으로 입력하려면 이 확인란을 선택합니다. PSTN 발신자에 대한 전화 회의 대기실로 라우팅하기 위해 이 확인란의 선택을 취소합니다. 전화 회의 발표자는 전화 회의에 대한 액세스 권한을 부여할 때까지 대기 중입니다.

- **발표자로 지정** 회의에 참가할 때 자동으로 발표자로 지정된 사용자 범주(모임 이끌이 외에)를 선택합니다. 이 설정에 관계없이 회의가 예약될 때 발표자는 명시적으로 발표자로 지정되거나, 회의 중에 발표자로 명시적으로 승격될 수 있습니다. 다음과 같은 옵션이 있습니다.

  - **없음** 이끌이가 다른 사용자가 자동으로 발표자로 지정되지 않았다면 이 옵션을 선택합니다.

  - **회사** 조직의 구성원만 발표자로 자동으로 지정하려면 이 옵션을 선택합니다.

  - **모든 사람** 모든 사람을 자동으로 발표자로 지정하려면 이 옵션을 선택합니다.

- **기본적으로 할당된 회의 유형** 이 설정은 Outlook 회의 추가 기능에서 이끌이의 할당된 회의를 사용하여 항상 회의를 예약할지 여부를 제어합니다. 즉, 예약된 회의의 참가 URL과 오디오 정보가 항상 동일합니다. 예약된 회의에서 항상 동일한 참가 URL을 사용하려면 이 확인란을 선택합니다. 각 회의에 대해 다른 참가 URL을 사용하게 하여 이 확인란의 선택을 취소합니다.

- **기본적으로 익명 사용자 지정** 익명(즉, 확인되지 않은) 사용자가 기본적으로 회의에 참가할 수 있는 경우 이 확인란을 선택합니다. 익명 사용자가 기본적으로 회의에 참석할 수 없는 경우 이 확인란의 선택을 취소합니다.

- **로고 URL** 사용자 지정 회의 초대에 사용할 이미지가 있는 URL을 입력합니다.

- **도움말 URL** 사용자가 회의 참가 지원을 받을 수 있는 웹 사이트의 URL을 입력합니다.

- **법적 텍스트 URL** 회의에 대한 법적 정보 및 고지 사항은 있는 웹 사이트의 URL을 입력합니다.

- **사용자 지정 발자국 텍스트** 사용자 지정 전화 회의 초대에 사용할 텍스트를 입력합니다.

모임 구성 작업에 대한 자세한 내용은 작업 설명서에서 [Create a or modify a Collection of Meeting Configuration 설정](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) 참조하십시오. 대규모 모임에 대한 모임 구성을 설정하는 데 대한 자세한 내용은 계획 설명서에서 [Setting Up Support for Large Meetings을](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) 참조하십시오.