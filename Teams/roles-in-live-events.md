---
title: Teams 라이브 이벤트의 발표자 및 참가자 기능
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 라이브 이벤트의 발표자 및 참가자 기능에 대해 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6341e688973dc50c070b9a0c01dfa57d03514119
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321727"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Teams 라이브 이벤트의 발표자 및 참가자 기능
======================================================

Microsoft Teams 실시간 이벤트는 다양한 참가자 유형을 지원합니다. 참가자는 조직 내부 또는 외부의 역할에 따라 다양한 라이브 이벤트 기능에 액세스할 수 있습니다.

사용 가능한 모임 기능은 다음과 같습니다.

- 채팅(사진과 스티커 포함)
- 회의 노트
- 화이트보드
- 녹화
- 파일
- 모임 예약(모임에만 해당)

이 문서에서는 참가자 기능과 라이브 이벤트 기능에 대한 액세스 권한에 대해 설명합니다.

## <a name="presenters-and-organizers"></a>발표자 및 이끌이

발표자와 이끌이에게는 다음이 포함됩니다.

- 조직의 발표자
- 다른 조직의 발표자(라이브 이벤트 제한) - 익명 및 외부 참가자를 포함합니다. 발표자는 주최자가 지정하며 이끌이가 보낸 개인 초대가 있어야 합니다.

발표자와 이끌이는 라이브 이벤트의 모든 기능에 액세스할 수 있습니다.

## <a name="participants"></a>참가자

다양한 유형의 라이브 이벤트 참여자가 있습니다.

- [테넌트 내 참가자](#in-tenant-participant)
- [게스트 참가자](#guest-participant)
- [외부(연합) 참가자](#external-federated-participant)
- [익명 참가자](#anonymous-participant)

### <a name="in-tenant-participant"></a>테넌트 내 참가자

테넌트 내 참가자는 조직에 속하고 테넌트에 대한 자격 증명을 보유합니다. [보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 이 참가자에 대해 자세히 알아보세요.

| 라이브 이벤트 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **기능**       | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 예 | 예 | 예 |
| 회의 노트 | 예 | 예 |예 |
| 화이트보드 | 예 | 예 |예 |
| 녹화 | 해당 없음 |예 | 예 |
| 파일 | 예 | 예 | 예 |
|||||||


### <a name="guest-participant"></a>게스트 참가자

게스트 참가자는 Azure Active Directory B2B 플랫폼을 기반으로 조직의 테넌트에 있는 Teams 또는 기타 리소스에 액세스하도록 초대 받은 다른 조직의 사람입니다. 게스트 사용자를 정기 모임 및 채널 모임에 참가하도록 초대할 수 있습니다. 게스트 참가자에 대한 자세한 내용은 [What the guest experience is like(게스트 환경의 모양)](guest-experience.md#comparison-of-team-member-and-guest-capabilities)을 참조하세요.

| 라이브 이벤트  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **기능**        | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 예 | 예 | 예 |
| 회의 노트 | 예 | 예 | 예 |
| 화이트보드 | 아니요 | 아니요 | 아니요 |
| 녹화 | 해당 없음 | 아니요 | 아니요 |
| 파일 | 아니요 | 아니요 | 아니요 |
|||||||


### <a name="external-federated-participant"></a>외부(연합) 참여자

외부 참가자는 Teams를 사용하며 모임에 참가하도록 초대되었지만, 사용자 조직의 다른 공유 리소스에 대한 액세스 권한이 없는 다른 조직의 사용자입니다. 외부 사용자 참석자는 자신의 조직에서 사용하는 것과 동일한 ID 이름으로 모임 명단에 표시됩니다. [Communicate with users from other organizations(다른 조직의 사용자와 커뮤니케이션)](communicate-with-users-from-other-organizations.md#external-access)에서 외부 참가자에 대해 자세히 알아봅니다.

| 라이브 이벤트 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **기능**         | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 아니요| 예 | 예 |
| 회의 노트 | 아니요 | 아니요 | 아니요 |
| 화이트보드 | 아니요| 아니요 | 아니요 |
| 녹화 | 해당 없음 | 아니요 | 아니요 |
| 파일 | 예 | 예 | 예 |
|||||||

### <a name="anonymous-participant"></a>익명 참가자

익명 참가자는 외부 사용자와 유사하지만, ID가 모임에 적용되지 않습니다. 참여할 때 수동으로 별칭을 입력합니다. [보안 및 Microsoft Teams](teams-security-guide.md#participant-types)의 익명 참가자에 대해 자세히 알아보세요.

| 라이브 이벤트|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **기능**        | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 아니요 | 예 | 아니요 |
| 회의 노트 | 해당 없음 | 아니요 | 해당 없음 |
| 화이트보드 | 해당 없음 | 아니요 | 해당 없음 |
| 녹화 | 해당 없음 | 아니요 | 해당 없음 |
| 파일 | 해당 없음 | 아니요 | 해당 없음 |
|||||||


## <a name="related-topics"></a>관련 항목

[보안 및 Microsoft Teams](teams-security-guide.md)

[Teams의 게스트 액세스](guest-access.md)
