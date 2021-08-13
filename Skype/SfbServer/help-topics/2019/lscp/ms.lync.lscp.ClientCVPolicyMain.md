---
title: 클라이언트 버전 정책
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다.
ms.openlocfilehash: 4cd788cce5c90e03d2b4b22363fb91ceef4fe79f221a895d00b61275bd2886f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304320"
---
# <a name="client-version-policy"></a>클라이언트 버전 정책

사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다. 사용자 환경에 포함된 기능을 비즈니스용 Skype 서버 전체 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**클라이언트 버전 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.

- **기본(전역)** 클라이언트 버전 정책을 편집합니다.

- 특정 사이트 또는 풀에 대한 클라이언트 버전 정책 만들기

- 개별 사용자에게 할당할 수 있는 클라이언트 버전 정책 만들기

> [!NOTE]
> 익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **새로 추가** 다음 각 클라이언트 버전 정책을 하나 이상 만들 수 있습니다.

  - 사이트 정책

  - 풀 정책

  - 사용자 정책

- **편집** 클라이언트 버전 정책의 옵션을 변경할 수 있습니다. 이 옵션을 사용하여 다음을 할 수 있습니다.

  - **세부 정보 표시** 이 옵션을 선택하면 클라이언트 버전 정책에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.

  - **모두 선택** 이 옵션은 목록의 모든 클라이언트 버전 정책을 선택합니다.

  - **삭제** 이 옵션은 선택한 모든 클라이언트 버전 정책을 삭제합니다.

- **새로 고침** 클라이언트 버전 정책 목록을 새로 고쳐 모든 클라이언트 버전 정책의 옵션 상태를 확인할 수 있습니다.

클라이언트와 클라이언트 버전 간 상호 연결성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability를](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 참조하십시오. 클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)을 참조하십시오.