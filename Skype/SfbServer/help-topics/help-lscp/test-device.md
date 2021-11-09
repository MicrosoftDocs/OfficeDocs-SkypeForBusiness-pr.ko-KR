---
title: 테스트 장치
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 디바이스를 추가하면 디바이스가 제어판의 테스트 장치 페이지에 비즈니스용 Skype 서버 표시됩니다.
ms.openlocfilehash: affad15aca974f389b23b693caca92d5bc9981cf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857725"
---
# <a name="test-device"></a>테스트 장치

테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 디바이스를 추가하면 디바이스가 제어판의 테스트  장치 페이지에 비즈니스용 Skype 서버 표시됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**테스트 장치** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 테스트 장치를 전역적으로 또는 특정 사이트에 대해 추가

- 기존 테스트 장치에 대한 옵션 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **새로 추가** 다음 범위를 사용하여 새 테스트 장치를 추가할 수 있습니다.

  - 전역

  - 사이트

- **편집** 목록에서 테스트 장치의 옵션을 변경할 수 있습니다. 이 옵션을 사용하여 다음을 할 수 있습니다.

  - **세부 정보 표시** 이 옵션을 선택하면 테스트 장치의 옵션을 변경할 수 있는 대화 상자가 열립니다.

  - **모두 선택** 이 옵션은 목록의 모든 테스트 장치를 선택합니다.

  - **삭제** 이 옵션은 선택한 모든 테스트 장치를 삭제합니다.

- **새로 고침** 테스트 장치 목록을 새로 고쳐 모든 테스트 장치의 옵션 상태를 확인할 수 있습니다.

장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서에서 [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)를 참조하십시오.
## <a name="see-also"></a>참고 항목

[장치 테스트: 새로 만들기 또는 기존 항목 편집](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[조직에서 장치에 대한 소프트웨어 업데이트 보기](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)