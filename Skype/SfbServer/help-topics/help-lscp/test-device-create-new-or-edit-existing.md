---
title: 테스트 장치 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 표시됩니다.
ms.openlocfilehash: 6a472923040dbf1101044a28667cb1358399f808
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099374"
---
# <a name="test-device-create-new-or-edit-existing"></a>테스트 장치: 새로 만들기 또는 기존 항목 편집

테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치를 전역적으로(전체 환경 전체) 또는 단일 사이트 내에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가하면 비즈니스용 Skype 서버 제어판의 테스트 장치 페이지에 있는 목록에 표시됩니다. 

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 테스트 장치** 또는 **테스트 장치 편집** 페이지에서 다음 작업을 수행할 수 있습니다.

- 새 테스트 장치 추가

- 기존 테스트 장치의 속성 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **범위** 테스트 장치의 범위(전역 또는 사이트)를 식별합니다.

- **이름** 테스트 장치의 이름을 추가하거나 수정할 수 있습니다.

- **장치 이름** 테스트 장치의 이름을 추가하거나 수정할 수 있습니다.

- **식별자 유형** 다음 중 하나를 선택하여 디바이스를 식별하는 데 사용할 방법을 선택할 수 있습니다.

  - **MAC 주소**

  - **일련 번호**

- **고유 식별자** 장치의 MAC 주소 또는 일련 번호를 입력할 수 있습니다.

장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서에서 [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)를 참조하십시오.
## <a name="see-also"></a>참고 항목

[장치 테스트](test-device.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[조직에서 장치에 대한 소프트웨어 업데이트 보기](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)