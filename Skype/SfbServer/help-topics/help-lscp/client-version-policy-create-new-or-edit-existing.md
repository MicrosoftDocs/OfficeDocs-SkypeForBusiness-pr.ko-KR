---
title: 클라이언트 버전 정책 새로 만들기 또는 기존 버전 편집
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다. 비즈니스용 Skype 서버 2015에 포함된 기능을 가장 잘 활용하고 전반적인 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.
ms.openlocfilehash: c6674d1efcc7791511870234754876b966f492a4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389240"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>클라이언트 버전 정책: 새로 만들기 또는 기존 항목 편집

사용자 환경에서 지원되는 클라이언트 버전을 지정할 수 있습니다. 버전이 다른 두 클라이언트가 상호 작용할 경우 각 클라이언트의 기능이 다른 클라이언트에서 사용할 수 있는 기능을 제한할 수 있습니다. 비즈니스용 Skype 서버 2015에 포함된 기능을 가장 잘 활용하고 전반적인 사용자 환경을 개선하기 위해 클라이언트 버전 필터를 사용하여 환경에서 사용되는 클라이언트 버전을 제한할 수 있습니다. 클라이언트 버전 필터를 사용하면 여러 클라이언트 버전을 지원할 때 비용을 절감하는 데에도 도움이 됩니다.

> [!IMPORTANT]
> 필터는 우선 순위에 따라 나열됩니다. 예를 들어 버전 1.5를 실행하는 클라이언트에 연결을 허용하는 필터 다음에 2.0 이전 버전을 실행하는 클라이언트를 차단하는 필터가 있는 경우 첫 번째 필터가 우선적으로 적용되므로 버전 1.5를 실행하는 클라이언트에 연결이 허용됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 클라이언트 버전 정책** 또는 **클라이언트 버전 정책 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 클라이언트 버전 정책의 이름이나 설명 추가 또는 수정

- 클라이언트 버전 정책에 대한 클라이언트 버전 규칙 추가 또는 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **범위** 클라이언트 버전 정책의 범위(사이트, 풀 또는 사용자)를 식별합니다.

- **이름** 클라이언트 버전 정책의 이름을 추가하거나 수정할 수 있습니다.

- **설명** 클라이언트 버전 정책 페이지의 목록에서 정책을 식별하는 데 도움이 되는 설명을 추가할 수 있습니다.

- **새로운** 정책에 새 클라이언트 버전 규칙을 추가할 수 있습니다.

- **세부 정보 표시** 이 옵션을 선택하면 클라이언트 버전 규칙에 대한 옵션을 변경할 수 있는 대화 상자가 열립니다.

- **제거** 이 옵션은 정책에서 선택한 클라이언트 버전 규칙을 제거합니다.

- **위쪽 및 아래쪽 화살표** 이 옵션을 선택하면 선택한 클라이언트 버전 규칙이 우선 순위에서 아래로 이동됩니다. 규칙은 나열된 순서대로 처리됩니다.

클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)을 참조하십시오. 클라이언트 버전 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)을 참조하십시오.