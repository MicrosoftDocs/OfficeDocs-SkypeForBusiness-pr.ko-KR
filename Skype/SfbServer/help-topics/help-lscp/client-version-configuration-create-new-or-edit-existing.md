---
title: 클라이언트 버전 구성 새로 만들기 또는 기존 버전 편집
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 비즈니스용 Skype 서버 설치되고 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 또는 사용하지 않도록 설정하는 데 사용됩니다. 전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다. 클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.
ms.openlocfilehash: 5dd3f1297ec618346a35424ca323d236b8527c62
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752317"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>클라이언트 버전 구성: 새로 만들기 또는 기존 항목 편집

클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 비즈니스용 Skype 서버 설치되고 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 또는 사용하지 않도록 설정하는 데 사용됩니다. 전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다. 클라이언트 버전 제어를 수행하지 않으려면 전역 클라이언트 버전 구성을 사용하지 않도록 설정하면 됩니다.

사이트별로 클라이언트 버전 제어를 사용하거나 사용하지 않도록 설정할 수 있는 사이트별 클라이언트 버전 구성을 만들 수도 있습니다. 사이트별 구성은 전역 구성보다 우선적으로 적용됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.

- 클라이언트 버전 구성의 이름 추가 또는 수정

- 클라이언트 버전 제어를 전역적으로 또는 특정 사이트에 대해 사용하거나 사용하지 않도록 설정

- 클라이언트 버전 구성에 대한 기본 작업 추가 또는 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **범위** 클라이언트 버전 구성의 범위(전역 또는 사이트)를 식별합니다.

- **이름** 클라이언트 버전 구성의 이름을 추가하거나 수정할 수 있습니다.

- **버전 제어 사용** 구성 범위에 따라 전역적으로 또는 사이트에 대해 클라이언트 버전 제어를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

- **기본 작업** 사용자가 특정 클라이언트 버전 정책이 없는 클라이언트 응용 프로그램을 사용하여 로그온을 시도할 때 적용되는 기본 작업을 선택할 수 있습니다. 다음과 같은 옵션을 선택할 수 있습니다.

  - **허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 허용합니다.

  - **차단** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 방지합니다.

  - **URL로 차단** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 방지하고 새 클라이언트를 다운로드할 수 있는 URL이 포함된 오류 메시지를 포함합니다.

  - **URL로 허용** 클라이언트 버전이 클라이언트 버전 정책 목록의 필터와 일치하지 않는 경우 클라이언트 로그온을 허용하고 새 클라이언트를 다운로드할 수 있는 URL이 포함된 오류 메시지를 포함합니다.

  - **URL** **URL로** 차단 또는 **URL로** 허용을 선택한 경우 오류 메시지에 포함할 클라이언트 다운로드 URL을 지정할 수 있습니다.

클라이언트 및 클라이언트 버전 간의 상호 운용성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)을 참조하십시오. 클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)을 참조하십시오.