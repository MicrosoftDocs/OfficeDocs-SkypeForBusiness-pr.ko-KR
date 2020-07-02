---
title: Teams 모임의 발표자 및 참가자 기능
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
description: Teams 모임의 발표자 및 참가자 기능에 대해 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0302a5c1f09e6ed6bfbb877709ed3562ce1440a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938177"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Teams 모임의 발표자 및 참가자 기능
======================================================

Microsoft Teams 모임은 다양한 참가자 유형을 지원합니다. 참가자는 조직 내부 또는 외부의 역할에 따라 다양한 모임 기능에 액세스할 수 있습니다.

사용 가능한 모임 기능은 다음과 같습니다.

- 채팅(사진 및 스티커 포함)
- 회의 노트
- 화이트보드
- 녹음/녹화
- 파일
    - 모임 채팅으로 파일 공유 및 모임 채팅에서 파일 보기/다운로드
    - (화면 공유가 아닌) 미팅에서 PPT를 제시하고 미팅에서 PPT를 봅니다.
- 모임 예약(모임에만 해당)

해당 문서에서는 참가자 기능과 모임 기능에 대한 액세스 권한에 대해 설명합니다.

## <a name="presenters-and-organizers"></a>발표자 및 주최자

발표자와 주최자에게는 다음이 포함됩니다.

- 조직의 발표자
- 다른 조직의 발표자 - 익명 및 외부 참가자를 포함합니다. 발표자는 주최자가 지정하며 주최자가 보낸 개인 초대가 있어야 합니다.

발표자 및 주최자는 모임 또는 라이브 이벤트의 모든 기능에 액세스할 수 있습니다.

## <a name="participants"></a>참가자

다양한 유형의 모임 참가자가 있습니다.

- [테넌트 내 참가자](#in-tenant-participant)
- [게스트 참가자](#guest-participant)
- [외부(페더레이션) 참가자](#external-federated-participant)
- [익명 참가자](#anonymous-participant)

### <a name="in-tenant-participant"></a>테넌트 내 참가자

테넌트 내 참가자는 조직에 속하고 테넌트에 대한 자격 증명을 보유합니다. [보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 해당 참가자에 대해 자세히 알아봅니다.

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **기능**        | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 예 | 예 | 예 |
| 회의 노트 | 예 | 예 |예 |
| 화이트보드 | 예 | 예 |예 |
| 녹음/녹화 | 해당 없음 |예 | 예 |
| 파일 - 모임 채팅으로 파일 공유 및 모임 채팅에서 파일 보기/다운로드 | 예 | 예 | 예 |
| 파일 - (화면 공유가 아닌) 미팅에서 PPT를 제시하고 미팅에서 PPT를 봅니다. | 예 | 예 | 예 |
| 모임 예약 | 예 | 해당 없음 | 해당 없음 |
|||||||

### <a name="guest-participant"></a>게스트 참가자

게스트 참가자는 Azure Active Directory B2B 플랫폼을 기반으로 조직의 테넌트에 있는 Teams 또는 기타 리소스에 액세스하도록 초대 받은 다른 조직의 참가자입니다. 게스트 사용자를 정기 모임 및 채널 모임에 참가하도록 초대할 수 있습니다. [What the guest experience is like(게스트 환경의 특징)](guest-experience.md#comparison-of-team-member-and-guest-capabilities)에서 게스트 참가자에 대해 자세히 알아봅니다.

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **기능**        | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 예 | 예 | 예 |
| 회의 노트 | 예 | 예 | 예 |
| 화이트보드 | 아니요 | 아니요 |아니요 |
| 녹음/녹화 | 해당 없음 |아니요 | 아니요 |
| 파일 - 모임 채팅으로 파일 공유 및 모임 채팅에서 파일 보기/다운로드 | 예 | 예 | 예 |
| 파일 - (화면 공유가 아닌) 미팅에서 PPT를 제시하고 미팅에서 PPT를 봅니다. | 예 | 예 | 예 |
| 모임 예약 | 아니요 | 해당 없음 | 해당 없음 |
|||||||

### <a name="external-federated-participant"></a>외부(페더레이션) 참가자

외부 참가자는 Teams를 사용하며 모임에 참가하도록 초대되었지만 사용자 조직의 다른 공유 리소스에 대한 액세스 권한이 없는 다른 조직의 사용자입니다. 외부 사용자 참가자는 자신의 조직에서 사용하는 것과 동일한 ID 이름으로 모임 명단에 표시됩니다. [Communicate with users from other organizations(다른 조직의 사용자와 커뮤니케이션)](communicate-with-users-from-other-organizations.md#external-access)에서 외부 참가자에 대해 자세히 알아봅니다.

|  ||
|-|-|-|
| **기능** |||
| 채팅 | 예 |
| 회의 노트 | 해당 없음 |  
| 화이트보드 | 해당 없음 |
| 녹음/녹화 | 해당 없음 |  
| 파일 - 모임 채팅으로 파일 공유 및 모임 채팅에서 파일 보기/다운로드 |  |  |  |
| 파일 - (화면 공유가 아닌) 미팅에서 PPT를 제시하고 미팅에서 PPT를 봅니다. |  |  |  |
| 모임 예약 | 해당 없음 |
|||

### <a name="anonymous-participant"></a>익명 참가자

익명 참가자는 외부 사용자와 유사하지만 ID가 모임에 프로젝션되지 않습니다. 참가 시 별칭을 직접 입력합니다. [보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 익명 참가자에 대해 자세히 알아봅니다.

|   | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **기능**        | 사전 모임 | 모임 중 | 모임 후 |
| 채팅 | 해당 없음 | 예 | 해당 없음 |
| 회의 노트 | 해당 없음 | 아니요 | 해당 없음 |
| 화이트보드 | 해당 없음 | 아니요 | 해당 없음 |
| 녹음/녹화 | 해당 없음 | 아니요 | 해당 없음 |
| 파일 - 모임 채팅으로 파일 공유 및 모임 채팅에서 파일 보기/다운로드 |  |  |  |
| 파일 - (화면 공유가 아닌) 미팅에서 PPT를 제시하고 미팅에서 PPT를 봅니다. |  |  |  |
| 모임 예약 | 해당 없음 | 해당 없음 | 해당 없음 |
|||||||

## <a name="related-topics"></a>관련 항목

[보안 및 Microsoft Teams](teams-security-guide.md)

[Teams의 게스트 액세스](guest-access.md)
