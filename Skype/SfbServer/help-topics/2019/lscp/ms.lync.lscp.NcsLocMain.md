---
title: 위치 정책
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.
ms.openlocfilehash: 6be87514ef98d23ccc0440b55451d40d7f2bc584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752873"
---
# <a name="location-policy"></a>위치 정책

위치 정책은 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정합니다.

위치 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.

- **글로벌 정책:** 전역 정책은 기본적으로 만들어집니다. 글로벌 정책을 편집할 수는 있지만 삭제할 수는 없습니다. 글로벌 정책을 제거하려고 하면 모든 설정이 기본값으로 다시 설정됩니다.

- **사이트 정책(선택 사항):** 하나 이상의 사이트 위치 정책을 만들 수 있습니다. 각 정책은 특정 사이트에 적용됩니다. 사이트 정책은 글로벌 정책을 재정의합니다.

- **사용자 정책(선택 사항):** 하나 이상의 사용자 위치 정책을 만들 수 있습니다. 각 정책은 특정 사용자 또는 사용자 그룹에 적용됩니다. 사용자 정책은 글로벌 정책 및 사이트 정책을 재정의합니다.

> [!NOTE]
> 서브넷 그룹인 네트워크 사이트에 위치 정책을 할당할 수도 있습니다. 네트워크 사이트에 할당된 위치 정책은 다른 모든 사용자 정책보다 우선적으로 적용됩니다. cmdlet을 사용하여 네트워크 사이트에 위치 정책을 할당하는 데 대한 자세한 내용은 [add a location policy to a network site in 비즈니스용 Skype 서버.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md) 네트워크 사이트에 위치 정책을 할당하는 비즈니스용 Skype 서버 제어판을 사용하는 데 대한 자세한 내용은 [Configuring Network Sites을 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)

**위치 정책** 페이지에는 조직에 대해 정의된 모든 위치 정책의 목록이 표시됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**위치 정책** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 새 사이트 위치 정책 또는 사용자 위치 정책 만들기

- 글로벌 정책 또는 기존 사이트 정책/사용자 정책 변경

- 사이트 정책 또는 사용자 정책 삭제

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 명령에 대해 설명합니다.

- **새로 추가** 새 사이트 위치 정책 또는 사용자 위치 정책을 시작합니다.

- **편집** 선택한 위치 정책을 열어 편집하거나, 목록의 모든 위치 정책을 선택하거나, 선택한 사이트 정책 또는 사용자 정책을 삭제합니다.

    > [!NOTE]
    > 글로벌 정책의 경우 **삭제** 를 클릭하면 설정이 기본값으로 다시 설정됩니다.

- **새로 고침** 위치 정책 목록을 새로 고침합니다.

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 위치 정책을 식별합니다.

- **범위** 위치 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.

- **E9-1-1** 이 위치 정책이 할당된 사용자가 E9-1-1을 사용할 수 있도록 설정되어 있는지 확인합니다.

- **위치** 클라이언트가 새 위치에서 비즈니스용 Skype 서버 등록할 때 위치 정보를 입력하라는 메시지가 사용자에게 표시될지 여부와 위치 정보를 입력하지 않고 메시지를 해지할 경우 고지 사항은 사용자에게 표시될지 여부를 지정합니다.

- **PSTN 사용** 이 프로필을 사용하여 클라이언트의 긴급 통화를 라우팅하는 데 사용되는 음성 경로를 결정하는 데 사용되는 PSTN(Public Switched Telephone Network) 사용을 지정합니다.

- **E9-1-1 번호** 응급 서비스에 연결하기 위해 전화를 걸 번호를 지정합니다.

- **E9-1-1 마스크** 사용자가 전화를 걸 때 긴급 전화 번호로 변환되는 번호를 지정합니다.

긴급 서비스 Enterprise Voice 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of E9-1-1를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) 참조하십시오. 위치 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)을 참조하십시오.