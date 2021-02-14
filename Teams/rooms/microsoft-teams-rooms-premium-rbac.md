---
title: Microsoft Teams Room Premium 서비스를 사용하여 역할 기반 액세스 제어
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 회의실 관리 서비스를 사용하여 역할 기반 액세스 제어에 대해 자세히 배워야 합니다.
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662603"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Microsoft Teams 회의실 관리 서비스를 사용하여 역할 기반 액세스 제어

Microsoft Teams Room 관리 서비스의 RBAC(역할 기반 액세스 제어)를 사용하면 조직의 회의실 리소스 데이터에 대한 사용자 액세스를 관리할 수 있습니다. 서비스 포털 사용자에게 역할을 할당하여 보고 변경할 수 있는 것을 제한할 수 있습니다. 각 역할에는 조직 내에서 액세스하고 변경할 수 있는 사용자를 결정하는 사용 권한 집합이 있습니다.

역할을 만들거나 편집하거나 할당하려면 계정에 다음 권한 중 하나만 있어야 합니다.

- Azure AD(Azure Active Directory)를 통한 전역 관리자
- Microsoft Teams 회의실 관리 서비스 포털을 통한 관리 서비스 관리자

## <a name="what-is-a-role"></a>역할이란?

역할은 해당 역할에 할당된 사용자에게 부여된 권한 집합을 정의합니다. 현재 Microsoft Teams 회의실 관리 서비스에는 **Managed Service Administrator,** Site **Lead** 및 Site Tech의 세 가지 기본 제공 **역할이 있습니다.** 회의실 관리와 관련될 수 있는 조직의 사용자에 대한 몇 가지 일반적인 시나리오를 다루고 있습니다.

역할을 확인하려면 Microsoft Teams 회의실 관리 서비스 포털의 왼쪽 탐색 모음에서 역할로 이동한 다음 역할 중 원하는 역할을 선택하여 역할의 속성, 사용 권한 및 할당을 봐야 합니다.  

- **속성:** 이름, 역할 유형 및 설명
- **사용 권한:** 역할에 액세스 권한이 있는 기능 및 사용 권한 수준을 나열합니다.
- **할당:** 방 리소스 계정의 범위에 대해 구성된 권한이 있는 사용자를 정의하는 역할 할당 목록입니다. 역할에는 여러 할당이 있을 수 있으며 사용자는 여러 할당에 있을 수 있습니다.

## <a name="built-in-roles"></a>기본 제공 역할

추가 구성 없이 그룹 또는 사용자에게 기본 제공 역할을 할당할 수 있습니다. 기본 제공 역할의 이름, 설명, 형식 또는 사용 권한을 삭제하거나 편집할 수 없습니다.

- **관리 서비스 관리자:** Microsoft Teams Room Premium 서비스 포털에 대한 모든 권한이 있습니다.
- **사이트 잠재 고객:** 회의실을 구성하고 보고서에 액세스할 수 있으며 티켓을 관리할 수 있습니다. 등록 키를 다시 설정하거나 서비스의 구성을 변경할 수 없습니다.  
- **사이트 기술:** 특정 회의실의 티켓을 관리합니다. 서비스를 수정하거나 서비스에서 회의실을 구성할 수 있는 권한이 없습니다.

다음 표에서는 각 역할이 할 수 있는 작업을 요약합니다.

|기능 |사용 권한 |관리 서비스 관리자  |사이트 잠재 고객  |Site Tech  |
|---------|---------|---------|---------|---------|
|회의실     |보기        |&#10004;           |&#10004;           |&#10004;  |
|    |수정         |&#10004;           |&#10004;           |&#10004; |
|    |키 다시 설정         |&#10004;           |         ||
|    |다운로드 키         |&#10004;           |&#10004;          |&#10004; |
|    |Unenroll         |&#10004;           |&#10004;           |&#10004; |
|그룹 관리   |만들기         |&#10004;           |           ||
|    |보기       |&#10004;          |&#10004;           ||
|    |수정         |&#10004;           |           ||
|업데이트 링 관리    |만들기         |&#10004;           |           ||
|    |보기         |&#10004;           |           ||
|    |수정         |&#10004;           |           ||
|보고서   |보기        |&#10004;           |&#10004;           ||
|티켓 관리   |고객 인시던트 만들기         |&#10004;           |&#10004;           |&#10004;  |
|    |보기         |&#10004;           |&#10004;           |&#10004;  |
|    |업데이트         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft Teams Rooms 관리 서비스 설정    |보기         |&#10004;           |         ||
|    |수정        |&#10004;           |         ||
|역할 관리    |보기         |&#10004;           |         ||
|    |수정         |&#10004;           |         ||

## <a name="assign-a-role"></a>역할 할당

역할을 할당하려면 전역 관리자 또는 관리 서비스 관리자해야 합니다.

1. Microsoft Teams 회의실 관리 서비스 포털의 왼쪽 탐색 모음에서 설정  >  **역할로 이동합니다.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="역할을 보여주는 액세스 제어 페이지의 스크린샷":::

2. 할당할 역할을 선택합니다.
3. 역할 창에서 할당 **추가를**  >  **선택합니다.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="역할을 추가하는 추가 옵션의 스크린샷":::

4. 일반 **설정 페이지의** 할당 속성 아래에서 이 할당의 이름을 입력합니다. 설명은 선택 사항입니다. 다음을 **선택**
5. 구성원  페이지의 사용자 또는  보안 그룹 검색 상자에 사용 권한을 부여하려는 테넌트의 사용자 또는 보안 그룹의 이름을 입력한 다음 선택을 완료합니다. 다음을 **선택** 
6. 범위 **페이지의** 방 또는  방 그룹 검색 상자에 사용자가 관리할 수 있는 방 또는 방 그룹의 이름을 입력합니다. 다음을 **선택**
7. 완료 **페이지에서** 과제의 세부 정보를 검토합니다. 구성에 만족하면 할당 **추가를 선택 합니다.** 섹션을 편집하려면 이전 단추를  사용하거나 왼쪽 탐색에서 단계를 선택합니다.  

## <a name="related-topics"></a>관련 항목

- [Microsoft Teams 회의실 관리 서비스](microsoft-teams-rooms-premium.md)
