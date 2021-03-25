---
title: 회의 정책
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
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: 회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.
ms.openlocfilehash: 6d69c463a9aa8a1e151b0787dfbfebf4e24fb693
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115368"
---
# <a name="conferencing-policy"></a>회의 정책

회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.

회의 정책에는 전역 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.

- **글로벌 정책:** 전역 정책은 기본적으로 만들어집니다. 글로벌 정책을 편집할 수는 있지만 삭제할 수는 없습니다. 글로벌 정책을 제거하려고 하면 모든 설정이 기본값으로 다시 설정됩니다.

- **사이트 정책(선택 사항):** 하나 이상의 사이트 회의 정책을 만들 수 있습니다. 각 정책은 특정 사이트에 적용됩니다. 사이트 정책은 글로벌 정책을 재정의합니다.

- **사용자 정책(선택 사항):** 하나 이상의 사용자 회의 정책을 만들 수 있습니다. 각 정책은 특정 사용자 또는 사용자 그룹에 적용됩니다. 사용자 정책은 글로벌 정책 및 사이트 정책을 재정의합니다.

회의 **정책** 페이지에는 조직에 대해 정의된 모든 회의 정책 목록이 표시됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**위치 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 새 사이트 회의 정책 또는 사용자 회의 정책 만들기

- 글로벌 정책 또는 기존 사이트 정책/사용자 정책 변경

- 사이트 정책 또는 사용자 정책 삭제

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 명령에 대해 설명합니다.

- **새로 추가** 새 사이트 회의 정책 또는 사용자 회의 정책을 시작합니다.

- **편집** 선택한 회의 정책을 열어 편집하거나, 목록의 모든 회의 정책을 선택하거나, 선택한 사이트 정책 또는 사용자 정책을 삭제합니다.

    > [!NOTE]
    > 글로벌 정책의 경우 **삭제** 를 클릭하면 설정이 기본값으로 다시 설정됩니다.

- **새로 고침** 회의 정책 목록을 새로 고쳐야 합니다.

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 회의 정책을 식별합니다.

- **범위** 회의 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.

- **데이터 공동 작업** 회의 정책이 회의에서 데이터 공동 작업을 허용하도록 지정하는지 확인

- **응용 프로그램 공유** 회의 정책이 회의에서 응용 프로그램 공유를 허용하도록 지정하는지 확인됩니다.

- **오디오** 회의 정책이 회의에서 오디오를 허용하도록 지정하는지 확인

- **비디오** 회의 정책이 회의에서 비디오를 허용하도록 지정하는지 확인됩니다.

- **PSTN** 회의 정책이 PSTN 전화 접속 회의를 허용하도록 지정하는지 확인

- **기록** 회의 정책이 회의에서 녹음/녹화를 허용하도록 지정하는지 확인됩니다.

회의 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Conferencing를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) 참조하십시오. 회의 정책 작업에 대한 자세한 내용은 작업 설명서에서 [Conferencing Policies을](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) 참조하십시오.